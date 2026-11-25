---
product: campaign
title: Ofertas em um canal de saída
description: Ofertas em um canal de saída
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 77fee343-09d1-4d60-be43-efe02953a70c
TQID: 'https://experienceleague.adobe.com/WGoYaHNR13J47UVmKpHRSm9aw0T8ZrvHUl9zGXezQBU'
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
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 54%
---
# Ofertas em um canal de saída{#offers-on-an-outbound-channel}



## Entrega da oferta de email {#email-offer-delivery}

Em nosso banco de dados, há uma categoria de ofertas de viagem para a África. A elegibilidade, os contextos e as representações de cada oferta foram configurados. Agora, queremos criar uma campanha para apresentar nossas ofertas por e-mail.

1. Crie uma campanha de marketing e o fluxo de trabalho de segmentação.

   ![Fluxo de trabalho de direcionamento da campanha Viagens para a África: atividades de pasta, entrega, desduplicação e duas atualizações de lista](assets/offer_delivery_example_001.png)

1. Edite a entrega do email e clique no ícone **[!UICONTROL Offers]**.

   ![Entrega de email com o ícone Ofertas abrindo a janela Gerenciamento de ofertas, opções de seleção de ofertas e campo Espaço de oferta](assets/offer_delivery_example_002.png)

1. Escolha o espaço de e-mail do ambiente de oferta que corresponda aos feriados.

   ![Janela de gerenciamento de ofertas com a lista Espaço de ofertas mostrando os espaços de email disponíveis, incluindo jornadas de Assinantes](assets/offer_delivery_example_003.png)

1. Escolha a categoria que contém as ofertas de viagem da África.

   ![Janela de gerenciamento de ofertas com a árvore Categoria expandida em Catálogo de ofertas e Jornadas, categoria África destacada](assets/offer_delivery_example_004.png)

1. Defina o número de ofertas na entrega para dois.

   ![Janela de gerenciamento de ofertas com categoria África e Número de propostas por mensagem definida como 2](assets/offer_delivery_example_005.png)

1. Feche a janela de gerenciamento de ofertas e crie o conteúdo de sua entrega.

   ![Editor de conteúdo do HTML de entrega de email com os modos de exibição de inclusão padrão, pronto para apresentações de oferta](assets/offer_delivery_example_006.png)

1. Use os menus para inserir uma apresentação de oferta e escolha a função de renderização HTML.

   ![Menu da barra de ferramentas Conteúdo do HTML: Proposições, depois Proposição 1, Função de renderização e Renderização do HTML](assets/offer_delivery_example_007.png)

1. Insira a segunda apresentação de oferta.

   ![O conteúdo do HTML de email com ambas as propostas inclui linhas que usam a exibição renderização/html, antes do link de cancelamento de assinatura](assets/offer_delivery_example_008.png)

1. Clique em **[!UICONTROL Preview]** para visualizar as ofertas na entrega e, em seguida, selecione um destinatário para visualizar as ofertas que eles receberão.

   ![Guia de Visualização de Entrega mostrando o email com o título, o texto e a imagem da oferta do Cruzamento do Saara para um destinatário selecionado](assets/offer_delivery_example_009.png)

1. Salve a entrega e inicie o fluxo de trabalho de segmentação.
1. Abra a entrega e clique na guia **[!UICONTROL Audit]** dele: é possível ver que o mecanismo de oferta selecionou as propostas a serem feitas dentre as várias ofertas do catálogo.

   ![Guia de Auditoria de Entrega - Registra as propostas geradas por oferta, como as ofertas das Pirâmides e do Saara](assets/offer_delivery_example_010.png)

## Executar uma simulação de oferta {#perform-an-offer-simulation}

1. Na guia **[!UICONTROL Profiles and Targets]**, clique no link **[!UICONTROL Simulations]** e depois clique no botão **[!UICONTROL Create]**.

   ![Lista de simulações com o botão Criar, abrindo a caixa de diálogo Nova simulação de oferta com modelo, rótulo e pasta](assets/offer_simulation_001.png)

