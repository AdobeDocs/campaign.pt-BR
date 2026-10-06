---
title: SMS Enviar provas
description: Saiba como enviar provas de uma entrega de SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: d2ec4d92-7f00-47c8-98e6-0613d6387de0
TQID: 'https://experienceleague.adobe.com/mAVky406-MXlkv76bqxfmolzhemVCUYKhQF1ESceRdE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 6%
---
# Enviar uma prova de entrega de SMS {#sms-proof}

A Adobe recomenda configurar um ciclo de validação de delivery. Verifique se o conteúdo foi aprovado antes de enviá-lo para o público-alvo.

Você pode enviar uma prova para o delivery de SMS para validá-lo:

1. Clique no botão **[!UICONTROL Send a proof]**. Uma janela será aberta

   ![](assets/proof_targeting.png){zoomable="yes"}

   Há vários modos para enviar uma prova:

   * **[!UICONTROL Definition of a specific proof target]**: permite consultar com filtros os endereços no banco de dados como o destino da prova
   * **[!UICONTROL Substitution of the address]**: permite inserir seus endereços de teste e usar os dados do destinatário de destino para validar o conteúdo. Os endereços de substituição podem ser inseridos manualmente ou selecionados na lista suspensa. A [enumeração](../../config/enumerations.md) associada é **[!UICONTROL Substitution address (rcpAddress)]**.
     Por padrão, a substituição é executada aleatoriamente, mas você pode selecionar um recipient específico do público-alvo principal, por meio do ícone **[!UICONTROL Detail]**.
   * **[!UICONTROL Seed addresses]**: permite acesso a seed addresses para ser o destino da prova. Esses endereços podem ser importados de um arquivo ou inseridos manualmente.
   * **[!UICONTROL Specific target and Seed addresses]**: permite combinar seed addresses e endereços de recipients.

1. Depois de escolher o **[!UICONTROL Targeting mode]**, adicione seus endereços de prova de acordo com ele

   No exemplo abaixo, escolhemos **[!UICONTROL Definition of a specific proof target]** e adicionamos um recipient:

   ![](assets/proof_recipient.png){zoomable="yes"}

1. Clique no botão **[!UICONTROL Analyze]**.
O Adobe Campaign realizará todo o controle antes de validar o envio da prova. No final da análise, o botão **[!UICONTROL Confirm delivery]** será clicável.

   ![](assets/proof_analyze.png){zoomable="yes"}

1. Para enviar a prova da entrega do SMS, clique no botão **[!UICONTROL Confirm delivery]**.

Se tudo estiver certo neste estágio, você pode avançar e [enviar sua entrega de SMS para o público-alvo](sms-audience.md).
