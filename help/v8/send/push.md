---
solution: Campaign v8
product: Adobe Campaign
title: Enviar notificação por push com o Adobe Campaign
description: Introdução à notificação por push no Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 16%

---

# Criar e enviar notificações por push

Os deliveries de aplicativos móveis permitem enviar notificações para sistemas iOS e Android.

Para enviar notificações por push no Adobe Campaign, é necessário:

1. Configurar o ambiente do Campaign
1. Crie um serviço de informações do tipo aplicativo móvel para seu aplicativo móvel.
1. Adicione as versões iOS e Android do aplicativo a este serviço.
1. Crie um delivery para iOS e Android.

:seta_upper_right: Saiba como começar a usar o aplicativo móvel na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## Integrar ao SDK do Adobe

### Integrar SDK do Campaign

O SDK do Campaign facilita a integração do aplicativo móvel na plataforma Adobe Campaign.

:seta_upper_right: Saiba como integrar o SDK do Campaign com seu aplicativo na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### Configurar a extensão do Campaign no Launch

É possível integrar o SDK do Adobe Experience Platform Launch com o Campaign, aproveitando a extensão Campaign Classic.

:seta_upper_right: Saiba mais em [Documentação do SDK do Adobe Mobile](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Definir as configurações do aplicativo no Campaign

Você deve definir as configurações dos aplicativos iOS e Android no Adobe Campaign.

:seta_upper_right: As diretrizes de configuração para iOS são detalhadas na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

:seta_upper_right: As diretrizes de configuração para Android são detalhadas na documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## Criar sua primeira notificação por push

:seta_upper_right: Saiba como criar suas primeiras notificações por push na documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)


>[!CAUTION]
>
>Com o registro móvel do Campaign v8 agora é **assíncrono**. [Saiba mais](../dev/staging.md).
