---
title: Integrar o SDK da AEP e o Campaign
description: Saiba como integrar o SDK móvel do Adobe Experience Platform ao seu aplicativo
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: ff6990f3db1122670bff4919f417b9f9f04d3183
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 3%

---


# AEP SDK + Campanha: configurar canal de notificação por push {#push-notification-configuration}

Antes de começar a enviar notificações por push com o Adobe Campaign, é necessário garantir que as configurações e integrações estejam em vigor no aplicativo móvel e para tags no Adobe Experience Platform.

O Adobe Experience Platform Mobile SDK fornece APIs de integração do lado do cliente para dispositivos móveis por meio de SDKs compatíveis com Android e iOS.

Para configurar seu aplicativo com SDKs do Adobe Experience Platform Mobile, siga estas etapas:

1. Verificar [pré-requisitos](#before-starting).
1. Configure um [propriedade de tag móvel](#launch-property) na Coleta de dados do Adobe Experience Platform.
1. Obtenha o SDK do Adobe Experience Platform Mobile como detalhado [nesta página](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (opcional) Ative o registro e as medições de ciclo de vida, conforme detalhado [nesta página](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (opcional) Adicionar [Adobe Experience Platform Assurance para o seu aplicativo](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Seguir [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} para obter a configuração com os SDKs do Adobe Experience Platform Mobile em seu aplicativo.
1. Instalar e configurar [Extensão do Adobe Campaign](#configure-extension) na propriedade móvel.
1. Configure seus serviços móveis iOS e Android no Adobe Campaign, conforme detalhado [nesta página](../send/push.md#push-config).


## Pré-requisitos {#before-starting}

### Configurar permissões {#setup-permissions}

Antes de criar um aplicativo móvel, primeiro verifique se você tem ou atribui as permissões de usuário corretas para tags no Adobe Experience Platform. Permissões de usuário para tags no Adobe Experience Platform são atribuídas aos usuários por meio do Adobe Admin Console. Saiba mais em [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>A configuração de push deve ser executada por um usuário especialista. Dependendo do modelo de implementação e das pessoas envolvidas nessa implementação, talvez seja necessário atribuir o conjunto completo de permissões a um único perfil de produto ou compartilhar permissões entre o desenvolvedor do aplicativo e a **Adobe Campaign** administrador.

Para atribuir **Propriedade** e **Empresa** , siga as etapas abaixo:

1. Acesse o **[!DNL Admin Console]**.
1. No **[!UICONTROL Products]** selecione a guia **[!UICONTROL Adobe Experience Platform Data Collection]** cartão.
1. Selecione um **[!UICONTROL Product Profile]** ou criar um novo com o **[!UICONTROL New profile]** botão. Saiba como criar um novo **[!UICONTROL New profile]** no [Documentação do Admin Console](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. Na guia **[!UICONTROL Permissions]**, selecione **[!UICONTROL Property Rights]**.
1. Clique em **[!UICONTROL Add all]**. Isso adicionará o seguinte direito ao perfil de produto:
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   Essas permissões são necessárias para instalar e publicar a extensão do Adobe Campaign e publicar a propriedade do aplicativo em **Adobe Experience Platform Mobile SDK**.

1. Em seguida, selecione **[!UICONTROL Company rights]** no menu à esquerda.
1. Adicione os seguintes direitos:

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   Essas permissões são necessárias para que o desenvolvedor do aplicativo móvel configure credenciais de push em **Coleta de dados do Adobe Experience Platform**.

1. Clique em **[!UICONTROL Save]**.

Para atribuir isso **[!UICONTROL Product profile]** para os usuários, siga as etapas abaixo:

1. Acesse o **[!DNL Admin Console]**.
1. No **[!UICONTROL Products]** selecione a guia **[!UICONTROL Adobe Experience Platform Data Collection]** cartão.
1. Selecione o **[!UICONTROL Product profile]** configurado anteriormente.
1. Na guia **[!UICONTROL Users]**, clique em **[!UICONTROL Add user]**.
1. Digite o nome do usuário ou endereço de email e selecione o usuário. Em seguida, clique em **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se o usuário não tiver sido criado anteriormente no Admin Console, consulte [Adicionar documentação de usuários](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Configurar seu aplicativo {#configure-app}

A configuração técnica envolve uma estreita colaboração entre o desenvolvedor do aplicativo e o administrador comercial. Antes de começar a enviar notificações por push com [!DNL Adobe Campaign], é necessário definir as configurações em [!DNL Adobe Experience Platform Data Collection] e integrar seu aplicativo móvel com os SDKs do Adobe Experience Platform Mobile.

Siga as etapas de implementação detalhadas nos links abaixo:

* Para **Apple iOS**: Saiba como registrar seu aplicativo com APNs em [Documentação do Apple](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* Para **Google Android**: Saiba como configurar um aplicativo cliente Firebase Cloud Messaging no Android em [Documentação do Google](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

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

## Configurar uma propriedade de tag móvel na Coleta de dados do Adobe Experience Platform {#launch-property}

A configuração de uma propriedade móvel permite que o desenvolvedor do aplicativo móvel ou profissional de marketing configure os SDKs móveis. Normalmente, você cria uma propriedade móvel para cada aplicativo móvel que deseja gerenciar. Saiba como criar e configurar uma propriedade móvel no [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

Saiba mais sobre [!DNL Adobe Experience Platform Data Collection] tags em [Documentação do Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Depois de criada, abra a nova propriedade de tag e crie uma biblioteca. Para fazer isso:

1. Navegue até **Fluxo de publicação** no painel de navegação esquerdo e selecione **Adicionar biblioteca**.
1. Insira o nome da biblioteca e selecione o ambiente .
1. Selecionar **Adicionar todos os recursos alterados** e **Salvar e criar no desenvolvimento**.
1. Por fim, defina essa biblioteca como a biblioteca de trabalho do **Selecionar uma biblioteca de trabalho** botão.


## Configurar a extensão Adobe Campaign na propriedade móvel {#configure-extension}

O **Extensão do Adobe Campaign Classic** para SDKs do Adobe Experience Platform Mobile, o aciona notificações por push para aplicativos móveis e ajuda a coletar tokens por push do usuário e gerencia a medição de interação com os serviços da Adobe Experience Platform.

Essa extensão, que se aplica ao Campaign Classic v7 e Campaign v8, é pré-instalada em seu ambiente e deve ser configurada. Para configurar a extensão para sua propriedade de tag móvel, siga estas etapas:

1. Abra a propriedade da tag criada anteriormente.
1. Na navegação à esquerda, navegue até **Extensões** e abra o **Catálogo** guia . Use o campo de pesquisa para localizar o **Adobe Campaign Classic** extensão.
1. No cartão Campaign Classic, clique no botão **Instalar** botão.
1. Insira as configurações conforme descrito em [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Agora é possível adicionar o Campaign ao seu aplicativo, conforme detalhado em  [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Configurar seus serviços móveis no Campaign{#push-service}

Depois que seu aplicativo móvel é configurado em [!DNL Adobe Experience Platform Data Collection], é necessário criar dois serviços (um para dispositivos iOS, um para dispositivos Android) para enviar notificações por push do **[!DNL Adobe Campaign]**.

Saiba como criar e configurar um serviço para notificações por push do iOS e Android em [esta seção](../send/push.md#push-config).
