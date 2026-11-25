---
product: campaign
title: 'Casos de uso: criar visões gerais'
description: 'Casos de uso: criar visões gerais'
feature: Web Apps
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
exl-id: a1ac3aab-dc81-4533-9207-26d5dc5e1c88
TQID: 'https://experienceleague.adobe.com/Awmu1sag3l7qN8ocg-uzbfSooV-8Cyhtxya4zVlo8EY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 69%
---
# Casos de uso: criar páginas de visão geral{#use-cases-creating-overviews}



No exemplo a seguir, criaremos aplicativos tipo visão geral para exibir todas as aplicações web no banco de dados. Configure os seguintes elementos:

* um filtro na pasta (consulte [Adição de um filtro em uma pasta](#adding-a-filter-on-a-folder)),
* um botão para criar uma nova aplicação web (consulte [Adição de um botão para configurar uma nova aplicação web](#adding-a-button-to-configure-a-new-web-application)),
* exibição detalhada de cada entrada na lista (consulte [Adição de detalhes a uma lista](#adding-detail-to-a-list)),
* um filtro por ferramenta de edição de links (consulte [Criação de um filtro usando um editor de links](#creating-a-filter-using-a-link-editor)),
* um link de atualização (consulte [Criação de um link de atualização](#creating-a-refresh-link)).

![Página de visão geral do aplicativo Web com rótulos: filtro de pasta, botão Novo, filtro do editor de link, link de atualização, lista, detalhes.](assets/s_ncs_configuration_webapp_overview.png)

## Criação de um aplicativo Web de uma única página {#creating-a-single-page-web-application}

1. Crie uma aplicação web de uma única **[!UICONTROL Page]** e desabilite as transições de saída e faça a transição para a próxima página.

   ![Propriedades da página, guia Geral, com a opção Desabilitar próxima página selecionada e Habilitar transições de saída desmarcada.](assets/s_ncs_configuration_webapp_create.png)

1. Alterar o título da página.

   Esse título aparecerá no cabeçalho da visão geral e na visão geral da aplicação web.

1. Nas propriedades da aplicação web, modifique a renderização do seu aplicativo selecionando o modelo **[!UICONTROL Single-page Web application]**.

   ![Caixa de diálogo Propriedades, guia Renderização, com o modelo de aplicativo Web de página única selecionado na lista Modelo.](assets/s_ncs_configuration_webapp_rendering.png)

1. Abra a atividade **[!UICONTROL Page]** da sua aplicação web e abra uma lista (**[!UICONTROL Static element > List]**).
1. Na guia **[!UICONTROL Data]** da lista, selecione o tipo de documento **[!UICONTROL Web applications]** e as colunas de saída **[!UICONTROL Label]** , **[!UICONTROL Creation date]** e **[!UICONTROL Type of application]**.
1. Na subguia **[!UICONTROL Filter]**, crie o filtro a seguir, como mostrado abaixo, para exibir somente as aplicações web e excluir os modelos da visualização.

   ![Guia Listar Dados, subguia Filtro, com condições Modelo igual a Não e Chave primária diferente de 0.](assets/s_ncs_configuration_webapp_filter.png)

1. Feche a janela de configuração da página e clique em **[!UICONTROL Preview]**.

   A lista de aplicativos Web disponíveis em seu banco de dados é exibida.

   ![Guia Visualizar do aplicativo Web mostrando a lista de aplicativos Web por rótulo.](assets/s_ncs_configuration_webapp_preview.png)

## Adicionar um filtro a uma pasta {#adding-a-filter-on-a-folder}

Em uma visão geral, você pode optar por acessar dados dependendo de sua localização na árvore do Adobe Campaign. Este é um filtro em uma pasta. Aplique o seguinte processo para adicioná-lo à sua visão geral.

1. Coloque o cursor no nó **[!UICONTROL Page]** da aplicação web e adicione um elemento **[!UICONTROL Select folder]** (**[!UICONTROL Advanced controls > Select folder]**).
1. Na janela **[!UICONTROL Storage]** que aparece, clique em **[!UICONTROL Edit variables]**.
1. Altere o rótulo da variável para atender às suas necessidades.
1. Altere o nome da variável com o valor da **folder** .

   >[!NOTE]
   >
   >O nome da variável deve corresponder ao nome do elemento vinculado à pasta (definido no esquema), ou seja **folder**, neste caso. Você deve reutilizar esse nome quando fizer referência à tabela.

1. Aplique o tipo **[!UICONTROL XML]** à variável.

   ![Selecione a entrada da pasta com a opção Editar ramificações abertas e Editar ramificações mostrando a variável Pasta do tipo XML.](assets/s_ncs_configuration_webapp_variable_xml.png)

1. Selecione a interação **[!UICONTROL Refresh page]**.

   ![Entrada de pasta com a ação Atualizar página selecionada para a Ação a ser executada ao selecionar uma pasta.](assets/s_ncs_configuration_webapp_variable.png)

1. Coloque o cursor na lista e na guia **[!UICONTROL Advanced]**, faça referência à variável criada anteriormente na guia **[!UICONTROL Folder filter XPath]** da lista. É necessário usar o nome do elemento relacionado ao link da pasta, isto é **folder**.

   ![Guia Lista Avançada com o campo XPath Filtro de pasta definido como pasta em Armazenamento/Filtragem.](assets/s_ncs_configuration_webapp_variable002.png)

   >[!NOTE]
   >
   >Nesse estágio, a aplicação web não está dentro do contexto de aplicação; o filtro, portanto, não pode ser testado na pasta.

## Adicionar um botão para configurar um novo aplicativo Web {#adding-a-button-to-configure-a-new-web-application}

1. Coloque o cursor no elemento **[!UICONTROL Page]** e adicione um link (**[!UICONTROL Static elements > Link]**).
1. Modifique o rótulo do link já que ele aparecerá no botão da visão geral.

   No nosso exemplo, o rótulo é **New**.

1. Insira a seguinte URL no campo URL: **xtk://open/?schema=nms:webApp&amp;form=nms:newWebApp**.

   >[!NOTE]
   >
   >**nms:webApp** coincide com o esquema da aplicação web.
   >
   >**nms:newWebApp** coincide com o assistente de criação de novas aplicações web.

1. Escolha exibir a URL na mesma janela.
1. Adicione o ícone da aplicação web no campo de imagem: **/nms/img/webApp.png**.

   Esse ícone aparecerá no botão **[!UICONTROL New]**.

1. Digite **botão** no campo **[!UICONTROL Style]**.

   Esse estilo é mencionado no modelo **[!UICONTROL Single-page Web application]** selecionado anteriormente.

   ![Novo elemento de link com a URL que abre o novo formulário de aplicativo web e o campo Estilo definidos como botão.](assets/s_ncs_configuration_webapp_link.png)

## Adicionar detalhes a uma lista {#adding-detail-to-a-list}

Ao configurar uma lista na sua visão geral, você pode optar por exibir detalhes adicionais para cada entrada na lista.

1. Coloque o cursor no elemento de lista criado anteriormente.
1. Na guia **[!UICONTROL General]**, selecione o modo de exibição **[!UICONTROL Columns and additional detail]** na lista suspensa.

   ![Guia Geral de Lista com a opção Exibir definida como Colunas e Detalhes Adicionais.](assets/s_ncs_configuration_webapp_detail.png)

1. Na guia **[!UICONTROL Data]**, adicione as colunas **[!UICONTROL Primary key]** , **[!UICONTROL Internal name]** e **[!UICONTROL Description]** e selecione a opção **[!UICONTROL Hidden field]** para cada uma.

   ![Guia Listar Dados com as colunas de saída Chave Primária, Nome Interno e Descrição marcadas como Campo Oculto.](assets/s_ncs_configuration_webapp_detail002.png)

   Dessa forma, essas informações só serão visíveis nos detalhes de cada entrada.

1. Na guia **[!UICONTROL Additional detail]**, adicione o seguinte código:

   ```html
   <div class="detailBox">
     <div class="actionBox">
       <span class="action"><img src="/xtk/img/fileEdit.png"/><a title="Open" class="linkAction" href="xtk://open/?schema=nms:webApp&form=nms:webApp&pk=
       <%=webApp.id%>">Open...</a></span>
       <% 
       if( webApp.@appType == 1 ) { //survey
       %>
       <span class="action"><img src="/xtk/img/report.png"/><a target="_blank" title="Reports" class="linkAction" href="/xtk/report.jssp?_context=selection&
         _schema=nms:webApp&_selection=<%=webApp.@id%>
         &__sessiontoken=<%=document.controller.getSessionToken()%>">Reports</a></span>
       <% 
       } 
       %>
     </div>
     <div>
       Internal name: <%= webApp.@internalName %>
     </div>
     <%
     if( webApp.desc != "" )
     {
     %>
     <div>
       Description: <%= webApp.desc %>
     </div>
     <% 
     } 
     %>
   </div>
   ```

>[!NOTE]
>
>As bibliotecas JavaScript levam cinco minutos para ser atualizadas no servidor. Você pode reiniciar o servidor para evitar ter que aguardar por esse atraso.

## Filtragem e atualização da lista {#filtering-and-updating-the-list}

Nesta seção, você criará um filtro para exibir a visão geral de aplicações web criadas por um operador específico. Esse filtro é criado com um editor de link. Após selecionar um operador, atualize a lista para aplicar seu filtro; isto exige a criação de um link de atualização.

Esses dois elementos serão agrupados no mesmo container para ser agrupados graficamente na visão geral.

1. Posicione o cursor no elemento **[!UICONTROL Page]** e selecione **[!UICONTROL Container > Standard]**.
1. Defina o número de colunas como **2**, para que o editor de link e o link estejam próximos um do outro.

   ![Contêiner de filtro com o campo de estilo Aparência definido como dottedFilter e duas colunas.](assets/s_ncs_configuration_webapp_container.png)

   Para obter informações sobre layout de elemento, consulte [Introdução aos formulários web](about-web-forms.md).

1. Aplique **dotedFilter**.

   Esse estilo é mencionado no modelo **[!UICONTROL Single-page Web application]** selecionado anteriormente.

   ![Guia Geral de contêiner de filtro com o campo de estilo Aparência definido como dottedFilter.](assets/s_ncs_configuration_webapp_container002.png)

### Criação de um filtro usando um editor de links {#creating-a-filter-using-a-link-editor}

1. Coloque o cursor no container criado durante a etapa anterior e insira um editor de link no menu **[!UICONTROL Advanced controls]**.
1. Na janela de armazenamento que abre automaticamente, selecione a opção **[!UICONTROL Variables]**, em seguida, clique no link **[!UICONTROL Edit variables]** e crie uma variável XML para filtrar dados.

   ![Entrada do editor de links: edite o armazenamento, edite as variáveis e a caixa de diálogo Variável criando a variável var2 XML.](assets/s_ncs_configuration_webapp_variable003.png)

1. Modifique o rótulo.

   Ele aparecerá ao lado do campo **[!UICONTROL Filter]** na visão geral.

1. Escolha a tabela Operador como um esquema de aplicativo.

   ![Editor de links rotulado como Criado por, armazenando na variável var2, com o esquema de aplicativo Operador selecionado.](assets/s_ncs_configuration_webapp_linkeditor.png)

1. Coloque o cursor no elemento da lista e crie um filtro através da guia **[!UICONTROL Data > Filter]**:

   * **Expression:** Chave externa do link &quot;Created by&quot;
   * **Operador:** igual a
   * **Value:** Variáveis (variáveis)
   * **Taken into account if:** &#39;$(var2/@id)&#39;!=&#39;&#39;

   ![Listar condições de filtro, incluindo a chave Created by link igual a Variáveis, aplicada somente se a id var2 estiver definida.](assets/s_ncs_configuration_webapp_filter002.png)

>[!CAUTION]
>
>O usuário da aplicação web deve ser um operador identificado com os direitos apropriados do Adobe Campaign para acessar as informações. Esse tipo de configuração não funcionará para aplicações web anônimas.

### Criação de um link de atualização {#creating-a-refresh-link}

1. Coloque o cursor no container e insira um **[!UICONTROL Link]** no menu **[!UICONTROL Static elements]**.
1. Modifique o rótulo.
1. Selecione **[!UICONTROL Refresh data in a list]**.
1. Adicione a lista criada anteriormente.

   ![Atualizar link com os Dados de atualização em uma ação de lista e Lista 1 escolhidos em Listas para atualização.](assets/s_ncs_configuration_webapp_refreshlink.png)

1. Adicione o ícone de atualização no campo **[!UICONTROL Image]**: **/xtk/img/refresh.png**.
1. Usar as setas de organização por tipo reorganiza os vários elementos da aplicação web, conforme mostrado abaixo.

   ![Árvore de elementos de página com as setas de ordem de classificação realçadas para mover a Lista 1 abaixo do elemento Filtro.](assets/s_ncs_configuration_webapp_orderelements.png)

A aplicação web agora está configurada. É possível clicar na guia **[!UICONTROL Preview]** para pré-visualizá-la.

![Visualização do aplicativo Web concluído: filtro de pasta, Novo link, Criado por filtro, Atualizar link e lista.](assets/s_ncs_configuration_webapp_result.png)
