---
product: campaign
title: Apresentar uma oferta (interação de entrada)
description: Saiba como apresentar a melhor oferta usando o módulo de interação do Campaign
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
TQID: 'https://experienceleague.adobe.com/aC-hN1JwwFkuGc6ZNV0M3uHpM7LcXTHpyC9wCbxKziQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 15%
---
# Apresentar a melhor oferta{#interaction-present-offers}

As ofertas podem ser apresentadas em vários espaços de ofertas usando [um canal de entrada ou saída](interaction-architecture.md#interaction-types). Este capítulo detalha alguns recursos específicos para canais de entrada.

![Fluxo de entrada: navegar em um site, identificar o visitante por cookie ou logon, o Mecanismo de oferta escolhe a melhor oferta do catálogo](assets/inbound-interactions.png)

Para que uma oferta seja selecionada pelo mecanismo de Oferta, ela deve ser aprovada e estar disponível em um ambiente ativo.

Para obter mais informações, consulte [Aprovação do conteúdo da oferta](approving-and-activating-an-offer.md#approving-offer-content).

No contexto de um contato de entrada, o usuário que está navegando na página pode ser identificado pelo site ou não. O mecanismo de oferta apresenta diferentes ofertas para perfis identificados e para perfis anônimos.

Antes de poder apresentar ofertas em um canal de entrada, é necessário configurar a chamada do Mecanismo de oferta onde deseja que as ofertas sejam apresentadas. Na maioria dos casos para uma interação de entrada, esta é a página da Web.

>[!NOTE]
>
>Para interações de entrada, é necessário configurar especificamente o mecanismo de Oferta para apresentar e atualizar uma ou várias ofertas.
>
>Também é preciso habilitar o modo unitário em seus espaços de oferta. Para obter mais informações, consulte [Espaços de ofertas de interação de campanha](interaction-offer-spaces.md).
