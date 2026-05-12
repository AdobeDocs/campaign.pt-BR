---
product: campaign
title: Gerenciamento de conteúdo
description: Gerenciamento de conteúdo
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 9b225f78-1959-4e4f-aa4e-ff8a63051154
TQID: https://experienceleague.adobe.com/7owt-TM494cZq-Knz55qMpCAAtGhlpaKOlf2iXXeqo4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 472
ht-degree: 83%

---

# Gerenciamento de conteúdo{#content-management}

Uma atividade de **Gerenciamento de conteúdo** permite criar e manipular um conteúdo e gerar arquivos com base nesse conteúdo. Esse conteúdo pode ser entregue por meio de uma atividade de &#39;Delivery&#39;.

>[!CAUTION]
>
>O gerenciamento de conteúdo é um módulo opcional do Adobe Campaign. Verifique o contrato de licença.

>[!NOTE]
>
>A interface da Web do Adobe Campaign permite usar fragmentos de conteúdo para o seu conteúdo. Ele permite que os usuários de marketing pré-criem vários blocos de conteúdo personalizados, graças a componentes reutilizáveis que podem ser referenciados em uma ou mais mensagens, permitindo reunir rapidamente o conteúdo da mensagem em um processo de design aprimorado. Para saber mais sobre os fragmentos de conteúdo, consulte a [documentação da interface do usuário da Web do Adobe Campaign.](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments){target=_blank}

As propriedades da atividade são divididas em três etapas:

* **Seleção de conteúdo**: o conteúdo pode ter sido criado anteriormente ou pode ser criado através da atividade.
* **Atualização de conteúdo**: a tarefa pode modificar o assunto do conteúdo ou importar todo o conteúdo XML.
* **Ação**: o conteúdo resultante pode ser salvo ou gerado.

  ![](assets/content_mgmt_edit.png)

1. **Conteúdo**

   * **[!UICONTROL Specified in the transition]**

     Essa opção permite usar o conteúdo especificado na transição, ou seja, o evento que ativa o gerenciamento de conteúdo deve conter uma variável **[!UICONTROL contentId]**. Essa variável pode ter sido definida por uma gerenciamento de conteúdo anterior ou por qualquer script.

   * **[!UICONTROL Explicit]**

     Essa opção permite selecionar um conteúdo já criado, por meio do campo **[!UICONTROL Content]**. Este campo fica visível somente quando a opção **[!UICONTROL Explicit]** é selecionada.

     ![](assets/content_mgmt_explicit.png)

   * **[!UICONTROL Calculated by a script]**

     O identificador de conteúdo é calculado por um script. O campo **[!UICONTROL Script]** permite definir um modelo JavaScript avaliando o identificador (chave primária) do conteúdo. Este campo fica visível somente quando a opção **[!UICONTROL Calculated by a script]** é selecionada.

     ![](assets/content_mgmt_script.png)

   * **[!UICONTROL New, created from a publication template]**

     Cria um novo conteúdo a partir de um modelo de publicação. Esse novo conteúdo será salvo no arquivo especificado no campo **[!UICONTROL String]**. O campo **[!UICONTROL Template]** especifica o modelo de publicação a ser usado para criar o conteúdo.

     ![](assets/content_mgmt_new.png)

1. **Atualização de conteúdo**

   * **[!UICONTROL Subject]**

     Este campo permite modificar o assunto do conteúdo.

   * **[!UICONTROL Access to data from an XML feed]**

     Essa opção permite construir o conteúdo de um documento XML baixado por meio de uma folha de estilos XSL. Quando essa opção é selecionada, o campo **[!UICONTROL URL]** especifica a URL de download de conteúdo XML. A **[!UICONTROL XSL stylesheet]** permite que você especifique a folha de estilos a ser usada para transformar o documento XML baixado. Esse campo é opcional.

     ![](assets/content_mgmt_xmlcontent.png)

1. **Ação a ser executada**

   * **[!UICONTROL Save]**

     Essa opção salva o conteúdo criado ou modificado.

     A transição de saída é ativada apenas uma vez, com o conteúdo salvo na variável **[!UICONTROL contentId]** como um parâmetro.

   * **[!UICONTROL Generate]**

     Essa opção salva o conteúdo e gera os arquivos de output para cada modelo de transformação com uma publicação de tipo &#39;Arquivo&#39;.

     ![](assets/content_mgmt_generate.png)

     A transição de saída é ativada para cada arquivo gerado com o identificador do conteúdo salvo na variável **[!UICONTROL contentId]** como seu parâmetro e o nome do arquivo na variável **[!UICONTROL filename]**.

## Parâmetros de entrada {#input-parameters}

* contentId

Identificador do conteúdo a ser usado se a opção **[!UICONTROL Specified in the transition]** estiver habilitada.

## Parâmetros de saída {#output-parameters}

* contentId

  Identificador de conteúdo.

* filename

  Nome completo do arquivo gerado se a ação selecionada for **[!UICONTROL Generate]**.
