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
source-git-commit: 9efd6442336a62e627b0da4e17fa742f59f715f9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 2%

---

# Workflows técnicos e replicação de dados

## Workflows técnicos 

O Adobe Campaign vem com um conjunto de fluxos de trabalho técnicos incorporados. Os workflows técnicos executam processos ou tarefas agendados regularmente no servidor.

Esses workflows executam operações de manutenção no banco de dados, aproveitam as informações de rastreamento nos logs do delivery, criam campanhas recorrentes e muito mais.

:seta_upper_right: A lista completa de workflows técnicos é detalhada em [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Além desses workflows técnicos, o Campaign v8 depende de workflows técnicos específicos para gerenciar [replicação de dados](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Esse workflow executa a replicação automática de tabelas de referência que precisam estar presentes no banco de dados local do Campaign (Postgres) e no banco de dados do Cloud (Snowflake). Ele é agendado para ser executado a cada hora, diariamente. If 
**** lastModifiedfield existe, a replicação acontece de forma incremental, caso contrário, toda a tabela é replicada. A ordem das tabelas na matriz abaixo é a ordem usada pelo workflow de replicação.
* **[!UICONTROL Replicate Staging data]**
Esse workflow replica dados de preparo para chamadas unitárias. Ele é agendado para ser executado a cada hora, diariamente.
* **[!UICONTROL Deploy FFDA immediately]**\
   Esse workflow executa uma implantação imediata no banco de dados do Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Esse workflow replica os dados XS para uma determinada conta externa.

Esses workflows técnicos estão disponíveis no nó **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** do explorador do Campaign.

## Replicação de dados{#data-replication}

As tabelas são replicadas do banco de dados do Campaign para o banco de dados da Snowflake Cloud por meio de workflows dedicados descritos acima.

As políticas de replicação são baseadas no tamanho da tabela. Algumas tabelas serão replicadas. Algumas tabelas serão replicadas em tempo real, e outras serão replicadas a cada hora. Algumas tabelas terão atualizações incrementais quando outras forem substituídas.

**DEVEMOS LISTAR TODAS AS TABELAS?**

PARA VERIFICAR

**Tópicos relacionados**

:seta_upper_right: Saiba como começar a usar workflows na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

:bulb: Acesse os períodos de retenção de dados em [nesta seção](../dev/datamodel-best-practices.md#data-retention)
