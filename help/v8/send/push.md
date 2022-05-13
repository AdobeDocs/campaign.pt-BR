---
title: Enviar notificação por push com o Adobe Campaign
description: Introdução à notificação por push no Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 29%

---

# Criar e enviar notificações por push

Os deliveries de aplicativos móveis permitem enviar notificações para sistemas iOS e Android.

Para enviar notificações por push no Adobe Campaign, é necessário:

1. Configurar o ambiente do Campaign
1. Crie um serviço de informações do tipo aplicativo móvel para seu aplicativo móvel.
1. Adicione as versões iOS e Android do aplicativo a este serviço.
1. Crie um delivery para iOS e Android.

![](../assets/do-not-localize/book.png) Saiba como começar a usar o aplicativo móvel no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html){target=&quot;_blank&quot;}

## Integrar SDK do Campaign

O SDK do Campaign facilita a integração do aplicativo móvel na plataforma Adobe Campaign.

Versões compatíveis do SDK são listadas em [Matriz de compatibilidade de campanha](../start/compatibility-matrix.md#MobileSDK).

![](../assets/do-not-localize/glass.png) Saiba como integrar SDKs do Campaign Android e iOS ao seu aplicativo em [esta seção](../config/push-config.md)

<!--
### Configure Campaign Extension in Launch

You can integrate Adobe Experience Platorm Launch SDK with Campaign, by leveraging Campaign Classic extension.

![](../assets/do-not-localize/book.png) Learn more in [Adobe Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target="_blank"}

-->

## Definir as configurações do aplicativo no Campaign

Você deve definir as configurações dos aplicativos iOS e Android no Adobe Campaign.

![](../assets/do-not-localize/book.png) As diretrizes de configuração do iOS estão detalhadas em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=pt-BR#sending-messages){target=&quot;_blank&quot;}

![](../assets/do-not-localize/book.png) As diretrizes de configuração do Android estão detalhadas em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages){target=&quot;_blank&quot;}

## Criar sua primeira notificação por push

Esta seção detalha os elementos específicos para o delivery de notificações iOS e Android.

>[!CAUTION]
>
>No contexto de um [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), o registro móvel agora é **assíncrono**. [Saiba mais](../architecture/staging.md)

