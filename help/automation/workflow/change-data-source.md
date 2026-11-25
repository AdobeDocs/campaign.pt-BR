---
title: Alterar fonte de dados
description: Saiba mais sobre a atividade de Alteração da fonte de dados
feature: Workflows, Data Management, Federated Data Access
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
TQID: 'https://experienceleague.adobe.com/jpyolWAkavJVJeUJzIP9-vHt17Z20oGKZ6sG99ahQE0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ee3dfd63-9a21-4961-9f24-ea3385284a21
    internal-label: Federated Data Access
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 14%
---
# Alterar fonte de dados {#change-data-source}

Use a atividade **[!UICONTROL Change data source]** para alterar a fonte de dados de uma [tabela de trabalho do fluxo de trabalho](use-workflow-data.md#work-table). Essa atividade oferece mais flexibilidade para gerenciar dados em diferentes fontes de dados, como o Federated Data Access (FDA), o banco de dados da Campaign Cloud (FFDA) e o banco de dados local do Campaign.

O fluxo de trabalho **[!UICONTROL Working table]** é usado para manipular e compartilhar dados com as atividades do fluxo de trabalho.

Por padrão, o **[!UICONTROL Working table]** é criado no mesmo banco de dados da fonte de dados que você precisa consultar.
Por exemplo, ao consultar a tabela **[!UICONTROL Recipients]**, armazenada no banco de dados em nuvem, o fluxo de trabalho cria um **[!UICONTROL Working table]** no mesmo banco de dados em nuvem.

Use uma atividade **[!UICONTROL Change Data Source]** para usar uma fonte de dados diferente para sua **[!UICONTROL Working table]**.

Observe que, ao usar a atividade **[!UICONTROL Change Data Source]**, é necessário alternar de volta para o banco de dados em nuvem para continuar a execução do fluxo de trabalho.

>[!IMPORTANT]
>
>Observe que as atividades **[!UICONTROL Change Dimension]** e **[!UICONTROL Change Data source]** não devem ser adicionadas em uma linha. Se você precisar usar ambas as atividades consecutivamente, certifique-se de incluir uma atividade **[!UICONTROL Enrichement]** entre elas. Isso garante a execução adequada e evita possíveis conflitos ou erros.

>[!NOTE]
>
>A atividade **Change Data Source** pode processar no máximo um milhão de registros por execução. Entre em contato com seu representante da Adobe se precisar aumentar esse limite.

Para usar a atividade **[!UICONTROL Change Data Source]**, você deve:

1. Criar um fluxo de trabalho.

1. Consulte seus destinatários alvos com uma atividade de **[!UICONTROL Query]**.

   Para mais informações sobre a atividade **[!UICONTROL Query]**, consulte esta [página](query.md#creating-a-query).

1. Adicione uma atividade **[!UICONTROL Change data source]**.

   ![Fluxo de trabalho com Início e Consulta, e atividade Change Data Source realçada na paleta](assets/change-data-source.png)

1. Edite sua atividade **[!UICONTROL Change data source]** para selecionar **[!UICONTROL Default data source]**.

   A tabela de trabalho, que contém o resultado do query, é então movida para o banco de dados local padrão do Campaign.

   ![Alterar atividade do Data Source com a opção Fonte de dados padrão selecionada](assets/change-data-source_2.png)

1. Adicione uma atividade **[!UICONTROL JavaScript code]** para executar operações unitárias na tabela de trabalho.

   Para obter mais informações sobre a atividade **[!UICONTROL JavaScript code]**, consulte o [código JavaScript e o código JavaScript avançado](sql-code-and-javascript-code.md#javascript-code).

1. Adicione outra atividade **[!UICONTROL Change data source]** para alternar de volta para o banco de dados em nuvem.

1. Edite esta atividade e selecione **[!UICONTROL Active FDA external account]** e a conta externa **[!UICONTROL External database]** correspondente.

   ![Alterar atividade do Data Source com a conta externa do Ative FDA selecionada e o Snowflake realçado na lista](assets/change-data-source_3.png)

1. Agora, você pode iniciar o seu fluxo de trabalho.
