---
title: Enviar notificação por push com o Adobe Campaign
description: Introdução à notificação por push no Campaign
feature: Push
role: User
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 6d54f072ad0e67b435cd6e03433fa9ddd0794dea
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 67%

---

# Criar e enviar notificações por push{#push-notifications-create}

Os deliveries por aplicativos móveis permitem enviar notificações para dispositivos iOS e Android.

Antes de começar a enviar notificações por push com o Adobe Campaign, é necessário garantir que as configurações e integrações estejam em vigor no aplicativo móvel e para tags na Adobe Experience Platform. [Saiba mais sobre configuração de push.](push-settings.md)

>[!CAUTION]
>
>Algumas alterações importantes no serviço Firebase Cloud Messaging (FCM) para Android serão lançadas em 2024 e poderão afetar sua implementação do Adobe Campaign. A configuração dos serviços de assinatura para mensagens por push no Android pode precisar ser atualizada para oferecer suporte a essa alteração. É recomendado verificar isso antecipadamente e tomar as devidas ações. [Saiba mais](../../technotes/upgrades/push-technote.md).


## Criar sua primeira notificação por push{#push-create}

Esta seção detalha os elementos específicos para o delivery de notificações iOS e Android.

>[!IMPORTANT]
>
>No contexto de um [Implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), o registro móvel agora é **assíncrono**. [Saiba mais](../architecture/staging.md)

Para criar um novo delivery, navegue até o **[!UICONTROL Campaigns]** clique em **[!UICONTROL Deliveries]** e clique no link **[!UICONTROL Create]** acima da lista de deliveries existentes.

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

Para enviar notificações em dispositivos iOS, siga estas etapas:

1. Selecione o modelo de entrega **[!UICONTROL Deliver on iOS]**.

   ![](assets/push_ios_1.png)

1. Para definir o target da notificação, clique no link **[!UICONTROL To]** e, em seguida, clique em **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. Selecionar **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, selecione o serviço relevante para seu aplicativo móvel e selecione a versão iOS do aplicativo.

   ![](assets/push_ios_3.png)

1. Escolha seu **[!UICONTROL Notification type]**: **[!UICONTROL General notification (Alert, Sound, Badge)]** ou **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >O modo **Push silencioso** permite que uma notificação &quot;silenciosa&quot; seja enviada a um aplicativo móvel. O usuário não está ciente da chegada da notificação. Ele é transferido diretamente para o aplicativo.

1. No campo **[!UICONTROL Title]**, insira o rótulo do título que deve aparecer na lista de notificações disponível no centro de notificações.

   Este campo permite a definição do valor do parâmetro **title** do conteúdo de notificação do iOS.

1. Você pode adicionar um **[!UICONTROL Subtitle]**, valor de **subtítulo** parâmetro da carga de notificação do iOS.

1. Insira o conteúdo da mensagem nas **[!UICONTROL Message content]** seção do assistente.

1. Na guia **[!UICONTROL Sound and Badge]**, é possível editar as seguintes opções:

   * **[!UICONTROL Clean Badge]**: ative essas opções para atualizar o valor do selo.

   * **[!UICONTROL Value]**: defina um número que será usado para exibir o número de novas informações não lidas diretamente no ícone do aplicativo.

   * **[!UICONTROL Critical alert mode]**: ative essa opção para adicionar som à sua notificação, mesmo que o telefone do usuário esteja configurado no modo de foco ou se o iPhone estiver sem áudio.

   * **[!UICONTROL Name]**: selecione o som a ser reproduzido pelo terminal móvel quando a notificação for recebida.

   * **[!UICONTROL Volume]**: volume do som, de 0 a 100.

     >[!NOTE]
     > 
     >Os sons devem ser incluídos no aplicativo e definidos quando o serviço é criado.
     >

   ![](assets/push_ios_5.png)

