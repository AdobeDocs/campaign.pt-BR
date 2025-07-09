---
title: Migração para o novo conector SMS v2
description: Saiba como migrar para o novo conector SMS v2
feature: Technote
role: Admin
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Migração para o novo conector SMS v2

Este documento descreve o procedimento e as principais considerações ao migrar do conector de SMS baseado em MTA para o novo **conector de processo de SMS dedicado** no Adobe Campaign v8.

## Por que alternar para o conector v2

O processo SMS dedicado apresenta suporte para o modo transceptor SMPP, reduzindo a contagem de conexões e melhorando a eficiência dos recursos, enquanto ainda oferece suporte às configurações de transmissor/receptor, se necessário. Ele oferece estabilidade significativamente maior, com recuperação mais rápida de erros, conexões persistentes e sem dependência de arquivos locais ou comunicação entre processos. O desempenho também é aprimorado, com latência mais baixa, throughput mais alta e microlotes inteligentes para equilibrar a velocidade e a confiabilidade. Além disso, o isolamento do processo de SMS simplifica a solução de problemas e minimiza o impacto entre canais. Esses aprimoramentos tornam o conector dedicado uma solução mais robusta e escalável para entrega de SMS.

## Diferenças entre conectores v1 e v2

O conector SMS dedicado no Adobe Campaign v8 apresenta várias alterações de arquitetura em comparação ao conector baseado em MTA. Uma diferença importante é o uso padrão do modo transceptor SMPP, que reduz o número de conexões combinando funções de envio e recebimento. Se o provedor não oferecer suporte a esse modo, ainda será possível usar conexões de transmissor e receptor separadas. Diferentemente do conector MTA, ativar respostas automáticas não afeta a contagem de conexões e todas as conexões de receptor podem lidar com qualquer tipo de mensagem recebida.

A contagem de conexões agora é calculada usando uma fórmula diferente:

```
Total connections = SMS sending threads * Number of MTA child connections. 
```

O parâmetro sendingThreads, definido no serverConf, assume o padrão 1 e geralmente deve permanecer inalterado, a menos que seja otimizado especificamente para alto desempenho. Como um único processo lida com todo o tráfego de SMS, o gerenciamento do paralelismo por meio desses parâmetros se torna essencial para controlar a carga e o comportamento do sistema.

A janela de envio se comporta de forma semelhante ao conector MTA, mas tem um impacto ainda maior no desempenho no modo dedicado. Janelas de envio maiores reduzem o IOPS do banco de dados e melhoram a taxa de transferência. O Campaign pode lidar com janelas de mais de 1000 mensagens com eficiência, desde que o provedor ofereça suporte a isso e o caso de uso permita uma pequena margem de perda ou duplicação de mensagens em caso de problemas de conexão. No lado do provedor, configurar uma janela de envio de SR maior também pode melhorar significativamente a taxa de transferência do relatório de entrega.

Por fim, enquanto o manuseio de mensagem MO (Originado por dispositivo móvel) permanece funcionalmente inalterado, o código subjacente foi atualizado. A taxa de transferência por conexão ainda é limitada da mesma maneira, mas o conector dedicado permite um envio de intermitência muito mais rápido. No entanto, sem limites de taxa de transferência, o envio de alta velocidade pode sobrecarregar os recursos do provedor ou do sistema, tornando aconselhável definir limites explícitos de taxa de transferência de MT na configuração da conta externa.

## Procedimento de switching

Para garantir uma alternância suave para o processo de SMS dedicado, é melhor executar a operação durante tráfego baixo ou sem tráfego de SMS. Algumas mensagens em buffer podem ser perdidas ou deixadas em um estado inválido se os buffers do MTA não forem totalmente liberados. Também é normal perder alguns SRs por até uma semana após o switch, devido ao tempo de SR imprevisível. Não seguir essas precauções pode levar à perda ou duplicação de mensagens, apesar das salvaguardas incorporadas.

Ambos os conectores SMS usam formatos diferentes para o processamento SR (Relatório de Status). Embora ambos dependam da tabela `NmsProviderMsgId`, interagem com ela de forma diferente. Portanto, a alternância de conectores requer a limpeza de toda a tabela para evitar conflitos ou dados órfãos. Há várias maneiras de executar essa limpeza. Abaixo estão as queries SQL que você pode usar:

```
TRUNCATE TABLE NmsProviderMsgId;
TRUNCATE TABLE NmsProviderMsgStatus;
```

### Etapas

1. Revisar configurações de `serverConf` (`sms > mta2`).
1. Pausar o fluxo de trabalho de preparação de mensagens em tempo real (se aplicável).
1. Pausar todos os deliveries de SMS.
1. Desative a conta externa do SMS.
1. Pare e reinicie os processos de MTA e SMS.
1. Verifique se nenhuma conexão SMPP está ativa. Se presente, verifique se todos os deliveries estão pausados.
1. Limpar o conteúdo das tabelas `NmsProviderMsgId` e `NmsProviderMsgStatus` no banco de dados.
1. Na conta externa:
   * Ative a caixa de seleção &quot;Processo dedicado&quot;
   * Ajustar outras configurações: conexões filho do MTA, taxa de transferência do MT, Janela de envio
1. Reative a conta externa e salve.
1. Retomar deliveries de SMS.
1. Verifique se os serviços SMS funcionam normalmente.

>[!NOTE]
>
>Monitore erros ou problemas nos logs secundários de SMS, MTA e MTA.
>
>Salvar configurações anteriores da conta externa para fins de reversão.

### Procedimento de reversão

A reversão para o conector MTA é possível seguindo as mesmas etapas usadas durante o switch inicial, na mesma ordem. Isso inclui interromper ou pausar todos os deliveries de SMS e restaurar a configuração original da conta externa.

1. Se a instância usar deliveries em tempo real, pause o workflow técnico responsável por preparar essas mensagens.
1. Pausar todos os deliveries de SMS.
1. Desative a conta externa do SMS.
1. Pare e reinicie os processos de MTA e SMS.
1. Verifique se nenhuma conexão SMPP permanece ativa; em caso positivo, verifique se todos os deliveries estão pausados corretamente.
1. Limpar as tabelas `NmsProviderMsgId` e `NmsProviderMsgStatus` no banco de dados.
1. Na conta externa:
   * Desmarque a opção &quot;dedicated process&quot; na conta externa.
   * Restaurar todas as configurações de conta externa anteriores: conexões filho do MTA, taxa de transferência do MT, janela de envio
1. Reative e salve a conta externa.
1. Retomar todos os deliveries de SMS.
1. Por fim, confirme se os serviços SMS estão funcionando normalmente.
