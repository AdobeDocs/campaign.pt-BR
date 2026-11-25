---
product: campaign
title: Ofertas em um canal de entrada
description: Ofertas em um canal de entrada
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 90afced3-465d-4370-8a33-51a7e4356135
TQID: 'https://experienceleague.adobe.com/HkXtRV9hn2hZSZyxx86o2muGafhdhWuLp-uYBe4xTaU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '2986'
ht-degree: 68%
---
# Ofertas em um canal de entrada{#offers-on-an-inbound-channel}



## Apresentação de uma oferta a um visitante anônimo {#presenting-an-offer-to-an-anonymous-visitor}

O site Neobank deseja exibir uma oferta destinada aos visitantes não identificados que navegam na página.

Para configurar essa interação, nós vamos:

1. [Criar um ambiente anônimo](#creating-an-anonymous-environment)
1. [Criar espaços de oferta anônimos](#creating-anonymous-offer-spaces)
1. [Criar uma categoria de oferta e um tema](#creating-an-offer-category-and-a-theme)
1. [Criar ofertas anônimas.](#creating-anonymous-offers)
1. [Configurar os espaços de oferta da Web no site](#configure-the-web-offer-space-on-the-website)

### Criação de um ambiente anônimo {#creating-an-anonymous-environment}

Siga o procedimento detalhado em [Criar um ambiente de oferta](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/offers/interaction-settings/interaction-env#create-an-offer-environment){target="_blank"} (documentação do Campaign v8) para criar seu ambiente anônimo com base nas dimensões de **visitantes**.

É possível obter uma estrutura de árvore contendo o novo ambiente:

![Árvore de design de ofertas e Ambiente - Propriedades dos visitantes, um ambiente para interações anônimas recebidas](assets/offer_env_anonymous_003.png)

### Criação de espaços de oferta anônimos {#creating-anonymous-offer-spaces}

1. No ambiente anônimo (**Visitors**), acesse o nó **[!UICONTROL Administration]** > **[!UICONTROL Spaces]**.
1. Clique em **[!UICONTROL New]** para criar um canal de chamada.

   ![Botão Novo na lista Espaços de oferta abrindo a caixa de diálogo Novo espaço de oferta com a guia Propriedades](assets/offer_inbound_anonymous_example_010.png)

   >[!NOTE]
   >
   >O espaço é automaticamente vinculado ao ambiente anônimo.

1. Altere o rótulo e selecione o canal **[!UICONTROL Inbound Web]**. Também é necessário marcar a caixa **[!UICONTROL Enable unitary mode]**.

   ![Caixa de diálogo Espaço de ofertas com o rótulo Oferta Anônima da Web Premium e o canal de Entrada da Web selecionado](assets/offer_inbound_anonymous_example_006.png)

1. Selecione os campos de conteúdo da oferta usados para o espaço e especifique-os através da marcação da caixa relevante.

   Dessa forma, qualquer oferta que não tenha um dos seguintes elementos não será elegível para este espaço:

   * Título
   * Conteúdo HTML
   * URL da imagem,
   * URL de destino

   ![Selecione uma caixa de diálogo de expressão com o campo Título escolhido como um campo de conteúdo de oferta do espaço de oferta](assets/offer_inbound_anonymous_example_030.png)

1. Edite a função de renderização HTML, por exemplo:

   ```javascript
   function (imageUrl, targetUrl, shortContent, htmlSource){
         var html = "<p><b>" + shortContent + "</b></p>";
         html += "<p>" + htmlSource + "</p>";
         html += "<a _urlType='11' href='" + targetUrl + "'><img src='" + encodeURI(imageUrl) + "'/></a>";
         return html;
       }   
   ```

   >[!IMPORTANT]
   >
   >A função de renderização deve nomear os campos usados para o espaço na ordem em que foram selecionados anteriormente, assim as ofertas são exibidas corretamente.

   ![Link para editar funções, abrindo a guia de renderização do HTML do espaço de ofertas para sobrecarregar a função de renderização](assets/offer_inbound_anonymous_example_031.png)

1. Salve o espaço de oferta.

### Criação de uma categoria de oferta e um tema {#creating-an-offer-category-and-a-theme}

1. Acesse o nó **[!UICONTROL Offer catalog]** no ambiente criado anteriormente.
1. Clique com o botão direito do mouse no nó **[!UICONTROL Offer catalog]** e selecione **[!UICONTROL Create a new 'Offer category' folder]**.

   Nomeie a nova categoria, **Financial products** por exemplo.

1. Acesse a guia da categoria **[!UICONTROL Eligibility]**, insira **financing** como um tema e, em seguida, salve as alterações.

   ![Guia Qualificação da categoria de oferta com o campo Temas definido como financiamento](assets/offer_inbound_anonymous_example_023.png)

### Criação de ofertas anônimas {#creating-anonymous-offers}

1. Acesse a categoria recém-criada.
1. Clique em **[!UICONTROL New]**.

   ![Botão Novo na lista de ofertas da categoria Produtos financeiros, abrindo a caixa de diálogo Nova oferta](assets/offer_inbound_anonymous_example_013.png)

1. Selecione o modelo de oferta anônimo pronto para uso ou um modelo criado anteriormente.

   ![Lista de modelos de oferta com Nova oferta anônima (emptyAnonOffer) e Nova oferta (emptyOfferVisitor)](assets/offer_inbound_anonymous_example_014.png)

1. Altere o rótulo e salve a oferta.

   ![Caixa de diálogo Nova oferta anônima com o rótulo Oferta Anônima Premium #1 antes de salvar](assets/offer_inbound_anonymous_example_015.png)

1. Acesse a guia **[!UICONTROL Eligibility]** e especifique o peso das ofertas de acordo com os contextos de aplicação.

   Neste exemplo, a oferta é configurada para ser exibida na home page do site como prioridade até o fim do ano.

   ![Guia Elegibilidade da Oferta com pesos da oferta e a caixa de diálogo Peso limitada ao espaço de ofertas anônimo](assets/offer_inbound_anonymous_example_016.png)

1. Acesse a guia **[!UICONTROL Content]** e defina o conteúdo da oferta.

   >[!NOTE]
   >
   >É possível selecionar as **[!UICONTROL Content definitions]** para exibir a lista de elementos necessários ao espaço da Web.

   ![Guia Conteúdo da Oferta com título, URL de destino, URL da imagem e conteúdo do HTML para a primeira oferta anônima](assets/offer_inbound_anonymous_example_017.png)

1. Crie uma segunda oferta.

   ![Guia Conteúdo da segunda oferta anônima com título, URL de destino e conteúdo do HTML](assets/offer_inbound_anonymous_example_018.png)

1. Vá para a guia **[!UICONTROL Eligibility]** e aplique o mesmo peso da primeira oferta.
1. Execute o ciclo de aprovação de cada oferta para criá-las, bem como seus espaços de ofertas aprovados, disponíveis no ambiente online.

### Configurar o espaço de ofertas no site {#configure-the-web-offer-space-on-the-website}

Para que as ofertas recém-configuradas fiquem visíveis no site, insira o código JavaScript na página HTML do site para chamar o mecanismo do Interaction (para obter mais informações, consulte [Sobre canais de entrada](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/offers/inbound/interaction-present-offers){target="_blank"} (documentação do Campaign v8)).

1. Vá para a página HTML e insira um atributo @id com um valor correspondente ao nome interno do espaço de ofertas anônimo criado anteriormente (consulte [Criar espaços de oferta anônimos](#creating-anonymous-offer-spaces)), precedido por **i_**.

   ![Origem da página do HTML com uma div cuja id é i_SPC3, o nome interno do espaço de oferta precedido por i_](assets/offer_inbound_anonymous_example_019.png)

1. Insira a URL de chamada.

   ![Chamada de script do HTML para interactionProposal.js com os parâmetros env=liveVisitor e th=financing realçados](assets/offer_inbound_anonymous_example_020.png)

   As caixas azuis de URL acima correspondem ao nome da instância, ao nome interno do ambiente (consulte [Criação de um ambiente anônimo](#creating-an-anonymous-environment)) e ao tema vinculado à categoria ([Criação de uma categoria de oferta e um tema](#creating-an-offer-category-and-a-theme)). O último é opcional.

Quando um visitante acessa a home page do site, as ofertas com o tema de **financiamento** são exibidas como configuradas na página HTML.

![Página inicial do Neobank com o bloco de ofertas especiais exibindo uma oferta anônima na barra lateral](assets/offer_inbound_anonymous_example_022.png)

Um usuário que visita a página várias vezes verá uma ou as outras ofertas na categoria desde que ambas tenham sido atribuídas a ele.

## Alternância para um ambiente anônimo no caso de contatos não identificados {#switching-to-an-anonymous-environment-in-case-of-unidentified-contacts}

A empresa Neobank gostaria de criar ofertas de marketing para dois targets diferentes. Ela quer exibir ofertas genéricas para navegadores anônimos de sites. Se um desses usuários for um cliente com identificadores fornecidos pela Neobank, a empresa gostaria de receber ofertas personalizadas assim que efetuarem logon.

Esse estudo de caso se baseia no seguinte cenário:

1. Um visitante navega no site da Neobank sem fazer logon.

   ![Página inicial do Neobank com o painel de logon exibido para um visitante que não está conectado](assets/offer_inbound_fallback_example_050.png)

   Três ofertas anônimas são exibidas na página: duas **Melhores Ofertas** de produtos Neobank e uma oferta de um parceiro Neobank.

   ![Página Neobank com três ofertas anônimas: duas Melhores Ofertas e uma Oferta de parceiro](assets/offer_inbound_fallback_example_051.png)

1. O usuário, um cliente do Neobank, faz logon com suas credenciais.

   ![Painel de logon Neobank com credenciais inseridas antes do logon do usuário](assets/offer_inbound_fallback_example_052.png)

   São exibidas três ofertas personalizadas.

   ![Página Neobank após logon com três ofertas personalizadas destacadas no bloco de ofertas especiais](assets/offer_inbound_fallback_example_053.png)

Para implementar esse estudo de caso, você precisa ter dois ambientes de ofertas: um para interações anônimas e um com ofertas configuradas especialmente para contatos identificados. O ambiente de oferta identificado será configurado para alternar para o ambiente de oferta anônima automaticamente se o contato não estiver conectado e, portanto, não for identificado.

Siga as etapas abaixo:

* Crie um catálogo de ofertas específico para interações de entrada anônimas ao seguir as etapas:

  1. [Criação de um ambiente para contatos anônimos](#creating-an-environment-for-anonymous-contacts)
  1. [Configuração de espaços de ofertas para o ambiente anônimo](#configuring-offer-spaces-for-the-anonymous-environment)
  1. [Criação de categorias de ofertas em um ambiente anônimo](#creating-offer-categories-in-an-anonymous-environment)
  1. [Criação de ofertas para visitantes anônimos](#creating-offers-for-anonymous-visitors)

* Crie um catálogo de ofertas específico para interações de entrada identificadas executando as seguintes etapas:

  1. [Configure os espaços de oferta no ambiente identificado](#configure-the-offer-spaces-in-the-identified-environment)
  1. [Criação de categorias de ofertas em um ambiente identificado](#creating-offer-categories-in-an-identified-environment)
  1. [Criação de ofertas personalizadas](#creating-personalized-offers)

* Configure a chamada para o motor de oferta:

  1. [Configuração de espaços de ofertas na página da Web](#configuring-offer-spaces-on-the-web-page)
  1. [Especificação das configurações avançadas dos espaços de ofertas identificados](#specifying-the-advanced-settings-of-the-identified-offer-spaces)

### Criação de um ambiente para contatos anônimos {#creating-an-environment-for-anonymous-contacts}

1. Crie um ambiente de oferta para interações de entrada anônimas por meio do assistente de mapeamento de entregas (mapeamento de **Visitantes**). Para obter mais informações sobre isso, consulte [Criar um ambiente de ofertas](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/offers/interaction-settings/interaction-env#create-an-offer-environment){target="_blank"} (documentação do Campaign v8).

   ![Árvore de design de ofertas e Ambiente - Propriedades dos visitantes, um ambiente para interações anônimas recebidas](assets/offer_env_anonymous_003.png)

### Configuração de espaços de ofertas para o ambiente anônimo {#configuring-offer-spaces-for-the-anonymous-environment}

As ofertas que devem ser apresentadas no site pertencem a duas categorias diferentes: **Best Offer** e **Partner**. Nesse exemplo, vamos criar um espaço de ofertas específico para cada categoria.

Para criar o espaço de ofertas para corresponder à categoria **Melhor Oferta** , realize o seguinte processo:

1. Na árvore do Adobe Campaign, vá para o ambiente anônimo recém-criado e adicione um espaço de ofertas.

   ![Lista de espaços de oferta no Ambiente - Ambiente de design de visitantes, com o botão Novo realçado](assets/offer_inbound_fallback_example_023.png)

1. Crie um novo espaço do tipo **[!UICONTROL Inbound web]**.

   ![Menu suspenso Canal de novo espaço de ofertas com Web de entrada selecionada](assets/offer_inbound_fallback_example_024.png)

1. Digite um rótulo para ele: **Web Best Anonymous Offer**, por exemplo.
1. Adicione os campos de conteúdo de oferta usados para esse espaço de ofertas e configure as funções de renderização.

   ![Melhor Oferta Anônima da Web para o Espaço de Ofertas com canal da Web de entrada, campos de conteúdo e função de renderização do HTML](assets/offer_inbound_fallback_example_025.png)

   >[!IMPORTANT]
   >
   >A função de renderização deve nomear os campos usados para o espaço na ordem em que foram selecionados anteriormente, assim as ofertas são exibidas corretamente.

1. Use o mesmo processo para criar um espaço de oferta de canal da web de entrada para corresponder à categoria **Parceiro** .

   ![Parceiro da Web do Espaço de ofertas anônimo com canal da Web de entrada, conteúdo do HTML e campos de URL de imagem](assets/offer_inbound_fallback_example_026.png)

### Criação de categorias de ofertas em um ambiente anônimo {#creating-offer-categories-in-an-anonymous-environment}

Comece criando duas categorias de ofertas: categoria **Melhor Oferta** e categoria **Parceiro.** Cada categoria terá duas ofertas para contatos anônimos.

1. Vá para o **[!UICONTROL Offer catalog]** no ambiente anônimo recém-criado.
1. Adicione uma pasta de **[!UICONTROL Offer category]** com **Best Offer** como o rótulo.

   ![Pasta de categoria de oferta rotulada como Melhor Oferta em Ambiente - Visitantes na árvore de design](assets/offer_inbound_fallback_example_027.png)

1. Crie uma segunda categoria com **Parceiro** como um rótulo.

   ![Categoria de oferta Parceiro criado ao lado de Melhor Oferta em Ambiente - Visitante](assets/offer_inbound_fallback_example_028.png)

### Criação de ofertas para visitantes anônimos {#creating-offers-for-anonymous-visitors}

Agora vamos criar duas ofertas em cada uma das categorias criadas acima.

1. Vá para a categoria **Melhor Oferta** e crie uma oferta anônima.

   ![Caixa de diálogo Nova oferta anônima na categoria Melhor Oferta com o rótulo Melhor oferta #1](assets/offer_inbound_fallback_example_029.png)

1. Acesse a guia **[!UICONTROL Eligibility]** e especifique o peso das ofertas de acordo com os contextos de aplicação.

   ![Guia de qualificação da oferta anônima Best offer #1 com pesos para Página Inicial e Salvando página](assets/offer_inbound_fallback_example_030.png)

1. Acesse a guia **[!UICONTROL Content]** e defina o conteúdo da oferta.

   ![Guia Conteúdo de uma Best Offer anônima com o título Conta Bancária Neobank e conteúdo do HTML](assets/offer_inbound_fallback_example_032.png)

1. Crie uma segunda oferta na categoria **Melhor Oferta**.

   ![Guia Conteúdo da segunda Melhor Oferta com o título Neobank Home Insurance e conteúdo do HTML](assets/offer_inbound_fallback_example_031.png)

1. Vá para a categoria **Parceiro** e crie uma oferta anônima.
1. Acesse a guia **[!UICONTROL Content]** e defina o conteúdo da oferta.

   ![Guia Conteúdo da oferta anônima de parceiro com título Neo Weekly e conteúdo HTML](assets/offer_inbound_fallback_example_033.png)

1. Acesse a guia **[!UICONTROL Eligibility]** e especifique o peso das ofertas de acordo com os contextos de aplicação.

   ![Guia de qualificação da oferta de mídia de Parceiro anônima com um peso de 3 para a Página inicial](assets/offer_inbound_fallback_example_034.png)

1. Crie uma segunda oferta para a categoria **Partner**.

   ![Guia Conteúdo da segunda oferta anônima de parceiro com título Excursion e conteúdo HTML](assets/offer_inbound_fallback_example_035.png)

1. Vá para a guia **[!UICONTROL Eligibility]** e aplique o mesmo peso aplicado à primeira oferta desta categoria para que as ofertas sejam exibidas sucessivamente no site.

   ![Guia de qualificação da segunda oferta de parceiro com peso de 3 para Página inicial, igual ao primeiro](assets/offer_inbound_fallback_example_036.png)

1. Execute o ciclo de aprovação em cada oferta para ativá-las. Ao aprovar o conteúdo, ative o espaço de ofertas **Parceiro** ou **Melhor Oferta**, de acordo com a oferta.

### Configurar os espaços de oferta no ambiente identificado {#configure-the-offer-spaces-in-the-identified-environment}

As ofertas que você vai apresentar no site são obtidas de duas categorias diferentes: **Best Offer** e **Partner**. Neste exemplo, queremos criar um espaço específico para cada delivery.

Para criar os dois espaços de oferta, realize o mesmo procedimento dos espaços de oferta anônimos. Consulte [Configuração de espaços de ofertas para o ambiente anônimo](#configuring-offer-spaces-for-the-anonymous-environment).

1. Na árvore do Adobe Campaign, vá para o ambiente recém-criado e adicione os espaços de ofertas **Melhor Oferta** e **Parceiro**.
1. Aplique o processo detalhado em [Configurar espaços de oferta para o ambiente anônimo](#configuring-offer-spaces-for-the-anonymous-environment).

   ![Lista de espaços de oferta do Ambiente - Ambiente de design de destinatários, com o espaço Identificado do Parceiro da Web aberto](assets/offer_inbound_fallback_example_005.png)

1. Selecione a opção **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]**.

   ![Retorne a um ambiente anônimo se nenhuma opção foi identificada selecionada no espaço de oferta](assets/offer_inbound_fallback_example_006.png)

1. Usando a lista suspensa, selecione o espaço de ofertas da Web anônimo criado anteriormente (consulte [Configuração de espaços de ofertas para o ambiente anônimo](#configuring-offer-spaces-for-the-anonymous-environment)).

   ![Lista suspensa de espaços de ofertas anônimos para o espaço anônimo vinculado, com a opção Parceiro Web Anônimo selecionada](assets/offer_inbound_fallback_example_007.png)

### Especificação das configurações avançadas dos espaços de ofertas identificados {#specifying-the-advanced-settings-of-the-identified-offer-spaces}

Neste exemplo, a identificação de contato ocorre graças ao endereço de email no banco de dados do Adobe Campaign. Para adicionar o email do destinatário ao espaço, siga o seguinte processo:

1. No ambiente identificado, vá para a pasta de espaço de ofertas.
1. Selecione o espaço de ofertas **Best Offer** e clique em **[!UICONTROL Advanced parameters]**.

   ![Espaço Identificado da Web Best Offer com o link Advanced parameters abrindo a guia de identificação Target](assets/offer_inbound_fallback_example_044.png)

1. Na guia **[!UICONTROL Target identification]**, clique em **[!UICONTROL Add]**.

   ![Guia de identificação de Target de parâmetros avançados com o botão Adicionar para um caminho de chave](assets/offer_inbound_fallback_example_046.png)

1. Clique em **[!UICONTROL Edit expression]**, vá para a tabela de destinatários e selecione o campo **[!UICONTROL Email]**.

   ![Editar seletor de campo de expressão na tabela de destinatários com o campo Email selecionado](assets/offer_inbound_fallback_example_047.png)

1. Clique em **[!UICONTROL OK]** para fechar a janela **[!UICONTROL Advanced parameters]** e finalizar a configuração do espaço de ofertas **Best Offer**.
1. Siga o mesmo processo para o espaço de ofertas do **Parceiro**.

   ![Parceiro da Web Identificou espaço com o caminho de chave @email definido na guia de identificação de Target de parâmetros avançados](assets/offer_inbound_fallback_example_048.png)

### Criação de categorias de ofertas em um ambiente identificado {#creating-offer-categories-in-an-identified-environment}

Vamos criar duas categorias separadas: a categoria **Melhor oferta** e a categoria **Parceiro**, cada uma com duas ofertas personalizadas.

1. Vá para o nó **[!UICONTROL Offer catalogs]** no ambiente identificado.
1. Como no ambiente anônimo, adicione duas pastas **[!UICONTROL Offer category]** com **Melhor Oferta** e **Parceiro** como rótulos.

   ![Ambiente - Árvore de design de destinatário com as categorias Melhor Oferta e Parceiro, espelhando o ambiente de visitantes](assets/offer_inbound_fallback_example_009.png)

### Criação de ofertas personalizadas {#creating-personalized-offers}

Queremos criar duas ofertas personalizadas para cada categoria, ou seja, quatro ofertas.

1. Vá para a categoria **Melhor Oferta** e crie a primeira oferta personalizada.

   ![Caixa de diálogo Nova oferta na categoria Melhor Oferta identificada usando o modelo Nova oferta (emptyOffer), rótulo Melhor oferta #1](assets/offer_inbound_fallback_example_011.png)

1. Acesse a guia **[!UICONTROL Eligibility]** e especifique o peso das ofertas de acordo com os contextos de aplicação.

   ![Guia Qualificação da primeira Melhor Oferta identificada com pesos para a página inicial e a página Bancária do Neobank](assets/offer_inbound_fallback_example_012.png)

1. Acesse a guia **[!UICONTROL Content]** e defina o conteúdo da oferta.

   ![Guia Conteúdo da Melhor Oferta personalizada com o título Conta Bancária Neobank e uma oferta para clientes Neobank](assets/offer_inbound_fallback_example_013.png)

1. Crie uma segunda oferta na categoria **Melhor Oferta**.

   ![Guia Conteúdo da segunda Melhor Oferta personalizada, Neobank Home Insurance, com reembolso para clientes existentes](assets/offer_inbound_fallback_example_014.png)

1. Vá para a categoria **Parceiro** e crie uma oferta personalizada.

   ![Guia Conteúdo da oferta personalizada do Partner com título Excursion e um desconto de 20% para clientes Neobank](assets/offer_inbound_fallback_example_015.png)

1. Acesse a guia **[!UICONTROL Eligibility]** e especifique o peso das ofertas de acordo com os contextos de aplicação.

   ![Guia Qualificação da Oferta de Viagem de Parceiro com um peso de 5 para a página inicial do Neobank](assets/offer_inbound_fallback_example_016.png)

1. Crie uma segunda oferta para a categoria **Partner**.

   ![Guia Conteúdo da segunda oferta do Partner, Neo Weekly, com 50% de desconto para clientes Neobank](assets/offer_inbound_fallback_example_017.png)

1. Vá para a guia **[!UICONTROL Eligibility]** e aplique o mesmo peso aplicado à primeira oferta desta categoria para que as ofertas sejam exibidas sucessivamente no site.
1. Execute o ciclo de aprovação para cada oferta para começar a atualizá-las. Durante a aprovação do conteúdo, ative os espaços de ofertas **Parceiro** ou **Melhor Oferta**.

### Configuração de espaços de ofertas na página da Web {#configuring-offer-spaces-on-the-web-page}

O site da empresa Neobank tem três espaços para ofertas: dois para ofertas relacionadas ao banco da categoria **Melhor Oferta** e um para ofertas da categoria **Parceiro**.

![Página inicial do Neobank para um usuário conectado com dois quadros Melhores ofertas e um quadro Oferta de parceiro em Ofertas especiais](assets/offer_inbound_fallback_example_038.png)

Para configurar esses espaços de ofertas na página HTML do site, siga o seguinte processo:

1. No conteúdo da página HTML, insira três

   elementos com um atributo @id cujo valor permitirá que chamemos as ofertas nos vários espaços de oferta do site.

   ![Origem da página do HTML com divs ContBO1, ContBO2 e ContPtn definindo os três espaços de oferta](assets/offer_inbound_fallback_example_039.png)

1. Em seguida, insira o script para definir valores de atributo.

   ![Script que define interactionDivs para ContBO1, ContBO2 e ContPtn com seus espaços e categorias](assets/offer_inbound_fallback_example_040.png)

   Neste exemplo, **ContBO1** e **ContBO2** recebem o valor **OsWebBestOfferIdentified**, ou seja, o nome interno do espaço de ofertas **Melhor Oferta** criado anteriormente no ambiente identificado. Os valores **CatBestOffer** e **CatBestOfferAnonym** correspondem ao nome interno das categorias **Best Offer** para ambientes anônimos e identificados.

   ![Best Offer space OSWebBestOfferIdentified e as categorias Best Offer dos ambientes identificados e anônimos](assets/offer_inbound_fallback_example_041.png)

   Da mesma forma, **ContPtn** recebe o valor **OSWebPartnerIdentified**, que corresponde ao nome interno do espaço de oferta do **Partner** criado no ambiente identificado. **CatPartner** e **CatPartnerAnonym** correspondem ao nome interno das categorias **Partner** para ambientes anônimos e identificados.

   ![Os valores das categorias OSWebPartnerIdentified e CatPartner e CatPartnerAnonym no script](assets/offer_inbound_fallback_example_042.png)

1. Atribua as informações que permitirão identificar a pessoa que faz logon no site Neobank na variável **interactionTarget**.

   Variável ![interactionTarget definida para o email da pessoa que faz logon no script de página](assets/offer_inbound_fallback_example_043.png)

   A identificação da pessoa pode ser baseada em um cookie de navegador, um parâmetro de leitura na URL, e-mail ou identificador da pessoa. Se um campo da tabela de destinatários diferente da chave primária for usado, ele precisará ser definido nos parâmetros avançados do espaço (consulte [Especificar as configurações avançadas dos espaços de ofertas identificados](#specifying-the-advanced-settings-of-the-identified-offer-spaces)).

1. Insira a URL de chamada.

   ![Chamada de script para interactionProposal.js com env=EnvNeobankIdnRecip, o nome interno do ambiente identificado](assets/offer_inbound_fallback_example_049.png)

   A URL contém **EnvNeobankIdnRecip**, o nome interno do ambiente identificado.

Quando você abre a página da Web, o script permite chamar o mecanismo do Interaction para exibir o conteúdo de ofertas nos espaços relevantes da página da Web. Em uma única chamada ao servidor do Adobe Campaign, o mecanismo determina o ambiente, o espaço de oferta e as categorias a serem selecionadas.

Neste exemplo, o mecanismo reconhece o ambiente identificado (**EnvNeobankIdnRecip**). Identifica o espaço de oferta (**OSWebBestOfferIdentified**) e a categoria **Best Offer** (**CatBestOffer**) para os primeiros e segundo espaços de oferta na página da Web, bem como o espaço de oferta (**OSWebPartnerIdentified**) e a categoria **Partner** (**CatPartner**) para o terceiro espaço de oferta do site.

Se o mecanismo não puder identificar o destinatário, ele alternará para os espaços de oferta anônimos referenciados nos espaços de oferta identificados e em direção às categorias anônimas (**CatPartner** e **CatPartnerAnonym**) conforme especificado no script.
