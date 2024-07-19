---
title: Enviar notificação por push com o Adobe Campaign
description: Introdução à notificação por push no Campaign
feature: Push
role: Data Engineer
level: Intermediate
badge: label="Disponibilidade limitada" type="Informative"
exl-id: 0f22b17c-ed01-4add-8300-8689b8a9f963
source-git-commit: 1fb93efac4fee4965213f8b42f518f2c10638e20
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 17%

---

# Configuração de notificação por push revisada {#push-notifications-config}

O Campaign v8.5 está apresentando nosso serviço de notificação por push mais recente, alimentado por uma estrutura robusta criada em uma tecnologia de ponta moderna. Este serviço foi projetado para desbloquear novos níveis de escalabilidade, garantindo que suas notificações possam alcançar um público maior com eficiência contínua. Com nossa infraestrutura aprimorada e nossos processos otimizados, você pode esperar maior escala e confiabilidade, permitindo que você interaja e se conecte com seus usuários de aplicativos móveis como nunca.

>[!AVAILABILITY]
>
> Esse recurso é acessível exclusivamente a novos clientes a partir do Campaign v8.5 e implantado progressivamente em um conjunto de clientes selecionados. Se seu ambiente foi provisionado antes de junho de 2023, esta página não se aplica a você e você deve seguir os procedimentos detalhados [nesta página](push-settings.md).

No contexto desta implementação atualizada, para enviar notificações por push no Adobe Campaign, siga estas etapas:

