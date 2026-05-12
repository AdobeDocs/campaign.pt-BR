---
product: campaign
title: Entregas entre canais
description: Saiba mais sobre entregas entre canais
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
TQID: https://experienceleague.adobe.com/hD15kwTxO1uHeIQjrozZmONmVWI5ZrMn40ORMwrGbf8
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 254
ht-degree: 74%

---

# Entregas entre canais{#cross-channel-deliveries}

Entregas entre canais estão disponíveis na guia **[!UICONTROL Deliveries]** de [atividades do fluxo de trabalho da campanha](campaign-workflows.md).

Selecionar o modelo no qual deseja basear a entrega e definir seu conteúdo.

Você pode especificar um target para o upstream de entrega de fluxo de trabalho usando as diferentes atividades de direcionamento.

No exemplo abaixo, saiba como criar um fluxo de trabalho para enviar um email ou SMS a assinantes de notificação por push e, em seguida, uma notificação por push uma semana depois. Para fazer isso:

1. Crie uma campanha.
1. Na guia **[!UICONTROL Targeting and workflows]** da campanha, adicione uma atividade **[!UICONTROL Query]**.
1. Configurar sua query: selecione os recipients que assinaram notificações por push como o target dimension.

   >[!NOTE]
   >
   >Para as notificações por push, use a dimensão de direcionamento dos **aplicativos de assinante**.

   ![](assets/cross_channel_delivery_1.png)

1. Adicione as condições de filtro à sua consulta. Nesse caso, selecionamos destinatários com um número de celular ou endereço de email.

   ![](assets/cross_channel_delivery_2.png)

1. Adicione uma atividade **[!UICONTROL Split]** ao fluxo de trabalho para dividir destinatários com um número de celular e aqueles com um endereço de email.
1. Na guia **[!UICONTROL Delivery]**, selecione um workflow para cada target.

   Crie seu delivery da mesma forma que com um assistente de delivery comum clicando duas vezes na atividade de delivery no seu workflow.

   ![](assets/cross_channel_delivery_3.png)

1. Adicione e configure uma atividade **[!UICONTROL Wait]** para os destinatários não receberem muitas entregas de uma vez.
1. Adicione uma atividade **[!UICONTROL Split]** para dividir os assinantes de aplicativos móveis iOS ou Android.

   Selecione um serviço para cada um dos sistemas operacionais.

   ![](assets/cross_channel_delivery_4.png)

1. Selecione e configure uma entrega de aplicativo móvel para cada um dos sistemas operacionais.

   ![](assets/cross_channel_delivery_5.png)
