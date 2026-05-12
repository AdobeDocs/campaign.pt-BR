---
title: SMS Enviar provas
description: Saiba como enviar provas de uma entrega de SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: d2ec4d92-7f00-47c8-98e6-0613d6387de0
TQID: https://experienceleague.adobe.com/mAVky406-MXlkv76bqxfmolzhemVCUYKhQF1ESceRdE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 244
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
