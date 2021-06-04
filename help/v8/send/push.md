---
product: Adobe Campaign
title: Enviar notificação por push com o Adobe Campaign
description: Introdução à notificação por push no Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
source-git-commit: c6f1cfdec3d05a81f8885cc73b370723024f858f
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 44%

---

# Criar e enviar notificações por push

Os deliveries de aplicativos móveis permitem enviar notificações para sistemas iOS e Android.

Para enviar notificações por push no Adobe Campaign, é necessário:

1. Configurar o ambiente do Campaign
1. Crie um serviço de informações do tipo aplicativo móvel para seu aplicativo móvel.
1. Adicione as versões iOS e Android do aplicativo a este serviço.
1. Crie um delivery para iOS e Android.

[!DNL :arrow_upper_right:] Saiba como começar a usar o aplicativo móvel na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## Integrar ao SDK do Adobe

### Integrar SDK do Campaign

O SDK do Campaign facilita a integração do aplicativo móvel na plataforma Adobe Campaign.

[!DNL :arrow_upper_right:] Saiba como integrar o SDK do Campaign ao seu aplicativo na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### Configurar a extensão do Campaign no Launch

É possível integrar o SDK do Adobe Experience Platform Launch com o Campaign, aproveitando a extensão Campaign Classic.

[!DNL :arrow_upper_right:] Saiba mais na documentação do SDK do  [Adobe Mobile](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Definir as configurações do aplicativo no Campaign

Você deve definir as configurações dos aplicativos iOS e Android no Adobe Campaign.

[!DNL :arrow_upper_right:] As diretrizes de configuração para iOS são detalhadas na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

[!DNL :arrow_upper_right:] As diretrizes de configuração para Android estão detalhadas na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## Criar sua primeira notificação por push

Esta seção detalha os elementos específicos para o delivery de notificações iOS e Android.

[!DNL :arrow_upper_right:] Todas as etapas para criar notificações por push são detalhadas na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)

>[!CAUTION]
>
>Com o Campaign v8, o registro móvel agora é **assíncrono**. [Saiba mais](../dev/staging.md)

Para criar um novo delivery, navegue até a guia **[!UICONTROL Campaigns]** , clique em **[!UICONTROL Deliveries]** e clique no botão **[!UICONTROL Create]** acima da lista de deliveries existentes.

![](assets/delivery_step_1.png)

### Envio de notificações no iOS {#sending-notifications-on-ios}

1. Selecione o template do delivery **[!UICONTROL Deliver on iOS]** e clique em **[!UICONTROL Continue]**.

   ![](assets/push-template-ios.png)

1. Para definir o target da notificação, clique no link **[!UICONTROL To]** e, em seguida, clique em **[!UICONTROL Add]**.

   ![](assets/push-ios-select-target.png)

1. Selecione **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, selecione o serviço relevante para seu aplicativo móvel e selecione a versão iOS do aplicativo.

   ![](assets/push-ios-subscribers.png)

1. Selecione o tipo de notificação: **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** ou **[!UICONTROL Silent Push]**.

   ![](assets/push-ios-alert.png)

1. No campo **[!UICONTROL Title]**, insira o rótulo do título que deve aparecer na notificação.

1. Insira o **[!UICONTROL Message]** e o **[!UICONTROL Value of the badge]** com base no tipo de notificação escolhido.

1. O **[!UICONTROL Action button]** permite definir um rótulo para o botão de ação que aparece nas notificações de alerta (campo **action_loc_key** da carga).

1. No campo **[!UICONTROL Play a sound]**, selecione o som a ser reproduzido pelo terminal móvel quando a notificação for recebida.

1. No campo **[!UICONTROL Application variables]**, insira o valor de cada variável. Por exemplo, você pode configurar uma tela de aplicativo específica a ser exibida quando o usuário ativar a notificação.

1. Quando a notificação estiver configurada, clique na guia **[!UICONTROL Preview]** para visualizar a notificação.

   ![](assets/push-ios-preview.png)

### Enviar notificações no Android {#sending-notifications-on-android}

1. Selecione o modelo de delivery **[!UICONTROL Deliver on Android (android)]**.

   ![](assets/push-template-android.png)

1. Para definir o target da notificação, clique no link **[!UICONTROL To]** e, em seguida, clique em **[!UICONTROL Add]**.

   ![](assets/nmac_delivery_android_2.png)

1. Selecione **[!UICONTROL Subscribers of an Android mobile application]**, escolha o serviço relevante para seu aplicativo móvel (Neotrips, neste caso) e selecione a versão Android do aplicativo.

   ![](assets/push-android-select-target.png)

1. Em seguida, insira o conteúdo da notificação.

   ![](assets/push-android-content.png)

1. Clique no ícone **[!UICONTROL Insert emoticon]** para inserir emoticons à notificação via push.

1. No campo **[!UICONTROL Application variables]**, insira o valor de cada variável. Por exemplo, você pode configurar uma tela de aplicativo específica a ser exibida quando o usuário ativar a notificação.

1. Quando a notificação estiver configurada, clique na guia **[!UICONTROL Preview]** para visualizar a notificação.

   ![](assets/push-android-preview.png)

## Teste, envie e monitore suas notificações por push

Para enviar uma prova e o delivery final, use o mesmo processo que os deliveries de email.

Após enviar as mensagens, você pode monitorar e rastrear seus deliveries.