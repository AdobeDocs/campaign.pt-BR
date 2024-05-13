---
title: Alterar fonte de dados
description: Saiba mais sobre a atividade de Alteração da fonte de dados
feature: Workflows, Data Management, Federated Data Access
role: User
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 5af8753e9412c239ba40997abc5f8e61f405e999
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 17%

---

# Alterar fonte de dados {#change-data-source}

Use o **[!UICONTROL Change data source]** atividade para alterar a fonte de dados de uma [tabela de trabalho do workflow](use-workflow-data.md#workflow-temporary-work-table). Essa atividade oferece mais flexibilidade para gerenciar dados em diferentes fontes de dados, como o Federated Data Access (FDA), o banco de dados da Campaign Cloud (FFDA) e o banco de dados local do Campaign.

O fluxo de trabalho **[!UICONTROL Working table]** é usado para manipular e compartilhar dados com as atividades do workflow.

Por padrão, a variável **[!UICONTROL Working table]** é criado no mesmo banco de dados da fonte de dados que você precisa consultar.
Por exemplo, ao consultar a variável **[!UICONTROL Recipients]** armazenada no banco de dados em nuvem, o workflow cria um **[!UICONTROL Working table]** no mesmo banco de dados em nuvem.

Use um **[!UICONTROL Change Data Source]** atividade para usar uma fonte de dados diferente para sua **[!UICONTROL Working table]**.

Observe que ao usar o **[!UICONTROL Change Data Source]** atividade, é necessário alternar de volta para o banco de dados em nuvem para continuar a execução do workflow.

>[!IMPORTANT]
>
>Observe que a variável **[!UICONTROL Change Dimension]** e **[!UICONTROL Change Data source]** as atividades não devem ser adicionadas em uma linha. Se precisar usar ambas as atividades consecutivamente, inclua uma **[!UICONTROOL Enriquecimento]** atividade entre eles. Isso garante a execução adequada e evita possíveis conflitos ou erros.

Para usar o **[!UICONTROL Change Data Source]** atividade, você deve:

1. Criar um workflow.

1. Consulte seus destinatários alvos com uma atividade de **[!UICONTROL Query]**.

   Para mais informações sobre a atividade **[!UICONTROL Query]**, consulte esta [página](query.md#create-a-query).

1. Adicionar um **[!UICONTROL Change data source]** atividade.

   ![](assets/change-data-source.png)

1. Editar seu **[!UICONTROL Change data source]** atividade a ser selecionada **[!UICONTROL Default data source]**.

   A tabela de trabalho, que contém o resultado do query, é então movida para o banco de dados local padrão do Campaign.

   ![](assets/change-data-source_2.png)

1. Adicionar um **[!UICONTROL JavaScript code]** atividade para executar operações unitárias na tabela de trabalho.

   Para obter mais informações sobre o **[!UICONTROL JavaScript code]** consulte a seção [esta página](sql-code-and-javascript-code.md#javascript-code).

1. Adicione outra atividade **[!UICONTROL Change data source]** para alternar de volta para o banco de dados em nuvem.

1. Editar esta atividade e selecionar **[!UICONTROL Active FDA external account]** e as correspondentes **[!UICONTROL External database]** conta externa.

   ![](assets/change-data-source_3.png)

1. Agora, você pode iniciar o seu workflow.