1. Escolha um rótulo e especifique as configurações de execução, se necessário.

   ![Nova caixa de diálogo de simulação de oferta com os assinantes de rótulo de 1 ano, a pasta Simulações e as configurações de execução](assets/offer_simulation_example_002.png)

1. Salve a simulação. Isso abrirá em uma nova guia.

   ![Painel de simulação de assinantes de 1 ano com a guia Editar e um botão Iniciar simulação](assets/offer_simulation_example_003.png)

1. Clique na guia **[!UICONTROL Edit]** e depois em **[!UICONTROL Scope]**.

   ![Guia Edição de Simulação, seção Escopo, com Ambiente ou categoria, Espaço de oferta, Temas, Data de contato e propostas](assets/offer_simulation_example_004.png)

1. Escolha a categoria que deseja simular ofertas.

   ![Lista de ambientes ou categorias expandida em Ofertas - design e Catálogo de ofertas, com a categoria Viagem selecionada](assets/offer_simulation_example_005.png)

1. Escolha o espaço de oferta a ser usado para a simulação.

   ![Lista de espaço de ofertas na categoria Viagem oferecendo Mala Direta e Email (Ambiente - Destinatário)](assets/offer_simulation_example_006.png)

1. Insira as datas de validade. É necessário inserir pelo menos uma data inicial. Isso permite que o mecanismo de oferta ofereça e escolha aqueles que são válidos em uma determinada data.
1. Se necessário, especifique um ou vários temas para restringir o número de ofertas que contêm essa palavra-chave em suas configurações.

   No nosso exemplo, a categoria **Viagem** contém duas subcategorias com dois temas separados. Queremos executar uma simulação para ofertas com o tema **Customers>1 ano** .

   ![Seção de escopo com o cliente > 1 ano de tema inserido no campo Temas para a categoria Viagem](assets/offer_simulation_example_007.png)

1. Escolha os destinatários que deseja direcionar.

   ![Assistente de filtro de seleção de público alvo escolhendo Uma lista de destinatários e, em seguida, a lista de Frequent travelers](assets/offer_simulation_example_008.png)

1. Configure o número de ofertas a serem enviadas para cada destinatário.

   No nosso exemplo, o mecanismo de oferta escolherá as 3 ofertas com o peso mais alto para cada destinatário.

   ![Seção de escopo com número de apresentações definido como 3 e a consulta de destino na lista de entrega de ofertas especiais](assets/offer_simulation_example_009.png)

1. Salve as configurações e clique em **[!UICONTROL Start]**, na guia **[!UICONTROL Dashboard]**, para executar a simulação.

   ![Caixa de diálogo de simulação de Início do Painel solicitando confirmação, com o botão OK realçado](assets/offer_simulation_example_010.png)

1. Uma vez concluída a simulação, consulte os **[!UICONTROL Results]** para obter um detalhamento das propostas por oferta.

   No nosso exemplo, o mecanismo de oferta baseou o detalhamento da oferta em 3 propostas.

   ![Guia Resultados da Simulação com Detalhamento de propostas por ofertas: tamanho da população 30, número de propostas 30](assets/offer_simulation_example_011.png)

1. Exiba **[!UICONTROL Breakdown of offers by rank]** para visualizar a lista de ofertas selecionadas pelo mecanismo de oferta.

   ![Detalhamento de ofertas por relatório de classificação com tabela de classificação de ofertas para Viagem aos EUA e Descubra a França e um gráfico de pizza](assets/offer_simulation_example_012.png)

1. Se necessário, é possível alterar as configurações do escopo e executar a simulação novamente clicando em **[!UICONTROL Start simulation]**.

   ![Caixa de diálogo de simulação de Início do Painel solicitando confirmação, com o botão OK realçado](assets/offer_simulation_example_010.png)

1. Para salvar os dados da simulação, use o histórico ou as funções de exportação disponíveis no relatório.

   ![Detalhamento de ofertas por relatório de classificação com o menu Exportar e o ícone salvar destacados](assets/offer_simulation_example_013.png)