Para criar um novo delivery, navegue até o **[!UICONTROL Campaigns]** clique em **[!UICONTROL Deliveries]** e clique no botão **[!UICONTROL Create]** acima da lista de deliveries existentes.

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) Para obter informações globais sobre como criar um delivery, consulte [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### Enviar notificações no iOS {#send-notifications-on-ios}

>[!NOTE]
>
>Esse recurso está disponível a partir do Campaign v8.3. Para verificar sua versão, consulte [esta seção](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

1. Selecione o modelo de delivery **[!UICONTROL Deliver on iOS]**.

   ![](assets/push_ios_1.png)

1. Para definir o target da notificação, clique no link **[!UICONTROL To]** e, em seguida, clique em **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. Selecionar **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, selecione o serviço relevante para o aplicativo móvel e selecione a versão iOS do aplicativo.

   ![](assets/push_ios_3.png)

1. Escolha sua **[!UICONTROL Notification type]** entre **[!UICONTROL General notification (Alert, Sound, Badge)]** ou **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >O modo **Push silencioso** permite que uma notificação &quot;silenciosa&quot; seja enviada a um aplicativo móvel. O usuário não está ciente da chegada da notificação. Ele é transferido diretamente para o aplicativo.

1. No **[!UICONTROL Title]** , insira o rótulo do título que deve aparecer na lista de notificações disponíveis no centro de notificações.

   Este campo permite a definição do valor do parâmetro **title** da carga de notificação iOS.

1. Você pode adicionar uma **[!UICONTROL Subtitle]**, valor da variável **subtítulo** parâmetro da carga de notificação do iOS.

1. Insira o conteúdo da mensagem na seção **[!UICONTROL Message content]** do assistente.

1. No **[!UICONTROL Sound and Badge]** , é possível editar as seguintes opções:

   * **[!UICONTROL Clean Badge]**: habilite essas opções para atualizar o valor do selo.

   * **[!UICONTROL Value]**: defina um número que será usado para exibir diretamente no ícone do aplicativo o número de novas informações não lidas.

   * **[!UICONTROL Critical alert mode]**: habilite esta opção para adicionar som à sua notificação, mesmo que o telefone do usuário esteja configurado no modo de foco ou se o iPhone estiver sem áudio.

   * **[!UICONTROL Name]**: selecione o som a ser reproduzido pelo terminal móvel quando a notificação for recebida.

   * **[!UICONTROL Volume]**: volume do seu som de 0 a 100.

      >[!NOTE]
      > 
      >Os sons devem ser incluídos no aplicativo e definidos quando o serviço for criado.
      >
      >As diretrizes de configuração do iOS estão detalhadas em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en).
   ![](assets/push_ios_5.png)

1. No **[!UICONTROL Application variables]** guia , sua **[!UICONTROL Application variables]** são adicionadas automaticamente. Eles permitem definir o comportamento de notificação, por exemplo, você pode configurar uma tela de aplicativo específica a ser exibida quando o usuário ativar a notificação.

   Para obter mais informações, consulte [esta seção](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en).

1. No **[!UICONTROL Advanced]** , é possível editar as seguintes opções gerais:

   * **[!UICONTROL Mutable content]**: habilite esta opção para permitir que o aplicativo móvel baixe conteúdo de mídia.

   * **[!UICONTROL Thread-id]**: identificador usado para agrupar notificações relacionadas.

   * **[!UICONTROL Category]**: nome da ID da categoria que exibirá botões de ação. Essas notificações fornecem ao usuário uma maneira mais rápida de realizar tarefas diferentes em resposta a uma notificação sem abrir o aplicativo ou navegar até ele.

   ![](assets/push_ios_6.png)

1. Para notificações sensíveis ao tempo, é possível especificar as seguintes opções:

   * **[!UICONTROL Target content ID]**: identificador usado para direcionar qual janela de aplicativo apresentar quando a notificação for aberta.

   * **[!UICONTROL Launch image]**: nome do arquivo de imagem de lançamento a ser exibido. Se o usuário optar por iniciar seu aplicativo, a imagem selecionada será exibida em vez da tela de inicialização do aplicativo.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: Definido por padrão, o sistema apresenta a notificação imediatamente, acende a tela e pode reproduzir um som. As notificações não percorrem os modos Foco.

      * **[!UICONTROL Passive]**: O sistema adiciona a notificação à lista de notificação sem acender a tela ou reproduzir um som. As notificações não percorrem os modos Foco.

      * **[!UICONTROL Time sensitive]** O sistema apresenta a notificação imediatamente, acende a tela, pode reproduzir um som e quebrar os modos de foco. Esse nível não requer uma permissão especial da Apple.

      * **[!UICONTROL Critical]** O sistema apresenta a notificação imediatamente, acende a tela e ignora os modos mudo ou foco. Observe que esse nível requer uma permissão especial da Apple.
   * **[!UICONTROL Relevance score]**: defina uma pontuação de relevância de 0 a 100. O sistema usa essa opção para classificar as notificações no resumo da notificação.

   ![](assets/push_ios_7.png)

1. Quando a notificação estiver configurada, clique na guia **[!UICONTROL Preview]** para visualizar a notificação.

   ![](assets/push-ios-preview.png)

### Enviar notificações no Android {#send-notifications-on-android}

1. Selecione o modelo de delivery **[!UICONTROL Deliver on Android (android)]**.

   ![](assets/push-template-android.png)

1. Para definir o target da notificação, clique no link **[!UICONTROL To]** e, em seguida, clique em **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Selecione **[!UICONTROL Subscribers of an Android mobile application]**, escolha o serviço relevante para seu aplicativo móvel (Neotrips, neste caso) e selecione a versão Android do aplicativo.

   ![](assets/push-android-subscribers.png)

1. Em seguida, insira o conteúdo da notificação.

   ![](assets/push-android-content.png)

1. Clique no ícone **[!UICONTROL Insert emoticon]** para inserir emoticons à notificação via push.

1. No campo **[!UICONTROL Application variables]**, insira o valor de cada variável. Por exemplo, você pode configurar uma tela de aplicativo específica a ser exibida quando o usuário ativar a notificação.

1. Quando a notificação estiver configurada, clique na guia **[!UICONTROL Preview]** para visualizar a notificação.

   <!--![](assets/push-android-preview.png)-->

## Teste, envie e monitore suas notificações por push

Para enviar uma prova e o delivery final, use o mesmo processo que os deliveries de email. Saiba mais na documentação do Campaign Classic v7:

* Validar um delivery e enviar provas
   ![](../assets/do-not-localize/book.png) [Saiba mais sobre as principais etapas para validar um delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=pt-BR){target=&quot;_blank&quot;}

* Confirmar e enviar o delivery
   ![](../assets/do-not-localize/book.png) [Saiba mais sobre as principais etapas para enviar um delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en){target=&quot;_blank&quot;}

Após enviar as mensagens, você pode monitorar e rastrear seus deliveries. Saiba mais na documentação do Campaign Classic v7:

* Quarentenas de notificação por push
   ![](../assets/do-not-localize/book.png) [Saiba mais sobre a quarentena de notificações por push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines){target=&quot;_blank&quot;}

* Solução de problemas
   ![](../assets/do-not-localize/book.png) [Saiba como solucionar problemas de notificações por push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en){target=&quot;_blank&quot;}
