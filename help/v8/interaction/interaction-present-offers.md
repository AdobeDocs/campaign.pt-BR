---
product: campaign
title: Apresentar uma oferta (interação de entrada)
description: Saiba como apresentar a melhor oferta usando o módulo de interação do Campaign
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 21%

---

# Apresentar a melhor oferta{#interaction-present-offers}

As ofertas podem ser apresentadas em vários espaços de oferta usando [um canal de entrada ou saída](interaction-architecture.md#interaction-types). Este capítulo detalha alguns recursos específicos para canais de entrada.

![](assets/inbound-interactions.png)

Para que uma oferta seja selecionada pelo mecanismo de Oferta, ela deve ser aprovada e estar disponível em um ambiente ativo.

Para obter mais informações, consulte [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content)

No contexto de um contato de entrada para um contato, o usuário que está navegando na página pode ser identificado pelo site ou não. O mecanismo de oferta apresenta diferentes ofertas para perfis identificados e para perfis anônimos.

Antes de poder apresentar ofertas em um canal de entrada, é necessário configurar a chamada do Mecanismo de oferta onde deseja que as ofertas sejam apresentadas. Na maioria dos casos para uma interação de entrada, esta é a página da Web.

>[!NOTE]
>
>Para interações de entrada, é necessário configurar especificamente o mecanismo de Oferta para apresentar e atualizar uma ou várias ofertas.
>
>Também é preciso habilitar o modo unitário em seus espaços de oferta. Para obter mais informações, consulte [esta página](interaction-offer-spaces.md).
