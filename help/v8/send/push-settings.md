---
title: Integrar SDK e Campaign da AEP
description: Saiba como integrar o SDK móvel do Adobe Experience Platform ao seu aplicativo
version: v8
feature: Push
role: Admin, Developer
level: Intermediate
exl-id: 1a75f411-3f71-4114-b738-277820dc6138
source-git-commit: 550e3cbd064ae7831855377f1d08d6acecd55c9e
workflow-type: tm+mt
source-wordcount: '1664'
ht-degree: 17%

---

# Configurar canal de notificação por push {#push-notification-configuration}

Para enviar notificações por push com o Adobe Campaign, primeiro você deve configurar o ambiente e o aplicativo conforme detalhado nesta página. No Adobe Campaign, o canal para enviar notificações por push é o canal de aplicativo móvel.

>[!CAUTION]
>
>Algumas alterações importantes no serviço Firebase Cloud Messaging (FCM) para Android serão lançadas em 2024 e poderão afetar sua implementação do Adobe Campaign. A configuração dos serviços de assinatura para mensagens por push no Android pode precisar ser atualizada para oferecer suporte a essa alteração. É recomendado verificar isso antecipadamente e tomar as devidas ações. [Saiba mais](../../technotes/upgrades/push-technote.md).

Antes de começar a enviar notificações por push com o Adobe Campaign, é necessário garantir que as configurações e integrações estejam em vigor no aplicativo móvel e para tags na Adobe Experience Platform. O SDK móvel da Adobe Experience Platform fornece APIs de integração do lado do cliente para seus dispositivos móveis por meio de SDKs compatíveis com Android e iOS.

Para configurar seu aplicativo com SDKs do Adobe Experience Platform Mobile, siga estas etapas:

