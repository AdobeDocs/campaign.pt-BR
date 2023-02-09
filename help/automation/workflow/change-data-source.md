---
title: Alterar fonte de dados
description: Saiba mais sobre a atividade de Alteração da fonte de dados
feature: Workflows, Data Management, Federated Data Access
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 21%

---

# Alterar fonte de dados {#change-data-source}

Use o **[!UICONTROL Change data source]** atividade para alterar a fonte de dados de um [tabela de trabalho do fluxo de trabalho](use-workflow-data.md#workflow-temporary-work-table). Essa atividade oferece mais flexibilidade para gerenciar dados em diferentes fontes de dados, como o Federated Data Access (FDA), o banco de dados do Campaign Cloud (FDA) e o banco de dados local do Campaign.

O fluxo de trabalho **[!UICONTROL Working table]** é usada para manipular e compartilhar dados com as atividades do workflow.

Por padrão, a variável **[!UICONTROL Working table]** é criado no mesmo banco de dados que a fonte dos dados que você precisa consultar.
Por exemplo, ao consultar o **[!UICONTROL Recipients]** , armazenado no banco de dados do Cloud, o workflow cria um **[!UICONTROL Working table]** no mesmo banco de dados do Cloud.

Use um **[!UICONTROL Change Data Source]** para usar uma fonte de dados diferente para sua **[!UICONTROL Working table]**.

Observe que ao usar a variável **[!UICONTROL Change Data Source]** , é necessário alternar de volta para o banco de dados do Cloud para continuar a execução do workflow.

Para usar o **[!UICONTROL Change Data Source]** atividade , é necessário:

1. Criar um workflow.

1. Consulte seus recipients alvos com uma atividade de **[!UICONTROL Query]**.

   Para mais informações sobre a atividade **[!UICONTROL Query]**, consulte esta [página](query.md#create-a-query).

1. Adicione um **[!UICONTROL Change data source]** atividade .

   ![](assets/change-data-source.png)

1. Edite as **[!UICONTROL Change data source]** atividade para selecionar **[!UICONTROL Default data source]**.

   A tabela de trabalho, que contém o resultado do query, é então movida para o banco de dados local padrão do Campaign.

   ![](assets/change-data-source_2.png)

1. Adicione um **[!UICONTROL JavaScript code]** para executar operações unitárias na tabela de trabalho.

   Para obter mais informações sobre o **[!UICONTROL JavaScript code]** , consulte a [esta página](sql-code-and-javascript-code.md#javascript-code).

1. Adicione outra atividade **[!UICONTROL Change data source]** para alternar de volta para o banco de dados em nuvem.

1. Editar esta atividade e selecionar **[!UICONTROL Active FDA external account]** e o correspondente **[!UICONTROL External database]** conta externa.

   ![](assets/change-data-source_3.png)

1. Agora, você pode iniciar o seu workflow.
