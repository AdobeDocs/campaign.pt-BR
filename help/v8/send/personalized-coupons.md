---
product: campaign
title: Cupons personalizados
description: Saiba como criar e inserir cupons personalizados
feature: Personalization
role: User
version: Campaign v8, Campaign Classic v7
exl-id: d5af1f98-42e8-4909-b2e6-be65c50c9874
TQID: 'https://experienceleague.adobe.com/RTn-nTK3YjtekmBU9BcSIK05n0eJX2EImRsJlHAUG48'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: 13af5358-448e-5a4a-850b-0db592bb0f8f
    internal-label: Personalization
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 72%
---
# Cupons personalizados{#personalized-coupons}

A adição de cupons a suas entregas pode oferecer aos destinatários valor aprimorado para produtos e serviços. Você pode usar o módulo de cupom do Campaign para criar um conjunto de cupons que você planeja adicionar às futuras ofertas de marketing. Quando estiver pronto para criar uma entrega, atribua os cupons aplicáveis. Como os cupons são válidos para um período de seleção, um cupom atribuído é vinculado exclusivamente à sua mensagem de entrega. Além disso, o Campaign confirma que há cupons suficientes para o número de mensagens antes do envio da entrega.

>[!AVAILABILITY]
>
>O gerenciamento de cupons não está disponível no Campaign v8 no contexto de uma Implantação corporativa (FFDA). Saiba mais na [documentação do Campaign v8](../architecture/enterprise-deployment.md).

O gerenciamento de cupons depende de um pacote que deve ser instalado. Para confirmar se há um gerenciamento de cupom, verifique **[!UICONTROL Administration > Configuration > Package management > Installed packages.]**

Os dados de cupom podem ser importados e exportados usando formatos CSV e XML. [Saiba mais](../start/import.md).

## Criar um cupom {#creating-a-coupon}

O módulo de gerenciamento de cupons oferece duas opções ao criar cupons:

* **Anônimo**: um cupom genérico para destinatários ou listas de destinatários selecionados.
* **Individual**: um cupom personalizado para destinatários selecionados.

Antes de seguir as etapas abaixo, verifique se você sabe o tipo de cupom que deseja criar.

1. Na árvore do Campaign, acesse **[!UICONTROL Resources > Campaign management > Coupons]**.

   ![Árvore de campanhas com Recursos, Gerenciamento de campanhas expandido e o nó Cupons selecionado](assets/deliv_coup_01.png)

1. Clique no botão **[!UICONTROL New]**.
1. Insira o nome do cupom no campo **[!UICONTROL Label]**. Um código exclusivo foi inserido automaticamente no **[!UICONTROL Coupon code]**. Você pode manter o código ou inserir um novo.

   ![Lista de cupons e guia Geral de um cupom com Rótulo, Código do cupom, Tipo de cupom, Data inicial e Campos de data final](assets/deliv_coup_02.png)

