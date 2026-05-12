---
title: Trabalhar com o editor de consultas
description: Saiba como trabalhar com o editor de consultas
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 071274f1-7c60-445d-ac07-f5f4f229a489
TQID: https://experienceleague.adobe.com/lK6pRjnRXZQImlY7JjrUtvGSHpw-ohay8pBTTu2NH14
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 153
ht-degree: 81%

---

# Consultar banco de dados do Campaign

A ferramenta de consulta está disponível em vários níveis do aplicativo e pode ser usada para definir as populações do público-alvo, segmentar clientes, extrair e filtrar logs de rastreamento, criar filtros e muito mais.

Ela fornece um assistente dedicado, o editor de consulta genérica, acessível pelo menu **[!UICONTROL Tools > Generic query editor...]**. Esse editor permite que as consultas a banco de dados extraiam, organizem, agrupem e ordenem informações. Por exemplo, ele pode recuperar destinatários que clicaram mais de n vezes em um link de boletim informativo durante um determinado período.

O editor de query genérico centraliza todos os recursos de consulta. Ele permite criar e armazenar filtros de restrição, que podem ser reutilizados em outros contextos, como a caixa de consulta de um fluxo de trabalho de direcionamento.

![Acessar o editor de consultas e selecionar uma tabela](assets/query_editor_nveau_21.png)


As etapas para criar uma consulta estão detalhadas [nesta página](design-queries.md).

<!--
Contexts to use the query editor iin Campaign are listed below:

|Usage|Example|
|  ---  |  ---  |
|**Define a Query activity in a workflow**: Define the criteria to query Campaign database in a workflow. [Learn how to configure the Query activity](../../automation/workflow/query.md)|![Image showing how to configure a query activity in a workflow](../../automation/workflow/assets/query-activity.png){width="200" align="center" zoomable="yes"}|
|**Define audiences**: Specify the population you want to target in your messages, and effortlessly create new audiences tailored to your needs. [Learn how to build audiences](../start/create-message.md#define-the-target-audience)|![Image showing how to access the audience creation interface](../send/sms/assets/audience_to.png){width="200" align="center" zoomable="yes"}|
|**Define audiences**: Specify the population you want to target in your messages or workflows, and effortlessly create new audiences tailored to your needs. [Learn how to build audiences](../audiences/create-audiences.md)|![Image showing how to access the audience creation interface](../audiences/assets/targeting-wf-age-filter.png){width="200" align="center" zoomable="yes"}|
|**Customize workflow activities**: Apply rules within workflow activities, such as **Split** and **Reconciliation**, to align with your specific requirements. [Learn more about workflow activities](../../automation/workflow/activities.md)|![Image showing how to access workflow customization options](assets/access-workflow.png){width="200" align="center" zoomable="yes"}|
|**Predefined filters**: Create predefined filters that serve as shortcuts during various filtering operations, whether you're working with data lists or forming the audience for a delivery. [Learn how to work with predefined filters](../get-started/predefined-filters.md)|![Image showing how to access predefined filters](assets/access-predefined-filter.png){width="200" align="center" zoomable="yes"}|
|**Filter reports data**: Add rules to filter the data displayed in reports. [Learn how to work with reports](../reporting/gs-reports.md)|![Image showing how to filter data in reports](assets/access-reports.png){width="200" align="center" zoomable="yes"}|
|**Customize lists**: Create custom rules to filter the data displayed in lists such as recipients or deliveries lists. [Learn how to filter lists](../get-started/list-filters.md#list-built-in-filters)|![Image showing how to customize list filters](assets/access-lists.png){width="200" align="center" zoomable="yes"}|
|**Build conditional content**: Make email content dynamic by creating conditions that define which content should be displayed to different recipients, ensuring personalized and relevant messaging. [Learn how to build conditional content](../personalization/conditions.md)|![Image showing how to create conditional content](assets/conditional-content.png){width="200" align="center" zoomable="yes"}|
-->

**Tópicos relacionados**

* [Atividade de Consulta de Fluxo de Trabalho](../../automation/workflow/query.md)
* [Consultar a tabela de destinatários](../../automation/workflow/querying-recipient-table.md)
* [Condições de filtragem](filter-conditions.md)
