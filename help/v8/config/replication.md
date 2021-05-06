---
solution: Campaign Classic
product: campaign
title: Workflows técnicos e replicação de dados
description: Workflows técnicos e replicação de dados
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: f1aed22d04bc0170b533bc088bb1a8e187b44dce
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 3%

---

# Workflows técnicos e replicação de dados

## Workflows técnicos 

O Adobe Campaign vem com um conjunto de fluxos de trabalho técnicos incorporados. Os workflows técnicos executam processos ou tarefas agendados regularmente no servidor.

Esses workflows executam operações de manutenção no banco de dados, aproveitam as informações de rastreamento nos logs do delivery, criam campanhas recorrentes e muito mais.

:seta_upper_right: A lista completa de workflows técnicos é detalhada em [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Além desses workflows técnicos, o Campaign v8 depende de workflows técnicos específicos para gerenciar [replicação de dados](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Esse workflow executa a replicação automática de tabelas incorporadas que precisam estar presentes no banco de dados local do Campaign (Postgres) e no banco de dados do Cloud ([!DNL Snowflake]). Ele é agendado para ser executado a cada hora, diariamente. Se o campo **lastModified** existir, a replicação ocorrerá de forma incremental, caso contrário, toda a tabela será replicada. A ordem das tabelas na matriz abaixo é a ordem usada pelo workflow de replicação.
* **[!UICONTROL Replicate Staging data]**
Esse workflow replica dados de preparo para chamadas unitárias. Ele é agendado para ser executado a cada hora, diariamente.
* **[!UICONTROL Deploy FFDA immediately]**\
   Esse workflow executa uma implantação imediata no banco de dados do Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Esse workflow replica os dados XS para uma determinada conta externa.

Esses workflows técnicos estão disponíveis no nó **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** do explorador do Campaign. **Eles não devem ser modificados.**

## Replicação de dados{#data-replication}

Algumas tabelas integradas são replicadas do banco de dados do Campaign para o [!DNL Snowflake] banco de dados do Cloud por meio de workflows dedicados descritos acima.

As políticas de replicação são baseadas no tamanho das tabelas. Algumas tabelas serão replicadas em tempo real, outras serão replicadas a cada hora. Algumas tabelas terão atualizações incrementais quando outras forem substituídas.

**Tópicos relacionados**

:seta_upper_right: Saiba como começar a usar workflows na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

:bulb: Acesse os períodos de retenção de dados em [nesta seção](../dev/datamodel-best-practices.md#data-retention)