1. Na guia **[!UICONTROL Application variables]**, suas **[!UICONTROL Application variables]** são adicionadas automaticamente. Elas permitem definir o comportamento da notificação: por exemplo, é possível configurar uma tela de aplicativo específica para ser exibida quando o usuário ativar a notificação.

1. Na guia **[!UICONTROL Advanced]**, é possível editar as seguintes opções gerais:

   * **[!UICONTROL Mutable content]**: habilite essa opção para permitir que o aplicativo móvel baixe conteúdo de mídia.

   * **[!UICONTROL Thread-id]**: identificador usado para agrupar notificações relacionadas.

   * **[!UICONTROL Category]**: nome da ID da categoria que exibirá botões de ação. Essas notificações fornecem ao usuário uma maneira mais rápida de realizar tarefas diferentes em resposta a uma notificação sem abrir o aplicativo ou navegar até ele.

   ![](assets/push_ios_6.png)

1. Para notificações sensíveis ao tempo, é possível especificar as seguintes opções:

   * **[!UICONTROL Target content ID]**: identificador usado para definir qual janela de aplicativo será apresentada quando a notificação for aberta.

   * **[!UICONTROL Launch image]**: nome do arquivo de imagem que será exibido na inicialização. Se o usuário optar por iniciar seu aplicativo, a imagem selecionada será exibida em vez da tela de inicialização do aplicativo.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: selecionado por padrão; o sistema apresenta a notificação imediatamente, ativa a tela e pode reproduzir um som. As notificações não interrompem os modos de foco.

      * **[!UICONTROL Passive]**: o sistema adiciona a notificação à lista de notificações sem ativar a tela ou reproduzir um som. As notificações não interrompem os modos de foco.

      * **[!UICONTROL Time sensitive]** O sistema apresenta a notificação imediatamente, ativa a tela, pode reproduzir um som e interrompe os modos de foco. Esse nível não requer uma permissão especial da Apple.

      * **[!UICONTROL Critical]** O sistema apresenta a notificação imediatamente, ativa a tela e ignora os modos de foco e a opção de mudo. Observe que esse nível requer uma permissão especial da Apple.

   * **[!UICONTROL Relevance score]**: defina uma pontuação de relevância de 0 a 100. O sistema usa essa opção para classificar as notificações no resumo de notificações.

   ![](assets/push_ios_7.png)

1. Quando a notificação estiver configurada, clique na guia **[!UICONTROL Preview]** para visualizar a notificação.

   ![](assets/push-ios-preview.png)


>[!TAB Android]

Para enviar notificações em dispositivos Android, siga estas etapas:

1. Selecione o modelo de entrega **[!UICONTROL Deliver on Android (android)]**.

   ![](assets/push-template-android.png)

1. Para definir o target da notificação, clique no link **[!UICONTROL To]** e, em seguida, clique em **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Selecione **[!UICONTROL Subscribers of an Android mobile application]**, escolha o serviço relevante para seu aplicativo móvel (Neotrips, neste caso) e selecione a versão Android do aplicativo.

   ![](assets/push-android-subscribers.png)

1. Em seguida, insira o conteúdo da notificação.

   ![](assets/push-android-content.png)

1. Clique em **[!UICONTROL Insert emoticon]** ícone para inserir emoticons à notificação via push.

1. No campo **[!UICONTROL Application variables]**, insira o valor de cada variável. Por exemplo, você pode configurar uma tela de aplicativo específica para ser exibida quando o usuário ativar a notificação.

1. Quando a notificação estiver configurada, clique na guia **[!UICONTROL Preview]** para visualizar a notificação.

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]

## Testar, enviar e monitorar as notificações por push

Para enviar uma prova e o delivery final, use o mesmo processo dos outros deliveries.

Saiba como validar um delivery no [esta página](preview-and-proof.md).

Saiba como confirmar e enviar o delivery no [esta página](send.md)

Após enviar as mensagens, você pode monitorar e rastrear suas entregas. Saiba mais sobre os motivos de falha na entrega de notificação por push em [esta página](delivery-failures.md#push-error-types).

