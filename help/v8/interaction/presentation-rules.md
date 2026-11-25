---
product: campaign
title: Regras de apresentação
description: Regras de apresentação
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: f9dd9ad6-48da-4a80-9405-109a433a1ed5
TQID: 'https://experienceleague.adobe.com/s2QV1BGLtUfyWg1BfYuryciF9STRK3HpIXNc6oQ0ATY'
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
source-wordcount: '703'
ht-degree: 62%
---
# Regras de apresentação{#presentation-rules}



## Criação de uma regra de apresentação {#creating-a-presentation-rule}

Em nosso banco de dados, existem várias ofertas de viagens para Europa, África, Estados Unidos e Canadá. Queremos enviar ofertas para uma viagem ao Canadá, mas se o recipient recusar esse tipo de oferta, não queremos enviá-lo novamente.

Vamos configurar nossa regra para que a viagem ao Canadá seja oferecida apenas uma vez por destinatário e, caso seja rejeitada, não será oferecida novamente.

1. Na árvore do Adobe Campaign, acesse o nó **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Typology management]** > **[!UICONTROL Typology rules]**.
1. Crie um novo tipo de regra **[!UICONTROL Offer presentation]**.

   ![Formulário de criação de regra de tipologia com a lista de tipos de regra aberta e a apresentação de oferta selecionada](assets/offer_typology_example_001.png)

1. Se necessário, altere o rótulo e a descrição.

   ![Guia Geral da regra de tipologia com um rótulo, o tipo de apresentação da oferta, o canal de email e uma descrição inserida](assets/offer_typology_example_002.png)

1. Escolha a opção **[!UICONTROL All channels]** para estender a regra para todos os canais.

   ![Lista de canais da regra de tipologia com Todos os canais selecionados](assets/offer_typology_example_003.png)

1. Clique no link **[!UICONTROL Edit expression]** e escolha o nó **[!UICONTROL Category]** como uma expressão.

   ![Janela de consulta com a caixa de diálogo Selecionar uma expressão aberta para escolher o campo Categoria](assets/offer_typology_example_004.png)

1. Escolha a categoria que corresponde à oferta de viagem para o Canadá e clique em **[!UICONTROL OK]** para fechar a janela de consulta.

   ![Consulta em categoria igual a Canadá, com a pasta Canadá selecionada na árvore de categoria de oferta de Viagem](assets/offer_typology_example_005.png)

1. Na guia **[!UICONTROL Offer presentation]**, escolha as mesmas dimensões que foram configuradas no ambiente.

   ![Guia de apresentação de oferta mostrando o Targeting dimension e o Storage dimension, que correspondem ao ambiente](assets/offer_typology_example_006.png)

1. Indique o período que a regra deve ser aplicada.

   ![Guia de apresentação de oferta com o período deslizante, campo Período considerado definido como 10d](assets/offer_typology_example_007.png)

1. Limite a apresentação para um, assim os destinatários que já rejeitaram uma viagem ao Canadá não receberão outra oferta semelhante.

   ![Guia Offer presentation com o campo Maximum number of propositions Quantity definido como 1](assets/offer_typology_example_008.png)

1. Selecione o filtro **[!UICONTROL Offers for the same category]** para excluir todas as ofertas da categoria **Canada**.

   ![Menu suspenso de ofertas em apresentações para contar com ofertas para a mesma categoria selecionada](assets/offer_typology_example_020.png)

1. Selecione o filtro **[!UICONTROL Rejected propositions]** para considerar apenas as apresentações rejeitadas pelo destinatário.

   ![Lista suspensa de status de apresentações para contar com as apresentações rejeitadas selecionadas](assets/offer_typology_example_021.png)

1. Indique os destinatários que a regra deve ser aplicada.

   Em nosso exemplo, nós indicaremos os destinatários do **Frequent travelers**.

   ![Editar assistente de consulta de filtragem selecionando a pasta de destinatários Frequent travelers como destino da regra](assets/offer_typology_example_009.png)

1. Referencie a regra em uma tipologia de oferta.

   ![Guia Tipologias da regra com a caixa de diálogo Adicionar tipologias listando a tipologia Ofertas selecionada](assets/offer_typology_example_013.png)

1. Acesse o ambiente de oferta, (**Environment - Recipient**, neste caso) e consulte a nova tipologia criada através da lista suspensa na guia **[!UICONTROL Eligibility]**.

   ![Guia Eligibility do ambiente de oferta com a lista Offer presentation typology mostrando Offers](assets/offer_typology_example_014.png)

## Aplicação da regra de apresentação {#applying-the-presentation-rule}

Aqui está um exemplo de aplicação da regra de tipologia criada anteriormente.

Queremos enviar uma apresentação de oferta que pertence à categoria Canadá. Se a oferta é rejeitada uma vez por qualquer um dos destinatários, então ela não será oferecida novamente.

1. Na pasta de destinatários **Frequent travelers**, escolha um dos perfis para verificar as ofertas para as quais estão qualificados: clique na guia **[!UICONTROL Propositions]** e, em seguida, na guia **[!UICONTROL Preview]**.

   Em nosso exemplo, **Tim Ramsey** está qualificado para uma oferta que faz parte da categoria **Americas** .

   ![Guia Apresentações do Destinatário, subguia Visualizar, listando a oferta qualificada para a categoria Américas](assets/offer_typology_example_015.png)

1. Comece criando uma entrega de email que seguimentará os seus representantes de **Frequent travelers** com ofertas.
1. Selecione os parâmetros de chamada do mecanismo de oferta.

   No nosso exemplo, a categoria **Travel in America** é escolhida, onde contém as subcategorias **Canada** e **United States**.

   ![Caixa de diálogo de gerenciamento de ofertas de uma entrega de email com a categoria Américas e 2 propostas por mensagem](assets/offer_typology_example_016.png)

1. Insira as ofertas no corpo da mensagem e envie a entrega. Para saber mais sobre isso, consulte [Sobre os canais de saída](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/offers/interaction-send-offers){target="_blank"} (documentação do Campaign v8).

   O destinatário recebeu a oferta para a qual está qualificado.

1. O destinatário rejeitou a oferta do Canadá, conforme mostrado no histórico de apresentações.

   ![Histórico de apresentações de destinatários com a oferta snowmobile do Canadá com o status Rejected](assets/offer_typology_example_018.png)

1. Verifique as ofertas para as quais ele está qualificado agora.

   Podemos ver que nenhuma oferta para o Canadá é escolhida.

   ![Guia Visualização de destinatários mostrando as ofertas qualificadas de Nova York e Grand Canyon, sem nenhuma oferta do Canadá](assets/offer_typology_example_019.png)
