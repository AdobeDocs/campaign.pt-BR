---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 6693bb8a62c0d126b871dc24a75b76de71b86f8d
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 21%

---

# Versões mais recentes {#latest-release}

Esta página lista novos recursos, melhorias e correções das **últimas versões** do Campaign v8 (console). Saiba mais sobre lançamentos, versões e atualizações do Campaign [nesta página](upgrades.md). Outras versões estão listadas na seção Versões anteriores desta documentação.

## Versão 8.9.1 {#release-8-9-1}

_27 de janeiro de 2026_

>[!CAUTION]
>
> A atualização do Console do Cliente é obrigatória. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

### Novos recursos {#new-8-9-1}

O **novo conector de envio de SMS** agora está disponível para todos os clientes (GA). Consulte a [documentação detalhada](../send/sms/sms.md).

Esta versão é fornecida com um conjunto de funcionalidades disponíveis na interface da Web do Campaign:

* [Recursos de entrega multilíngue (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=pt-BR){target="_blank"}
* [Enriquecimento de Perfil em Mensagens Transacionais (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=pt-BR){target="_blank"}
* [Adobe Experience Manager live e cópias de idioma](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [Experimentos de conteúdo - teste A/B](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html)
* [Atividade de entrega contínua](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html)
* [Gerenciamento de aprovação de campanha](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html)

Consulte as [notas de versão](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=pt-BR){target="_blank"} da interface da Web do Campaign

### Melhorias de segurança {#security-8-9-1}

* As contas externas do Snowflake agora oferecem suporte à autenticação OAuth2, fornecendo métodos de autenticação modernos e seguros para conexões de acesso a dados federados. (NEO-87013)
* Correção de vulnerabilidades de acesso a arquivos de workflow restringindo operações a diretórios autorizados, impedindo o acesso não autorizado e a possível execução remota de código. (NEO-88460)
* Adição do URL FTP, que incluir na lista de permissões os controles às atividades de fluxo de trabalho do código JavaScript, restringindo as conexões de FTP de saída somente aos endereços autorizados. (NEO-89083)

### Outras alterações {#changes-8-9-1}

* Gerenciamento aprimorado da memória do contêiner ao implementar a limitação automática do fluxo de trabalho durante condições de alta memória, com recursos inteligentes de reinicialização do fluxo de trabalho e medidas de proteção de memória para processos não críticos. (NEO-89041)
* Adição de suporte para funções de criptografia assimétrica e descriptografia em workflows do Campaign. (NEO-80257)
* Desempenho aprimorado do agente de replicação e resiliência de memória para uploads de dados grandes em implantações FFDA. (NEO-88430)


### Correções {#fixes-8-9-1}

* Correção de um problema em que os relatórios dinâmicos exibiam contagens incorretas ao serem agrupados por determinadas colunas. (NEO-86898)
* Solução de discrepâncias de dados entre relatórios dinâmicos e dados reais da campanha. (NEO-88068)
* Correção de problemas de concatenação com tipos de campo &quot;char&quot; do PostgreSQL que causavam resultados inesperados em consultas. (NEO-87769)
* Correção de um problema em que o comando logInfo do JavaScript não tratava corretamente de determinados parâmetros. (NEO-88263)
* Solução de problemas de travamento de sincronização no processamento de eventos em tempo real do Centro de mensagens. (NEO-88330)
* Correção de um problema em que o Editor visual reformatava automaticamente o conteúdo do HTML, causando alterações no layout. (NEO-88409)
* Correção de um problema em que a atividade Desduplicação não funcionava corretamente com esquemas temporários. (NEO-88577)
* Correção de um problema que impedia que seed addresses fossem gerados ao enviar provas. (NEO-88720)
* Desempenho de consulta PostgreSQL aprimorado por meio da otimização do tratamento de colunas de partição. (NEO-88771)
* Correção de um problema em que as atividades de transferência de arquivos não lidavam corretamente com caracteres de continuação de linha. (NEO-88812)
* Otimização aprimorada de consultas PostgreSQL para melhor desempenho em grandes conjuntos de dados. (NEO-88885)
* Correção de um erro &quot;Permissão negada&quot; que impedia a abertura de campanhas híbridas. (NEO-88955)
* Suporte estendido a recursos de código de barras para manipular strings de texto mais longas. (NEO-88958)
* Correção de um erro nos logs de campanha que ocorria ao usar provas com deliveries recorrentes. (NEO-88976)
* Correção de um problema que afetava as operações de envio de email em determinados cenários. (NEO-89019)
* Solução de um problema em que o modo de início do fluxo de trabalho era alterado inesperadamente de Imediato para Normal. (NEO-89025)
* Correção de erros que ocorriam ao executar a atividade Atualizar dados em condições específicas. (NEO-89031)
* Correção de um problema em que a atividade Atualizar dados perdia metadados de esquema personalizados. (NEO-89056)
* Correção de um erro de validação que ocorria durante a preparação do delivery. (NEO-89063)
* Resolução de geração SQL inválida quando as consultas continham filtros em relações de link 1-1. (NEO-89065)
* Correção de um problema em que a atividade Consulta incremental não respeitava o limite de tamanho configurado. (NEO-89066)
* Desempenho de fluxo de trabalho aprimorado em implantações FFDA para operações de grande escala. (NEO-89098)
* Gerenciamento de memória e estabilidade aprimorados para processos de workflow. (NEO-89105)
* Ativação da validação de coluna estrita para formulários web para evitar inconsistências de dados. (NEO-89111)
* Solução de problemas de sincronização do Centro de mensagens que causavam atrasos de processamento. (NEO-89138)
* Correção de erros no fluxo de trabalho &quot;Atualizar para entregabilidade&quot; que impediam a execução adequada. (NEO-89160)
* Correção de erros que ocorriam ao executar atividades de código JavaScript em workflows. (NEO-89169)
* Remoção de configurações de warehouse codificadas do Snowflake para permitir configurações de conta externa apropriadas. (NEO-89201)
* Correção de 403 erros proibidos que ocorriam durante operações de transferência de arquivos do workflow. (NEO-89226)
* Consultas lentas otimizadas na tabela de recipients em implantações do FFDA. (NEO-89268)
* Correção de um problema em que as atividades de query incremental ignoravam os agendamentos configurados. (NEO-89317)
* Correção de erros de acesso ao abrir campanhas em ambientes híbridos. (NEO-89320)
