---
product: campaign
title: Sobre a simulação de ofertas
description: Sobre a simulação de ofertas
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
exl-id: facaa88e-1fa2-4189-9d8f-348aaef3e235
TQID: 'https://experienceleague.adobe.com/034-CFbQIFVm9QiSpDyRHlVsIrF46NSqKMwp-Gm3-mc'
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 936b7519d13ab54d94df9305ef05d4ceb6d6742d
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 100%
---
# Sobre a simulação de ofertas{#about-offers-simulation}



O módulo **Simulation** permite testar a distribuição de ofertas pertencentes a uma categoria ou um ambiente antes de enviar sua proposta para os destinatários.

A simulação leva em consideração os contextos e as regras de elegibilidade aplicadas anteriormente às ofertas (consulte [Visão geral do catálogo de ofertas](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/offers/interaction-offer-catalog){target="_blank"} na documentação do Campaign v8), bem como suas regras de apresentação (consulte [Gerenciar a apresentação de ofertas](managing-offer-presentation.md)). Isso permite testar e refinar várias versões da apresentação de oferta sem realmente usar uma oferta ou sobrecarregar ou não um destino, já que a simulação não tem impacto nos destinatários de destino.

Para saber como simular uma oferta, leia as etapas abaixo.

![](assets/how-to-video.png)[ Você também pode assistir a este vídeo](https://helpx.adobe.com/campaign/classic/how-to/simulate-offer-in-acv6.html?playlist=/ccx/v1/collection/product/campaign/classic/segment/digital-marketers/explevel/intermediate/applaunch/introduction/collection.ccx.js&ref=helpx.adobe.com).

## Etapas principais para a criação de uma simulação {#main-steps-for-creating-a-simulation}

Para criar uma simulação de suas ofertas, aplique as seguintes etapas:

1. Na guia **[!UICONTROL Profiles and Targets]**, clique no link **[!UICONTROL Simulations]** e depois clique no botão **[!UICONTROL Create]**.

   ![](assets/offer_simulation_001.png)

1. Salve e edite a simulação que acabou de criar.
1. Vá para a guia **[!UICONTROL Edit]** e especifique as configurações de execução.

   Para obter mais informações, consulte [Configurações de execução](execution-settings.md).

   ![](assets/offer_simulation_003.png)

   >[!NOTE]
   >
   >As configurações de execução só estarão disponíveis se estiver usando o Interaction com o Campaign.

1. Especifique o escopo da simulação.

   Para obter mais informações, consulte [Definição do escopo](simulation-scope.md#definition-of-the-scope).

   ![](assets/offer_simulation_004.png)

1. Adicione eixos de relatórios para aprimorar o relatório **[!UICONTROL Offer distribution by rank]** (opcional).

   Para obter mais informações, consulte [Adição de eixos de relatórios](simulation-scope.md#adding-reporting-axes).

   ![](assets/offer_simulation_005.png)

1. Clique em **[!UICONTROL Save]** para gravar as configurações da simulação.
1. Inicie a simulação através do painel.

   ![](assets/offer_simulation_006.png)

1. Verifique o resultado da simulação e exiba o relatório de análise.

   Para obter mais informações, consulte [Rastreamento de simulação](simulation-tracking.md).

   ![](assets/offer_simulation_007.png)
