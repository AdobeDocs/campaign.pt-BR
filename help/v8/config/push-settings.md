---
title: Integrar o SDK da AEP e o Campaign
description: Saiba como integrar o SDK móvel do Adobe Experience Platform ao seu aplicativo
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e3ea361cc486096fe6c19ac469e8a71b636371ac
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 3%

---


# AEP SDK + Campanha: configurar canal de notificação por push {#push-notification-configuration}

Antes de começar a enviar notificações por push com o Adobe Campaign, é necessário garantir que as configurações e integrações estejam em vigor no aplicativo móvel e para tags no Adobe Experience Platform...... .... ....


## Antes de começar {#before-starting}

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

### Integrar seu aplicativo móvel ao SDK do Adobe Experience Platform {#integrate-mobile-app}

O Adobe Experience Platform Mobile SDK fornece APIs de integração do lado do cliente para dispositivos móveis por meio de SDKs compatíveis com Android e iOS. Seguir [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} para obter a configuração com os SDKs do Adobe Experience Platform Mobile em seu aplicativo.

Ao final disso, você também deve ter criado e configurado uma propriedade móvel no [!DNL Adobe Experience Platform Data Collection]. Normalmente, você cria uma propriedade móvel para cada aplicativo móvel que deseja gerenciar. Saiba como criar e configurar uma propriedade móvel no [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.


## Etapa 1: Adicionar suas credenciais de push do aplicativo na Coleta de dados do Adobe Experience Platform {#push-credentials}

Após conceder as permissões de usuário corretas, agora é necessário adicionar suas credenciais de push do aplicativo móvel na Coleta de dados do Adobe Experience Platform.

O registro de credenciais de push do aplicativo móvel é necessário para autorizar o Adobe a enviar notificações por push em seu nome. Consulte as etapas detalhadas abaixo:

1. De [!DNL Adobe Experience Platform Data Collection], navegue até **[!UICONTROL App Surfaces]** no painel esquerdo.

1. Clique em **[!UICONTROL Create App Surface]** para criar uma nova configuração.

1. Insira um **[!UICONTROL Name]** para a configuração.

1. De **[!UICONTROL Mobile Application Configuration]**, selecione o Sistema operacional:

   * **Para iOS**

      1. Insira o aplicativo móvel **ID do pacote** no **[!UICONTROL App ID (iOS Bundle ID)]** campo. A ID do pacote de aplicativos pode ser encontrada no **Geral** da meta principal em **XCode**.

      1. Ligado o **[!UICONTROL Push Credentials]** para adicionar suas credenciais.

      1. Arraste e solte seu arquivo .p8 Chave de autenticação de notificação por push do Apple. Essa chave pode ser adquirida do **Certificados**, **Identificadores** e **Perfis** página.

      1. Forneça a **Key ID**. Esta é uma string de 10 caracteres atribuída durante a criação da chave de autenticação p8. Pode ser encontrado em **Teclas** em **Certificados**, **Identificadores** e **Perfis** página.

      1. Forneça a **ID do grupo**. Este é um valor de string que pode ser encontrado na guia Membership .
   * **Para Android**

      1. Forneça a **[!UICONTROL App ID (Android package name)]**: geralmente, o nome do pacote é a id do aplicativo em seu `build.gradle` arquivo.

      1. Ligado o **[!UICONTROL Push Credentials]** para adicionar suas credenciais.

      1. Arraste e solte as credenciais de push do FCM. Para obter mais detalhes sobre como obter as credenciais de push, consulte [Documentação do Google](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.



1. Clique em **[!UICONTROL Save]** para criar a configuração do seu aplicativo.


## Etapa 2: Configurar uma propriedade de tag móvel na Coleta de dados do Adobe Experience Platform {#launch-property}

A configuração de uma propriedade móvel permite que o desenvolvedor do aplicativo móvel ou profissional de marketing configure os atributos de SDKs móveis, como Tempo limite da sessão, o [!DNL Adobe Experience Platform] sandbox a ser direcionada e a variável **[!UICONTROL Adobe Experience Platform Datasets]** a ser usado para o SDK móvel para enviar dados ao .

Para mais detalhes e procedimentos sobre como configurar um **propriedade móvel** , consulte as etapas detalhadas em [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

Para obter os SDKs necessários para que a notificação por push funcione, você precisará das seguintes extensões do SDK, tanto para Android quanto para iOS:

* **[!UICONTROL Mobile Core]** (instalado automaticamente)
* **[!UICONTROL Profile]** (instalado automaticamente)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, opcional, mas recomendado para depurar a implementação móvel.

Saiba mais sobre [!DNL Adobe Experience Platform Data Collection] tags em [Documentação do Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Depois de criada, abra a nova propriedade de tag e crie uma biblioteca. Para fazer isso:

1. Navegue até **Fluxo de publicação** no painel de navegação esquerdo e selecione **Adicionar biblioteca**.
1. Insira o nome da biblioteca e selecione o ambiente .
1. Selecionar **Adicionar todos os recursos alterados** e **Salvar e criar no desenvolvimento**.
1. Por fim, defina essa biblioteca como a biblioteca de trabalho do **Selecionar uma biblioteca de trabalho** botão.


## Etapa 3: Configurar a extensão Adobe Campaign na propriedade móvel {#configure-extension}

O **Extensão do Adobe Campaign Classic** para SDKs do Adobe Experience Platform Mobile, o aciona notificações por push para aplicativos móveis e ajuda a coletar tokens por push do usuário e gerencia a medição de interação com os serviços da Adobe Experience Platform.

Essa extensão é pré-instalada em seu ambiente e deve ser configurada. Para configurar a extensão para sua propriedade de tag móvel, siga estas etapas:

1. Abra a propriedade da tag criada anteriormente.
1. Na navegação à esquerda, navegue até **Extensões** e abra o **Catálogo** guia . Use o campo de pesquisa para localizar o **Adobe Campaign Classic** extensão.
1. No cartão Campaign Classic, clique no botão **Instalar** botão.
1. Insira as configurações conforme descrito em [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Agora é possível adicionar o Campaign ao seu aplicativo, conforme detalhado em  [Documentação do SDK do Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Etapa 4: Configurar seus serviços móveis no Campaign{#push-service}

Depois que seu aplicativo móvel é configurado em [!DNL Adobe Experience Platform Data Collection], é necessário criar dois serviços (um para dispositivos iOS, um para dispositivos Android) para enviar notificações por push do **[!DNL Adobe Campaign]**.

Saiba como criar e configurar um serviço para notificações por push do iOS e Android em [esta seção](../send/push.md#push-config).
