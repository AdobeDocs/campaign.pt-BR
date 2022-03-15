---
product: campaign
title: Apresentar uma oferta (interação de entrada)
description: Saiba como apresentar a melhor oferta usando o módulo Campaign Interaction
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: c19ac91fe7b4b825f75ec096320efabc3e78328c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 25%

---

# Apresentar a melhor oferta{#interaction-present-offers}

As ofertas podem ser apresentadas em vários espaços de ofertas usando [um canal de entrada ou saída](interaction-architecture.md#interaction-types). Este capítulo detalha alguns recursos específicos para canais de entrada.

![](assets/inbound-interactions.png)

Para que uma oferta seja selecionada pelo mecanismo Offer, ela deve ser aprovada e estar disponível em um ambiente ativo.

![](../assets/do-not-localize/book.png) Para obter mais informações, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=en#approving-offer-content)

No contexto de um contato de entrada, o usuário que está navegando na página pode ser identificado pelo site ou não. O Motor de oferta apresenta ofertas diferentes para perfis identificados e para perfis anônimos.

Antes de poder apresentar ofertas em um canal de entrada, você deve configurar a chamada do mecanismo de oferta onde deseja que as ofertas sejam apresentadas. Na maioria dos casos para uma interação de entrada, esta é a página da Web.

>[!NOTE]
>
>Para interações de entrada, você deve configurar especificamente o mecanismo de oferta para apresentar e atualizar uma ou várias ofertas.
>
>Também é preciso habilitar o modo unitário em seus espaços de oferta. Para obter mais informações, consulte [esta página](interaction-offer-spaces.md).