1. [Criar uma superfície de aplicativo na coleção de dados do Adobe Experience Platform](#create-app-surface)

1. [Definir as configurações do aplicativo no Adobe Campaign](#push-config-campaign)

1. [Criar e configurar uma propriedade móvel na Coleção de dados da Adobe Experience Platform](#create-mobile-property)

1. [Adicionar extensão do Adobe Adobe Experience Platform Assurance](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}(recomendado)

1. [Adicionar o Campaign Classic ao seu aplicativo para dispositivos móveis](#campaign-mobile-ap)

1. [Criar um delivery para o iOS e o Android](##push-create)

>[!NOTE]
>
> O FCM e o APNS p12 herdados não são compatíveis com a Coleção de dados.

## Criar uma superfície de aplicativo na coleção de dados do Adobe Experience Platform {#create-app-surface}

Você precisa adicionar suas credenciais de push do aplicativo móvel em [!DNL Adobe Experience Platform Data Collection].

O registro da credencial de push do aplicativo móvel é necessário para autorizar o Adobe a enviar notificações por push em seu nome. Consulte as etapas detalhadas abaixo:

1. Em [!DNL Adobe Experience Platform Data Collection], selecione a guia **[!UICONTROL App Surfaces]** no painel esquerdo.

1. Clique em **[!UICONTROL Create App Surface]** para criar uma nova configuração.

   ![](assets/push-config-1.png)

1. Insira um **[!UICONTROL Name]** para a configuração.

1. Em **[!UICONTROL Mobile Application Configuration]**, selecione o Sistema operacional:

   * **Para iOS**

     ![](assets/push-config-2.png)

      1. Insira a **Id do Pacote** do aplicativo móvel no campo **[!UICONTROL App ID (iOS Bundle ID)]**.

         A ID do Pacote de aplicativos pode ser encontrada na guia **Geral** do destino principal em **XCode** da sua conta de desenvolvedor do Apple.

      1. Ative **[!UICONTROL Push Credentials]** para adicionar suas credenciais.

      1. Arraste e solte seu arquivo .p8 Apple Push Notification Authentication Key.

         Esta chave pode ser adquirida nas páginas **Certificados**, **Identificadores** e **Perfis** da sua conta de desenvolvedor do Apple.

      1. Forneça a **Key ID**. Esta é uma sequência de 10 caracteres atribuída durante a criação da chave de autenticação p8.

         Ele pode ser encontrado na guia **Chaves** da página **Certificados**, **Identificadores** e **Perfis** da sua conta de desenvolvedor do Apple.

      1. Forneça a **ID da Equipe**. Este é um valor de cadeia de caracteres que pode ser encontrado na guia **Associação**.

   * **Para Android**

     ![](assets/push-config-3.png)

      1. Forneça o **[!UICONTROL App ID (Android package name)]**. Normalmente, o nome do pacote é a ID do aplicativo no arquivo `build.gradle`.

      1. Alterne **[!UICONTROL Push Credentials]** para adicionar suas credenciais.

      1. Arraste e solte as credenciais de push do FCM. Para obter mais detalhes sobre como obter as credenciais de push, consulte a [Documentação do Google](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

1. Clique em **[!UICONTROL Save]** para criar sua configuração de aplicativo.

## Definir as configurações do aplicativo no Adobe Campaign{#push-config-campaign}

### Criar um serviço {#create-service}

Antes de enviar notificações por push, você deve definir as configurações de aplicativos iOS e Android no Adobe Campaign.

As notificações por push são enviadas aos usuários do aplicativo por meio de um serviço dedicado. Quando os usuários instalam seu aplicativo, eles assinam esse serviço: a Adobe Campaign depende desse serviço para direcionar somente os assinantes do seu aplicativo. Neste serviço, é necessário adicionar os aplicativos iOS e Android para enviar em dispositivos iOS e Android.

Para criar um serviço para enviar notificações por push, siga as etapas abaixo:

1. Navegue até a guia **[!UICONTROL Profiles and Targets > Services and Subscriptions]** e clique em **[!UICONTROL Create]**.

   ![](assets/push-config-4.png){width="800" align="left"}

1. Insira um **[!UICONTROL Label]** e um **[!UICONTROL Internal name]**, e selecione um tipo **[!UICONTROL Mobile application]**.

   >[!NOTE]
   >
   >O target mapping **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** padrão é vinculado à tabela de destinatários. Para utilizar um mapeamento de alvo diferente, é necessário criar um novo e inseri-lo no campo **[!UICONTROL Target mapping]** do serviço. Saiba mais sobre target mappings em [esta página](../audiences/target-mappings.md).

1. Em seguida, use o ícone **[!UICONTROL Add]** à direita para definir os aplicativos móveis que usam esse serviço.

   ![](assets/push-config-5.png)

### Criar um aplicativo para dispositivos móveis {#create-sapp}

Depois de criar o serviço, é necessário definir os aplicativos móveis que usarão esse serviço.

>[!BEGINTABS]

>[!TAB iOS]

Para criar um aplicativo para dispositivos iOS, siga estas etapas:

1. Em seu Serviço, clique em **[!UICONTROL Add]** e selecione **[!UICONTROL Create an iOS application]**. Clique em **[!UICONTROL Next]**.

   ![](assets/push-config-6.png)

1. Na janela **[!UICONTROL Launch app configurations list]**, selecione a superfície App criada anteriormente nesta seção. Clique em **[!UICONTROL Next]**.

   ![](assets/push-config-7.png)

1. (opcional) Você pode enriquecer um conteúdo de mensagem de push com alguns **[!UICONTROL Application variables]**. Eles são totalmente personalizáveis e uma parte da carga da mensagem é enviada para o dispositivo móvel.

   No exemplo abaixo, as variáveis **mediaURl** e **mediaExt** são adicionadas para criar notificações por push avançadas e, em seguida, fornecem ao aplicativo a imagem que será exibida na notificação.

   ![](assets/push-config-8.png)

1. Navegue até a guia **[!UICONTROL Subscription parameters]** para definir o mapeamento com uma extensão do esquema **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]**.

1. Navegue até a guia **[!UICONTROL Sounds]** para definir um som a ser reproduzido. Clique em **[!UICONTROL Add]** e preencha o campo **[!UICONTROL Internal name]** que deve conter o nome do arquivo incorporado no aplicativo ou o nome do som do sistema.

1. Clique em **[!UICONTROL Next]** para configurar o aplicativo de desenvolvimento.

1. O **[!UICONTROL Integration key]** é específico para cada aplicativo. Ele vincula o aplicativo móvel ao Adobe Campaign e será usado ao configurar a extensão do Campaign.

   Verifique se o mesmo **[!UICONTROL Integration key]** está definido no Adobe Campaign e no código do aplicativo por meio do SDK.

   Saiba mais em [a Documentação para desenvolvedores](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > A **[!UICONTROL Integration key]** é totalmente personalizável com o valor da string, mas precisa ser exatamente a mesma especificada no SDK.
   >
   > Não é possível usar o mesmo certificado para a versão de desenvolvimento (sandbox) e a versão de produção do aplicativo.

   ![](assets/push-config-9.png)

1. Selecione o ícone do campo **[!UICONTROL Application icon]** para personalizar o aplicativo para dispositivos móveis em seu serviço.

1. Clique em **[!UICONTROL Next]** para configurar o aplicativo de produção e siga as mesmas etapas descritas acima. Observe que você não pode usar o mesmo **[!UICONTROL Integration key]** para a versão de desenvolvimento (sandbox) e a versão de produção do aplicativo.

1. Clique em **[!UICONTROL Finish]**.

Seu aplicativo do iOS agora está pronto para ser usado no Campaign.

>[!TAB Android]

Para criar um aplicativo para dispositivos Android, siga estas etapas:

1. Em seu Serviço, clique em **[!UICONTROL Add]** e selecione **[!UICONTROL Create an Android application]**. Clique em **[!UICONTROL Next]**.

   ![](assets/push-config-10.png)

1. Na janela **[!UICONTROL Launch app configurations list]**, selecione a superfície de Aplicativo criada nesta seção e clique em **[!UICONTROL Next]**.

   ![](assets/push-config-11.png)

1. A chave de integração é específica para cada aplicativo. Ele vincula o aplicativo móvel ao Adobe Campaign e será usado ao configurar a extensão do Campaign.

   Verifique se o mesmo **[!UICONTROL Integration key]** está definido no Adobe Campaign e no código do aplicativo por meio do SDK.

   Saiba mais em [a Documentação para desenvolvedores](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}

   >[!NOTE]
   >
   > A **[!UICONTROL Integration key]** é totalmente personalizável com o valor da string, mas precisa ser exatamente a mesma especificada no SDK.

   ![](assets/push-config-12.png)

1. Selecione o ícone do campo **[!UICONTROL Application icon]** para personalizar o aplicativo para dispositivos móveis em seu serviço.

1. (opcional) Você pode enriquecer um conteúdo de mensagem de push com alguns **[!UICONTROL Application variables]** se necessário. Eles são totalmente personalizáveis e uma parte da carga da mensagem é enviada para o dispositivo móvel.

1. Navegue até a guia **[!UICONTROL Subscription parameters]** para definir o mapeamento com uma extensão do esquema **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]**.

1. Clique em **[!UICONTROL Finish]** e em **[!UICONTROL Save]**.

Seu aplicativo do Android agora está pronto para ser usado no Campaign.

>[!ENDTABS]

Abaixo estão os nomes de payload do FCM para personalizar ainda mais sua notificação por push:

| Tipo de mensagem | Elemento de mensagem configurável (nome da carga FCM) | Opções configuráveis (nome da carga do FCM) |
|:-:|:-:|:-:|
| mensagem de dados | N/D | validate_only |
| mensagem de notificação | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |

## Configurar uma propriedade móvel na Coleção de dados do Adobe Experience Platform {#create-mobile-property}

1. Na página inicial da Coleção de dados, acesse o menu Tags.

1. Clique em **[!UICONTROL New Property]**.

   ![](assets/push-config-13.png)

1. Digite um nome para a propriedade e selecione **[!UICONTROL Mobile]** como plataforma.

   ![](assets/push-config-14.png)

1. Clique em **[!UICONTROL Save]** para criar a propriedade móvel.

1. Acesse a propriedade móvel recém-criada.

1. No painel de propriedades móveis, acesse o menu **[!UICONTROL Extensions]** e depois a guia **[!UICONTROL Catalog]**.

   ![](assets/push-config-15.png)

1. Instale a extensão **[!DNL Adobe Campaign Classic]**. [Saiba mais sobre a extensão do Campaign](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configure-campaign-classic-extension)

   ![](assets/push-config-16.png)

1. Preencha os detalhes da instância:

   * As URLs **[!UICONTROL Registration endpoint]** ou **[!UICONTROL Tracking endpoint]** podem ser encontradas no menu **[!UICONTROL Tools]** > **[!UICONTROL Advanced]** > **[!UICONTROL Deployment wizard]** no Campaign.
   * **[!UICONTROL Integration keys]** pode ser encontrado no aplicativo móvel configurado em [esta seção](#create-app).

   ![](assets/push-config-17.png)

1. Clique em **[!UICONTROL Save]**.

1. Agora, você precisa publicar a configuração do menu **[!UICONTROL Publishing flow]**. [Saiba mais](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

Sua propriedade móvel agora será sincronizada automaticamente com o fluxo de trabalho técnico do **[!UICONTROL Adobe Experience Platform Data Collection]**. [Saiba mais](../../automation/workflow/technical-workflows.md#list-technical-workflows)

## Adicionar o Campaign Classic ao seu aplicativo para dispositivos móveis {#campaign-mobile-app}

O SDK móvel da Adobe Experience Platform ajuda a potencializar as soluções e os serviços da Adobe Experience Cloud em seus aplicativos móveis. A configuração dos SDKs é gerenciada por meio da interface da Coleção de dados, para oferecer configuração flexível e integrações extensíveis baseadas em regras.

[Saiba mais na documentação do Adobe Developer](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}

## Criar sua notificação por push{#push-create}

Depois de configurar com êxito o aplicativo móvel na Coleção de dados, você pode criar e enviar notificações por push no Adobe Campaign.

Consulte [esta página](push.md#push-create) para obter os elementos detalhados específicos da entrega de notificações do iOS e do Android.
