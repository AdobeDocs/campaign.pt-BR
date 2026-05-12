---
product: campaign
title: Apresentar uma oferta (interação de entrada)
description: Saiba como apresentar a melhor oferta usando o módulo de interação do Campaign
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
TQID: https://experienceleague.adobe.com/aC-hN1JwwFkuGc6ZNV0M3uHpM7LcXTHpyC9wCbxKziQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 23%

---

# Apresentar a melhor oferta{#interaction-present-offers}

As ofertas podem ser apresentadas em vários espaços de ofertas usando [um canal de entrada ou saída](interaction-architecture.md#interaction-types). Este capítulo detalha alguns recursos específicos para canais de entrada.

![](assets/inbound-interactions.png)

Para que uma oferta seja selecionada pelo mecanismo de Oferta, ela deve ser aprovada e estar disponível em um ambiente ativo.

Para obter mais informações, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=pt-BR#approving-offer-content){target="_blank"}.

No contexto de um contato de entrada para um contato, o usuário que está navegando na página pode ser identificado pelo site ou não. O mecanismo de oferta apresenta diferentes ofertas para perfis identificados e para perfis anônimos.

Antes de poder apresentar ofertas em um canal de entrada, é necessário configurar a chamada do Mecanismo de oferta onde deseja que as ofertas sejam apresentadas. Na maioria dos casos para uma interação de entrada, esta é a página da Web.

>[!NOTE]
>
>Para interações de entrada, é necessário configurar especificamente o mecanismo de Oferta para apresentar e atualizar uma ou várias ofertas.
>
>Também é preciso habilitar o modo unitário em seus espaços de oferta. Para obter mais informações, consulte [esta página](interaction-offer-spaces.md).
