---
product: campaign
title: Criar hipóteses
description: Saiba como criar hipóteses no Gestor de resposta do Campaign
feature: Campaigns
version: Campaign v8, Campaign Classic v7
audience: campaign
content-type: reference
topic-tags: response-manager
exl-id: e0b3bc9f-5e81-463f-a59e-cd972a47109b
TQID: 'https://experienceleague.adobe.com/FggklU5pqlhjpHlUpd6C2G3Cb0A0dsooRZo9iEya858'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: d72afaa0-c842-48c8-9a3c-51b7911edc1b
    internal-label: Response Management
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '1375'
ht-degree: 74%
---
# Criar hipóteses{#creating-hypotheses}



Há várias possibilidades para criar/vincular hipóteses a uma oferta de campanha ou entrega:

* Na pasta **[!UICONTROL Measurement hypotheses]**, criando uma nova hipótese com base em um modelo existente e vinculando-a a uma entrega existente.
* Através da guia **[!UICONTROL Edit]** > **[!UICONTROL Measurement]** em uma campanha.
* Com a opção **[!UICONTROL Measurement]** de uma entrega criado de uma campanha.

A hipótese só poderá ser calculada depois que a campanha de marketing tiver sido iniciada e os destinatários tiverem recebido a entrega. Se a hipótese for baseada em uma apresentação da oferta, a última necessidade deverá ser apresentada e ainda estar ativa. A oferta e a entrega são criados por meio da pasta **[!UICONTROL Measurement hypotheses]** e se baseiam em um modelo de hipótese. No entanto, é possível fazer referência a uma hipótese diretamente na entrega ou na campanha, antes que esta tenha início. Nesse caso, as hipóteses serão calculadas automaticamente no momento em que a campanha de marketing tiver início, com base nas configurações de execução. [Saiba mais](hypothesis-templates.md#hypothesis-template-execution-settings)

## Criar uma hipótese em tempo real em uma entrega {#creating-a-hypothesis-on-the-fly-on-a-delivery}

Para criar uma hipótese em uma entrega existente, aplique o seguinte processo:

>[!NOTE]
>
>Esta operação é possível somente para entregas pendentes.

1. Na árvore do Adobe Campaign, acesse **[!UICONTROL Campaign management > Measurement hypotheses]**.
1. Clique no botão **[!UICONTROL New]** ou clique com o botão direito na lista de hipóteses e selecione **[!UICONTROL New]** na lista suspensa.

   ![Lista de hipóteses de medida com o botão Novo e a caixa de diálogo Nova hipótese para escolher um modelo](assets/response_hypothesis_instance_creation_002.png)

1. Na janela da hipótese, selecione um modelo criado anteriormente. [Saiba mais](hypothesis-templates.md)

   ![Caixa de diálogo Nova hipótese com o menu suspenso Modelo de hipótese listando os modelos disponíveis](assets/response_hypothesis_instance_creation_003.png)

   É exibido na tela o contexto da hipótese como definido no template selecionado.

   >[!NOTE]
   >
   >As configurações definidas no modelo e invisíveis nesta etapa também são mantidas na memória e reatribuído à hipótese em andamento.

   ![Caixa de diálogo de nova hipótese mostrando a consulta herdada do modelo selecionado e do campo Entrega](assets/response_hypothesis_instance_creation_004.png)

1. Selecione a entrega para a qual deseja criar uma hipótese.

   ![Caixa de diálogo Nova hipótese com a lista suspensa Entrega listando entregas a serem selecionadas](assets/response_hypothesis_instance_creation_005.png)

1. É possível personalizar a hipótese editando as guias **[!UICONTROL General]**, **[!UICONTROL Transactions]** e **[!UICONTROL Scope]**. [Saiba mais](hypothesis-templates.md#creating-a-hypothesis-model)
1. Comece a hipótese clicando em **[!UICONTROL Start]**.

   Um fluxo de trabalho é criado automaticamente para executar a mensuração. O nome é definido automaticamente de acordo com a configuração da hipótese.

   >[!CAUTION]
   >
   >É possível acessar se a caixa **[!UICONTROL Keep execution workflow]** estiver marcada.\
   >Essa opção deve ser ativada somente para fins de depuração, caso ocorra um erro durante a execução da hipótese. Os fluxos de trabalho gerados automaticamente são salvos na pasta **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Objects created automatically]** > **[!UICONTROL Campaign workflows]** no explorer do Adobe Campaign.
   > 
   >Além disso, os fluxos de trabalho gerados automaticamente não devem ser modificados. Qualquer modificação eventual em outro lugar é desconsiderada para cálculos posteriores.
   >
   >Se essa opção está marcada, exclua o fluxo de trabalho após a execução.

   ![Botão Iniciar da lista de hipóteses de medição e o prompt de confirmação para iniciar a hipótese](assets/response_hypothesis_instance_creation_006.png)

   Quando o cálculo é concluído, os indicadores de mensuração são atualizados automaticamente.

   ![Guia Geral da Hipótese com os indicadores calculados pela hipótese, como taxa de resposta e reações](assets/response_hypothesis_instance_creation_007.png)

1. Se necessário, altere as configurações e reinicie a hipótese.

## Referenciar uma hipótese em uma entrega de campanha {#referencing-a-hypothesis-in-a-campaign-delivery}

É possível fazer referência a uma hipótese em uma campanha de marketing antes de ela ser iniciada. Nesse caso, a hipótese será iniciada automaticamente quando a entrega for enviada, com base nas configurações de execução definidas no modelo da hipótese. Para criar uma hipótese em uma entrega, aplique o seguinte processo:

1. Dependendo das suas necessidades, você pode criar um ou mais modelos do tipo **[!UICONTROL Delivery]**, conforme descrito em [Criar um modelo de hipótese](hypothesis-templates.md#creating-a-hypothesis-model)
1. Criar uma campanha de marketing e os fluxos de trabalho de segmentação.
1. Na janela da entrega, clique no ícone **[!UICONTROL Delivery measurement]**.
1. Selecione o modelo da hipótese (a consulta configurada no modelo é exibida na janela de hipótese).

   A hipótese será calculada automaticamente quando a campanha for concluída, com base nas datas configuradas no modelo. [Saiba mais](hypothesis-templates.md#hypothesis-template-execution-settings)

   ![Janela de medição de entrega com o botão Adicionar para fazer referência a um modelo de hipótese em uma entrega](assets/response_hypothesis_instance_creation_008.png)

## Adicionar uma hipótese padrão em entregas de uma campanha {#adding-a-default-hypothesis-to-deliveries-for-a-campaign}

Você pode fazer referência diretamente a uma hipótese no nível da campanha. Nesse caso, a hipótese será vinculada automaticamente a todos os envios criados na campanha. Para fazer isso:

1. Acesse a guia **[!UICONTROL Edit]** da campanha.
1. Na seção de mensuração, clique na guia **[!UICONTROL Default hypotheses]**.

   ![Guia Editar da campanha, seção Medição, com a guia Hipóteses padrão realçada](assets/response_hypothesis_instance_creation_010.png)

1. Clique em **[!UICONTROL Add]** e selecione um modelo de hipótese.

   ![Adicione uma caixa de diálogo de hipótese com o menu suspenso de modelo na guia Default hypotheses de uma campanha](assets/response_hypothesis_instance_creation_011.png)

   Agora uma hipótese baseada nesse modelo é referenciada por padrão em cada nova entrega da campanha.

   ![Janela de medição de entrega em uma lista de fluxo de trabalho de direcionamento Hipótese de compras](assets/response_hypothesis_instance_creation_012.png)

Os resultados da hipótese podem ser exibidos nas guias **[!UICONTROL General]** e **[!UICONTROL Reactions]** da hipótese. [Saiba mais](hypothesis-tracking.md)

Para obter mais informações, você também pode consultar [esta amostra](#example--creating-a-hypothesis-linked-to-a-delivery).

## Criar uma hipótese em uma oferta {#creating-a-hypothesis-on-an-offer}

Criar uma hipótese em uma apresentação da oferta é semelhante à criação em uma entrega de forma instantânea. A hipótese pode ser executada desde que a oferta esteja ativa. O período de cálculo é baseado na data da apresentação da oferta. Quando a hipótese permite vincular um destinatário a uma compra, o status da apresentação da oferta que provavelmente será aceita pode ser alterado automaticamente. [Saiba mais](hypothesis-templates.md#transactions)

1. Crie um ou mais modelos do tipo **[!UICONTROL Offer]** conforme descrito em [Crie um modelo de hipótese](hypothesis-templates.md#creating-a-hypothesis-model).
1. Vá para o nó **[!UICONTROL Campaign management > Measurement hypotheses]**
1. Crie uma hipótese do tipo **[!UICONTROL Offers]** ao selecionar o modelo criado anteriormente.

   ![Caixa de diálogo Nova hipótese com a lista suspensa de modelos listando modelos de oferta como Nova hipótese de oferta](assets/response_hypothesis_instance_offer_001.png)

   A consulta criada no modelo aparece na janela.

   ![Caixa de diálogo Nova hipótese com o modelo de Hipótese de oferta e o tipo de consulta igual a Item](assets/response_hypothesis_instance_offer_003.png)

1. Escolha a oferta para a qual deseja criar uma hipótese.

   ![Caixa de diálogo da nova hipótese com ofertas da lista suspensa Oferta, como Viagem a Paris](assets/response_hypothesis_instance_offer_004.png)

1. Refine a consulta, se necessário.
1. Clique em **[!UICONTROL Start]** para executar a hipótese.
1. Os resultados da hipótese podem ser exibidos nas guias **[!UICONTROL General]** e **[!UICONTROL Reactions]**. [Saiba mais](hypothesis-tracking.md)

   As hipóteses feitas em uma oferta são referenciadas na guia **[!UICONTROL Measurement]**.

   ![Guia Offer Measure com a lista de hipóteses vinculadas à oferta em Calculation of effectiveness ROI](assets/response_hypothesis_instance_offer_007.png)

   Se a opção **[!UICONTROL Update offer proposition status]** foi habilitada no modelo da hipótese, o status da apresentação da oferta é alterado automaticamente, fornecendo feedback sobre o impacto da campanha (para mais informações, consulte [Transações](hypothesis-templates.md#transactions)).

## Exemplo: criar uma hipótese vinculada a uma entrega {#example--creating-a-hypothesis-linked-to-a-delivery}

Neste exemplo, queremos criar uma hipótese vinculada a uma entrega. Essa hipótese será baseada no modelo criado anteriormente. [Saiba mais](hypothesis-templates.md#example--creating-a-hypothesis-template-on-a-delivery)

Em seguida, refine a consulta herdada do modelo para fazer uma hipótese em um artigo específico da tabela de compras.

1. Crie uma campanha e uma entrega. Consulte a [documentação do Campaign v8](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=pt-BR){target=_blank}.

   Nesse exemplo há uma entrega do tipo correspondência direta.

1. Configurar um endereço de origem: o modelo de hipótese criado anteriormente foi configurado para levar um grupo de controle em consideração nos resultados da reação.

   ![Configurações avançadas do Campaign, guia População de controle, com a configuração do grupo de controle habilitada](assets/response_hypothesis_delivery_example_007.png)

   >[!NOTE]
   >
   >Para obter mais informações, consulte a [documentação do Campaign v8](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=pt-BR#add-a-control-group){target="_blank"}.

1. Abra o **[!UICONTROL Direct mail delivery]** e clique no ícone **[!UICONTROL Delivery measurement]** e, em seguida, clique em **[!UICONTROL Add]**.

   ![Janela de medição de uma entrega de correspondência direta com o botão Adicionar para a hipótese](assets/response_hypothesis_delivery_example_002.png)

1. Escolha na lista suspensa o modelo de hipótese criado anteriormente.

   ![Adicione uma caixa de diálogo de hipótese com a lista suspensa de modelo Hipótese de Compra (HYP4)](assets/response_hypothesis_delivery_example_004.png)

   A consulta criada no modelo é exibida.

   ![Caixa de diálogo Nova hipótese com o modelo de linha Hipótese por tíquete e seu Filtro de consulta por produto](assets/response_hypothesis_delivery_example_005.png)

1. Clique em **[!UICONTROL Edit query...]** e refine a consulta inserindo o produto que a hipótese deve relacionar.

   ![Editar a janela de consulta que filtra a hipótese sobre o nome do produto igual a Vestuário](assets/response_hypothesis_delivery_example_006.png)

   É possível verificar se a hipótese está vinculada à entrega na guia **[!UICONTROL Edit]** > **[!UICONTROL Measurement]** da campanha.

   ![Seção de medição de campanha, guia Hipótese de medição, listando a Hipótese de compras para uma entrega](assets/response_hypothesis_delivery_example_008.png)

1. Inicie o fluxo de trabalho de direcionamento e execute as verificações necessárias até a conclusão da campanha. Consulte a [documentação do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries#start-a-delivery){target=_blank}.

   ![Painel de campanha com uma entrega de correspondência direta em andamento e seu status, população alvo e provas](assets/response_hypothesis_delivery_example_009.png)

1. Na árvore do Adobe Campaign, acesse o nó **[!UICONTROL Campaign management > Measurement hypotheses]** para verificar os indicadores calculados pela hipótese.

   ![Lista de hipóteses de medição e guia Geral com os indicadores calculados, como taxa de resposta contatada](assets/response_hypothesis_delivery_example_010.png)