1. Escolha **[!UICONTROL Start date]** e **[!UICONTROL End date]** para definir o período de validade do cupom.
1. Em **[!UICONTROL Coupon type]**, escolha Anônimo ou Individual.

   **[!UICONTROL Anonymous coupons]** : Um cupom anônimo é idêntico para todos os destinatários. Confirme se Anônimo está selecionado no menu **Tipo de cupom** e clique em **Salvar** para gerar o cupom.

   **[!UICONTROL Individual coupons]** : Um cupom individual pode ser personalizado ainda mais com códigos de cupom adicionais. Por exemplo, um cupom individual é criado para uma venda em uma loja de equipamentos esportivos. No entanto, a lista de destinatários é longa e não compartilham a mesma paixão por um único esporte. Você pode adicionar nomes personalizados para o cupom individual com base em um esporte (por exemplo, futebol, futebol americano, beisebol etc.) e enviar cada nome para os destinatários aplicáveis.

   1. Ao escolher Indivíduo, Cupons abre como uma nova guia na parte inferior esquerda. Acesse a guia **[!UICONTROL Coupons]** e clique em **[!UICONTROL Add]**.
   1. Insira um código exclusivo para o cupom individual quando solicitado pela janela pop-up.
   1. Clique em **[!UICONTROL Save]** para gerar o cupom.

   Para obter mais detalhes sobre a guia Cupons, consulte [Configurar cupons individuais](#configuring-individual-coupons).

   >[!NOTE]
   >
   >Os cupons individuais podem ser importados em massa. Para obter detalhes sobre a importação e exportação, consulte [Introdução aos perfis](../start/import.md).

### Configurar cupons individuais {#configuring-individual-coupons}

![Guia Cupons de um cupom que lista códigos de cupom individuais, cada um com um status Disponível](assets/deliv_coup_03.png)

A guia Cupons está disponível apenas com cupons individuais. Depois que um cupom é associado a uma entrega, a guia Cupons fornece os seguintes detalhes:

* **[!UICONTROL Status]** : Disponibilidade do cupom.
* **[!UICONTROL Redeemed on]** : A data de resgate do cupom.
* **[!UICONTROL Channel]** : O canal usado para enviar o cupom.
* **[!UICONTROL Address]** : Os endereços de email dos destinatários.

Os valores de **[!UICONTROL status]**, **[!UICONTROL channel]** e **[!UICONTROL address]** são automaticamente preenchidos. No entanto, os valores de **[!UICONTROL redeemed on]** não são recuperados pelo Campaign. Eles podem ser concluídos ao importar um arquivo com os detalhes de resgate do cupom.

## Inserir um cupom em uma entrega por email {#inserting-a-coupon-into-an-email-delivery}

No exemplo abaixo, a entrega é criada a partir da Home page. Para obter instruções detalhadas sobre como criar um delivery, consulte [Enviar emails com o Adobe Campaign](email.md).
1. Acesse **[!UICONTROL Campaigns]** e escolha **[!UICONTROL Deliveries]**.
1. Clique em **[!UICONTROL Create]**.

   ![Lista de entregas na guia Campanhas com o botão Criar realçado](assets/deliv_coup_04.png)

1. Insira um nome em **[!UICONTROL Label]** e clique em **[!UICONTROL Continue]**.
1. Clique em **[!UICONTROL To]** para adicionar destinatários.
1. Clique em **[!UICONTROL Add]** para escolher os destinatários da entrega Depois de selecionar seus destinatários, clique em **[!UICONTROL Ok]** para retornar para a entrega.

   ![Caixa de diálogo Selecionar destino na guia Destino principal com o botão Adicionar realçado](assets/deliv_coup_05.png)

1. Insira um assunto e adicione conteúdo à mensagem.

   ![Editor de entrega com um assunto e conteúdo do HTML para o email de cupom](assets/deliv_coup_06.png)

1. Na barra de ferramentas, clique em **[!UICONTROL Properties]** e escolha a guia **[!UICONTROL Advanced]**.
1. Clique no ícone de pasta para **[!UICONTROL Coupon management]**.

   ![Guia Propriedades de entrega Avançadas com o ícone de pasta ao lado do campo Cupom na Gestão de cupom realçado](assets/deliv_coup_07.png)

1. Escolha o cupom e clique em **[!UICONTROL Ok]**. Clique novamente em **[!UICONTROL Ok]**.

   ![Caixa de diálogo de seleção de cupom listando documentos de cupom com cupons de futebol selecionados](assets/deliv_coup_08.png)

1. Clique na mensagem para escolher onde deseja colocar o cupom.

   ![Editor de conteúdo do HTML com o cursor colocado onde o código do cupom deve ser inserido](assets/deliv_coup_09.png)

1. Clique no ícone de personalização para fazer a escolha baseada no tipo de cupom:

   * Cupom anônimo: **[!UICONTROL Coupon > Coupon code]**

     ![Menu do Personalization com Cupom e código do cupom selecionado, para um cupom anônimo](assets/deliv_coup_10.png)

   * Cupom individual: **[!UICONTROL Coupon value > Coupon code]**

     ![Menu do Personalization com valor do cupom e código do cupom selecionado, para um cupom individual](assets/deliv_coup_11.png)

     O cupom é inserido na mensagem como código em vez do nome que você atribuiu. O código é usado no modelo padrão de dados do Campaign.

   ![Conteúdo de email com o script de código de cupom inserido, couponValue.couponCode, realçado](assets/deliv_coup_12.png)

1. Execute um teste para confirmar o nome atribuído ao cupom. Acesse a guia **[!UICONTROL Preview]** e clique em **[!UICONTROL Test personalization]**. Escolha um destinatário para o teste.

   ![Guia Visualizar com o menu de personalização de teste aberto e a opção Destinatário realçada](assets/deliv_coup_13.png)

   Após o teste, o cupom deve aparecer como o nome atribuído em vez do código.

   ![Visualização do email com o código do cupom Trynow exibido no corpo da mensagem](assets/deliv_coup_14.png)

1. Na barra de ferramentas, clique em **[!UICONTROL Send]**, no canto superior esquerdo, e escolha como enviar a entrega.

   ![Enviar para a caixa de diálogo principal do destino de entrega com a opção Enviar assim que possível e o botão Analisar](assets/deliv_coup_15.png)

1. Clique em **[!UICONTROL Analyze]**. Se o log de análise confirmar que há cupons suficientes para todos os destinatários, clique em **[!UICONTROL Confirm delivery]** para enviar a mensagem.

   ![Log de análise de entrega mostrando 2 cupons reciclados e o botão Confirmar entrega disponível](assets/deliv_coup_16.png)

>[!NOTE]
>
>Para obter instruções sobre como gerenciar os cupons insuficientes de um delivery, consulte [Gerenciar cupons insuficientes](#managing-insufficient-coupons).

Para confirmar que a entrega foi bem-sucedida:

1. Vá para **[!UICONTROL Explorer > Resources > Campaign management > Coupons]**.
1. Clique na guia **[!UICONTROL Deliveries]**.

   ![Guia Entregas de um cupom que lista as entregas que o usam com suas contagens de status e mensagens](assets/deliv_coup_17.png)

   O status é lido como **[!UICONTROL Finished]** para uma entrega bem-sucedida.

>[!NOTE]
>
>Por padrão, o módulo de gestão de cupom usa uma tabela **nms:recipient**. [Saiba mais](../dev/datamodel.md#ootb-profiles).
>
>Aprenda como usar uma tabela de destinatário personalizada [nesta página](../dev/custom-recipient.md).

## Gerenciar cupons insuficientes {#managing-insufficient-coupons}

A análise da entrega para se o número de cupons for menor que de mensagens. Nesse caso, você pode importar mais cupons ou restringir o número de mensagens. Siga as instruções abaixo se desejar limitar o número de mensagens.

1. Vá para a janela de entrega do email.
1. Clique em **[!UICONTROL To]**.
1. Em **[!UICONTROL Select target]**, acesse a guia **[!UICONTROL Exclusions]**.

   ![Caixa de diálogo Selecionar destino com a guia Exclusões realçada e o link Editar para configurações de exclusão](assets/deliv_coup_18.png)

1. Na seção de configurações de exclusão, clique em **[!UICONTROL Edit]**.
1. Insira o número de mensagens que deseja enviar em **[!UICONTROL Limit delivery to...messages]** e clique em **[!UICONTROL Ok]**. Você pode enviar a entrega.

   ![Caixa de diálogo de configurações de exclusão com o campo Limitar entrega a definido como 20 mensagens realçadas](assets/deliv_coup_19.png)

>[!NOTE]
>
>Ao gerenciar um número limitado de cupons, um fluxo de trabalho de entrega permite dividir a entrega com base em seus critérios. É uma boa opção para enviar cupons para um população selecionada sem restringir o target.
