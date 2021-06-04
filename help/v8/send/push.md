---
product: Adobe Campaign
title: Enviar notificação por push com o Adobe Campaign
description: Introdução à notificação por push no Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
source-git-commit: 09979331284757527fc9a24479a53d2d488f4649
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 34%

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

[!DNL :arrow_upper_right:] Todas as etapas para criar notificações por push são detalhadas na documentação do  [Campaign Classic v7](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en)

>[!CAUTION]
>
>Com o Campaign v8, o registro móvel agora é **assíncrono**. [Saiba mais](../dev/staging.md)

Para criar um novo delivery, navegue até a guia **[!UICONTROL Campaigns]** , clique em **[!UICONTROL Deliveries]** e clique no botão **[!UICONTROL Create]** acima da lista de deliveries existentes.

![](assets/delivery_step_1.png)

[!DNL :arrow_upper_right:] Para obter informações globais sobre como criar um delivery, consulte a documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages).

### Enviar notificações no iOS {#send-notifications-on-ios}

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

1. Você também pode definir os seguintes elementos:

   * O **[!UICONTROL Action button]** permite definir um rótulo para o botão de ação que aparece nas notificações de alerta (campo **action_loc_key** da carga).

   * No campo **[!UICONTROL Play a sound]**, selecione o som a ser reproduzido pelo terminal móvel quando a notificação for recebida.

   * No campo **[!UICONTROL Application variables]**, insira o valor de cada variável. Por exemplo, você pode configurar uma tela de aplicativo específica a ser exibida quando o usuário ativar a notificação.

1. Quando a notificação estiver configurada, clique na guia **[!UICONTROL Preview]** para visualizar a notificação.

   ![](assets/push-ios-preview.png)

[!DNL :arrow_upper_right:] Todas as etapas detalhadas para criar e enviar notificações por push no iOS estão detalhadas na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)

### Enviar notificações no Android {#send-notifications-on-android}

1. Selecione o modelo de delivery **[!UICONTROL Deliver on Android (android)]**.

   ![](assets/push-template-android.png)

1. Para definir o target da notificação, clique no link **[!UICONTROL To]** e, em seguida, clique em **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Selecione **[!UICONTROL Subscribers of an Android mobile application]**, escolha o serviço relevante para seu aplicativo móvel (Neotrips, neste caso) e selecione a versão Android do aplicativo.

   ![](assets/push-ios-subscribers.png)

1. Em seguida, insira o conteúdo da notificação.

   ![](assets/push-android-content.png)

1. Clique no ícone **[!UICONTROL Insert emoticon]** para inserir emoticons à notificação via push.

1. No campo **[!UICONTROL Application variables]**, insira o valor de cada variável. Por exemplo, você pode configurar uma tela de aplicativo específica a ser exibida quando o usuário ativar a notificação.

1. Quando a notificação estiver configurada, clique na guia **[!UICONTROL Preview]** para visualizar a notificação.

   <!--![](assets/push-android-preview.png)-->

[!DNL :arrow_upper_right:] Todas as etapas detalhadas para criar e enviar notificações por push no Android estão detalhadas na documentação do  [Campaign Classic v7 .](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-android)

## Teste, envie e monitore suas notificações por push

Para enviar uma prova e o delivery final, use o mesmo processo que os deliveries de email. Saiba mais na documentação do Campaign Classic v7:

* Validar um delivery e enviar provas
   [!DNL :arrow_upper_right:] [Saiba mais sobre as principais etapas para validar um delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

* Confirmar e enviar o delivery
   [!DNL :arrow_upper_right:] [Saiba mais sobre as principais etapas para enviar um delivery](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en)

Após enviar as mensagens, você pode monitorar e rastrear seus deliveries. Saiba mais na documentação do Campaign Classic v7:

* Notificação por push em quarentena
   [!DNL :arrow_upper_right:] [Saiba mais sobre a quarentena de notificações por push](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines)

* Solução de problemas
   [!DNL :arrow_upper_right:] [Saiba como solucionar problemas de notificações por push](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en)