1. Marcar [pré-requisitos](#before-starting).
1. Configurar um [propriedade de tag móvel](#launch-property) em Coleção de dados da Adobe Experience Platform.
1. Obtenha o SDK do Adobe Experience Platform Mobile como detalhado [nesta página](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (opcional) Ativar registro e medições de ciclo de vida, conforme detalhado [nesta página](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (opcional) Adicionar [Adobe Experience Platform Assurance para o seu aplicativo](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Configure os serviços móveis para iOS e Android no Adobe Campaign conforme detalhado [nesta página](#push-service).
1. Instalar e configurar [Extensão do Adobe Campaign](#configure-extension) em sua propriedade móvel.
1. Seguir [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} para obter a configuração com os SDKs do Adobe Experience Platform Mobile no seu aplicativo.

## Pré-requisitos {#before-starting}

### Configurar permissões {#setup-permissions}

Antes de criar um aplicativo para dispositivos móveis, primeiro verifique se você tem ou atribui as permissões de usuário corretas para as tags na Adobe Experience Platform. As permissões do usuário para tags na Adobe Experience Platform são atribuídas aos usuários por meio da Adobe Admin Console. Saiba mais em [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>A configuração de push deve ser executada por um usuário especialista. Dependendo do modelo de implementação e das pessoas envolvidas nesta implementação, talvez seja necessário atribuir o conjunto completo de permissões a um único perfil de produto ou compartilhar permissões entre o desenvolvedor do aplicativo e a **Adobe Campaign** administrador.

Para atribuir **Propriedade** e **Empresa** , siga as etapas abaixo:

1. Acesse o **[!DNL Admin Console]**.
1. No **[!UICONTROL Products]** , selecione a **[!UICONTROL Adobe Experience Platform Data Collection]** cartão.
1. Selecionar um existente **[!UICONTROL Product Profile]** ou crie um novo com o **[!UICONTROL New profile]** botão. Saiba como criar um novo **[!UICONTROL New profile]** no [Documentação do Admin Console](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. Na guia **[!UICONTROL Permissions]**, selecione **[!UICONTROL Property Rights]**.
1. Clique em **[!UICONTROL Add all]**. Isso adicionará o seguinte direito ao perfil de produto:
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   Essas permissões são necessárias para instalar e publicar a extensão do Adobe Campaign e publicar a propriedade do aplicativo no **Adobe Experience Platform Mobile SDK**.

1. Em seguida, selecione **[!UICONTROL Company rights]** no menu à esquerda.
1. Adicione os seguintes direitos:

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   Essas permissões são necessárias para que o desenvolvedor de aplicativos móveis configure credenciais de push no **Coleta de dados do Adobe Experience Platform**.

1. Clique em **[!UICONTROL Save]**.

Para atribuir este **[!UICONTROL Product profile]** Para adicionar usuários, siga as etapas abaixo:

1. Acesse o **[!DNL Admin Console]**.
1. No **[!UICONTROL Products]** , selecione a **[!UICONTROL Adobe Experience Platform Data Collection]** cartão.
1. Selecione o **[!UICONTROL Product profile]** configurado anteriormente.
1. Na guia **[!UICONTROL Users]**, clique em **[!UICONTROL Add user]**.
1. Digite o nome de usuário ou endereço de email e selecione o usuário. Em seguida, clique em **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se o usuário não tiver sido criado anteriormente no Admin Console, consulte a [Adicionar documentação de usuários](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Configurar seu aplicativo {#configure-app}

A configuração técnica envolve estreita colaboração entre o desenvolvedor do aplicativo e o administrador de negócios. Antes de começar a enviar notificações por push com [!DNL Adobe Campaign], é necessário definir as configurações em [!DNL Adobe Experience Platform Data Collection] e integre seu aplicativo móvel aos SDKs móveis da Adobe Experience Platform.

Siga as etapas de implementação detalhadas nos links abaixo:

* Para **Apple iOS**: saiba como registrar seu aplicativo com APNs no [Documentação do Apple](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* Para **Google Android**: saiba como configurar um aplicativo cliente do Firebase Cloud Messaging no Android no [Documentação do Google](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## Configurar uma propriedade de tag móvel na Coleção de dados da Adobe Experience Platform {#launch-property}

A configuração de uma propriedade móvel permite que o desenvolvedor ou profissional de marketing do aplicativo móvel configure os SDKs móveis. Normalmente, você cria uma propriedade móvel para cada aplicativo móvel que deseja gerenciar. Saiba como criar e configurar uma propriedade móvel no [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

Saiba mais sobre [!DNL Adobe Experience Platform Data Collection] tags na [Documentação do Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Depois de criada, abra a nova propriedade de tag e crie uma biblioteca. Para fazer isso:

1. Navegue até **Fluxo de publicação** na navegação à esquerda e selecione **Adicionar biblioteca**.
1. Insira o nome da biblioteca e selecione o ambiente.
1. Selecionar **Adicionar todos os recursos alterados**, e **Salvar e criar no desenvolvimento**.
1. Por fim, defina essa biblioteca como sua biblioteca de trabalho na **Selecionar uma biblioteca de trabalho** botão.

## Configurar os serviços móveis no Campaign {#push-service}

Depois que o aplicativo móvel for configurado no no [!DNL Adobe Experience Platform Data Collection], é necessário criar dois serviços (um para dispositivos iOS e um para dispositivos Android) para enviar notificações por push do **[!DNL Adobe Campaign]**.

As notificações por push são enviadas aos usuários do aplicativo por meio de um serviço dedicado. Quando os usuários instalam seu aplicativo, eles assinam esse serviço: a Adobe Campaign depende desse serviço para direcionar somente os assinantes do seu aplicativo. Neste serviço, é necessário adicionar os aplicativos iOS e Android para enviar em dispositivos iOS e Android.

Para criar um serviço para enviar notificações por push, siga as etapas abaixo:

1. Navegue até **[!UICONTROL Profiles and Targets > Services and Subscriptions]** e clique em **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. Insira um **[!UICONTROL Label]** e uma **[!UICONTROL Internal name]** e selecione um **[!UICONTROL Mobile application]** tipo.

   >[!NOTE]
   >
   >O target mapping **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** padrão é vinculado à tabela de destinatários. Para utilizar um mapeamento de alvo diferente, é necessário criar um novo e inseri-lo no campo **[!UICONTROL Target mapping]** do serviço. Saiba mais sobre target mappings em [esta página](../audiences/target-mappings.md).

1. Em seguida, use o **[!UICONTROL Add]** ícone à direita para definir os aplicativos móveis que usam este serviço.

>[!BEGINTABS]

>[!TAB iOS]

Para criar um aplicativo para dispositivos iOS, siga estas etapas:

1. Selecione **[!UICONTROL Create an iOS application]** e clique em **[!UICONTROL Next]**.

   ![](assets/new-ios-app.png){width="600" align="left"}

1. Insira o nome do aplicativo na caixa **[!UICONTROL Label]** campo.
1. (opcional) Você pode enriquecer um conteúdo de mensagem de push com alguns **[!UICONTROL Application variables]**. Eles são totalmente personalizáveis e uma parte da carga da mensagem é enviada para o dispositivo móvel.

   No exemplo abaixo, a variável **mediaURl** e **mediaExt** as variáveis são adicionadas para criar notificações por push avançadas e, em seguida, fornecem ao aplicativo a imagem que será exibida na notificação.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. Navegue até o **[!UICONTROL Subscription parameters]** para definir o mapeamento com uma extensão do **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** esquema.

1. Navegue até o **[!UICONTROL Sounds]** para definir um som a ser reproduzido. Clique em **[!UICONTROL Add]** e preencha o campo **[!UICONTROL Internal name]** que deve conter o nome do arquivo incorporado no aplicativo ou o nome do som do sistema.

1. Clique em **[!UICONTROL Next]** para configurar o aplicativo de desenvolvimento.

1. A chave de integração é específica para cada aplicativo. Ele vincula o aplicativo móvel ao Adobe Campaign.

   Certifique-se de que o mesmo **[!UICONTROL Integration key]** é definido no Adobe Campaign e no código do aplicativo por meio do SDK.

   Saiba mais em [a Documentação do desenvolvedor](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > A **[!UICONTROL Integration key]** é totalmente personalizável com o valor da string, mas precisa ser exatamente a mesma especificada no SDK.
   >
   > Não é possível usar o mesmo certificado para a versão de desenvolvimento (sandbox) e a versão de produção do aplicativo.

1. Selecione o ícone na lista suspensa **[!UICONTROL Application icon]** para personalizar o aplicativo para dispositivos móveis em seu serviço.

1. Selecione **[!UICONTROL Authentication mode]**. Dois modos estão disponíveis:

   * (Recomendado) **[!UICONTROL Token-based authentication]**: Preencha as configurações de conexão APNs **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** e **[!UICONTROL Bundle Id]** em seguida, selecione o certificado p8 clicando em **[!UICONTROL Enter the private key...]**. Para obter mais informações, **[!UICONTROL Token-based authentication]**, consulte [Documentação do Apple](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**: Clique **[!UICONTROL Enter the certificate...]**  em seguida, selecione a chave p12 e insira a senha fornecida pelo desenvolvedor de aplicativos para dispositivos móveis. Observe que este certificado vem com uma data de expiração e deve ser renovado anualmente. Para evitar uma interrupção no serviço para seus usuários, atualize seus certificados antes que expirem. Os certificados são válidos por um ano e você deve atualizá-los para continuar a se comunicar com APNs.

1. Use o **[!UICONTROL Test the connection]** botão para validar a configuração.

1. Clique em **[!UICONTROL Next]** para configurar o aplicativo de produção e siga as mesmas etapas descritas acima.

1. Clique em **[!UICONTROL Finish]**.

Seu aplicativo do iOS agora está pronto para ser usado no Campaign.

>[!TAB Android]

Para criar um aplicativo para dispositivos Android, siga estas etapas:

1. Selecione **[!UICONTROL Create an Android application]** e clique em **[!UICONTROL Next]**.

   ![](assets/new-android-app.png){width="600" align="left"}

1. Insira o nome do aplicativo na caixa **[!UICONTROL Label]** campo.
1. A chave de integração é específica para cada aplicativo. Ele vincula o aplicativo móvel ao Adobe Campaign.

   Certifique-se de que o mesmo **[!UICONTROL Integration key]** é definido no Adobe Campaign e no código do aplicativo por meio do SDK.

   Saiba mais em [a Documentação do desenvolvedor](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > A **[!UICONTROL Integration key]** é totalmente personalizável com o valor da string, mas precisa ser exatamente a mesma especificada no SDK.
   >

1. Selecione o ícone na lista suspensa **[!UICONTROL Application icon]** para personalizar o aplicativo para dispositivos móveis em seu serviço.
1. Selecionar **HTTP v1** in  **[!UICONTROL API version]** lista suspensa.
1. Clique em **[!UICONTROL Load project json file to extract project details...]** para carregar o arquivo de chave JSON. Para obter mais informações sobre como extrair o arquivo JSON, consulte [Documentação do Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   Você também pode inserir manualmente os seguintes detalhes:
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. Use o **[!UICONTROL Test the connection]** botão para validar a configuração.

   >[!CAUTION]
   >
   >A variável **[!UICONTROL Test connection]** O botão não verifica se o servidor MID tem acesso ao servidor FCM.

1. (opcional) Você pode enriquecer um conteúdo de mensagem de push com alguns **[!UICONTROL Application variables]** se necessário. Eles são totalmente personalizáveis e uma parte da carga da mensagem é enviada para o dispositivo móvel.

1. Clique em **[!UICONTROL Finish]** e em **[!UICONTROL Save]**. Seu aplicativo Android agora está pronto para ser usado no Campaign.

Abaixo estão os nomes de payload do FCM para personalizar ainda mais sua notificação por push:

| Tipo de mensagem | Elemento de mensagem configurável (nome da carga FCM) | Opções configuráveis (nome da carga do FCM) |
|:-:|:-:|:-:|
| mensagem de dados | N/D | validate_only |
| mensagem de notificação | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]

## Configurar a extensão do Adobe Campaign na sua propriedade móvel {#configure-extension}

A variável **Extensão do Adobe Campaign Classic** Os SDKs do Adobe Experience Platform Mobile capacitam as notificações por push para seus aplicativos móveis e ajudam você a coletar tokens de push do usuário e gerenciar a medição de interação com os serviços da Adobe Experience Platform.

Essa extensão, que se aplica ao Campaign Classic v7 e ao Campaign v8, é pré-instalada em seu ambiente e deve ser configurada. Para configurar a extensão para sua propriedade de tag móvel, siga estas etapas:

1. Abra a propriedade de tag criada anteriormente.
1. Na navegação à esquerda, navegue até **Extensões** e abra a variável **Catálogo** guia. Use o campo de pesquisa para localizar o **Adobe Campaign Classic** extensão.
1. No cartão Campaign Classic, clique no botão **Instalar** botão.
1. Insira as configurações conforme descrito em [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Agora você pode adicionar o Campaign ao seu aplicativo, conforme detalhado em  [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.
