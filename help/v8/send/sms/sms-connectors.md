---
title: Conectores SMS
description: Saiba mais sobre conectores SMS no Adobe Campaign
feature: SMS
role: User, Admin
level: Intermediate
source-git-commit: e349e9f236c3eeb28ffe96bcc5ec72ab64c4c127
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 1%

---

# Sobre tipos de conectores SMS {#sms-connectors}

O Adobe Campaign oferece suporte a dois conectores SMS usados para enviar mensagens SMS aos clientes:

* **Conector SMS herdado**: primeira versão do conector usado no Campaign v7 e versões anteriores do Campaign v8. [Saiba mais](#legacy-sms-connector)
* **Conector SMS v2**: disponível no GA a partir do Campaign v8.9.1, esse conector SMS dedicado v2 foi modernizado para oferecer melhor desempenho e confiabilidade. [Saiba mais](#sms-connector-v2)

## Conector SMS herdado {#legacy-sms-connector}

O conector SMS herdado é o conector SMS baseado em MTA usado em versões anteriores do Adobe Campaign. Esse conector ainda é compatível com as implementações existentes, mas a Adobe recomenda que você atualize para a versão v8.9.1 ou posterior para se beneficiar do desempenho e da confiabilidade aprimorados do conector v2.

Para saber como se beneficiar do conector v2, consulte a seção [Ativação](#activation).

Para obter informações detalhadas sobre a configuração e o uso do conector SMS herdado, consulte a [documentação do Campaign Classic](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Conector SMS v2 {#sms-connector-v2}

Disponível no GA a partir da v8.9.1, o conector v2 habilita conexões SMPP no modo transceptor, conexões SMPP persistentes e garante melhor compatibilidade. Uma conta externa de SMS dedicada está disponível para todas as implementações de SMS usando o conector v2.

O conector v2 é ativado por padrão para novas instalações. Se você atualizou de uma versão anterior usando o conector herdado, é necessário entrar em contato com o representante da Adobe para alternar para o conector v2. Consulte a seção [Ativação](#activation).

Para saber como usar o conector SMS v2 no Campaign v8, consulte a [documentação de SMS](sms.md).

>[!NOTE]
>
>O conector v2 também está disponível nas seguintes builds com algumas restrições:
>* 8.8.1: versão para todos os ambientes FDA do Campaign. Não disponível para implantações do FFDA do Campaign.
>* 8.8.2: versão para todos os tipos de implantação, incluindo FFDA. Lançado em disponibilidade limitada (DL).

## Ativação {#activation}

### Por que alternar para o conector v2 {#why-switch-v2}

O processo SMS dedicado apresenta suporte para o modo transceptor SMPP, reduzindo a contagem de conexões e melhorando a eficiência dos recursos, enquanto ainda oferece suporte às configurações de transmissor/receptor, se necessário. Ele oferece estabilidade significativamente maior, com recuperação mais rápida de erros, conexões persistentes e sem dependência de arquivos locais ou comunicação entre processos. O desempenho também é aprimorado, com latência mais baixa, throughput mais alta e microlotes inteligentes para equilibrar a velocidade e a confiabilidade. Além disso, o isolamento do processo de SMS simplifica a solução de problemas e minimiza o impacto entre canais. Esses aprimoramentos tornam o conector dedicado uma solução mais robusta e escalável para entrega de SMS.

### Configuração {#configuration}

Com o Adobe Campaign Managed Cloud Services, a configuração do servidor e a migração do conector SMS são gerenciadas pelo Adobe. Este procedimento técnico requer acesso direto aos arquivos de configuração do servidor e às operações do banco de dados.

Para ativar e começar a usar o conector SMS v2, primeiro é necessário atualizar para a v8.9.1 ou posterior. Entre em contato com seu representante da Adobe ou com o Atendimento ao cliente da Adobe. Eles agendarão e executarão as atualizações necessárias para sua instância.