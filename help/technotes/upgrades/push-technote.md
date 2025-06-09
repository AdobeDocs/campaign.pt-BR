---
product: campaign
title: Próximas alterações no Canal de notificação por push
description: Próximas alterações no Canal de notificação por push
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="Também se aplica ao Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="Aplicável ao Campaign v8"
exl-id: 45ac6f8f-eb2a-4599-a930-1c1fcaa3095b
source-git-commit: a9aa9cb508ca1f5cdcd59e61b5be029e3de1a82f
workflow-type: tm+mt
source-wordcount: '1665'
ht-degree: 10%

---

# Alterações no Canal de notificação por push {#push-upgrade}

Você pode usar o Campaign para enviar notificações por push em dispositivos iOs e Android. Para fazer isso, o Campaign depende dos serviços de assinatura de aplicativo móvel.

Algumas alterações importantes no serviço Android Firebase Cloud Messaging (FCM) foram lançadas em 2024 e podem afetar sua implementação do Adobe Campaign. A configuração dos serviços de assinatura para mensagens por push do Android pode precisar ser atualizada para dar suporte a essa alteração.

Além disso, a Adobe recomenda mudar para a conexão baseada em token para APNs em vez de uma conexão baseada em certificado, que é mais segura e escalável.

## Serviço Google Android Firebase Cloud Messaging (FCM) {#fcm-push-upgrade}

### O que mudou? {#fcm-changes}

Como parte do esforço contínuo do Google para melhorar seus serviços, as APIs herdadas do FCM serão descontinuadas em **terça-feira, 22 de julho de 2024**. Saiba mais sobre o protocolo HTTP do Firebase Cloud Messaging em [documentação do Google Firebase](https://firebase.google.com/docs/cloud-messaging/migrate-v1){target="_blank"}.

O Adobe Campaign Classic v7 e o Adobe Campaign v8 já oferecem suporte às APIs mais recentes para enviar mensagens de notificação por push. No entanto, algumas implementações antigas ainda dependem das APIs herdadas. Essas implementações devem ser atualizadas.

### Você será afetado? {#fcm-impact}

Se sua implementação atual suportar serviços de assinatura conectados ao FCM usando as APIs herdadas, você será afetado. A transição para as APIs mais recentes é obrigatória para evitar qualquer perturbação do serviço. Nesse caso, as equipes do Adobe entrarão em contato com você.

Para verificar se você foi afetado, você pode filtrar seus **Serviços e Assinaturas** de acordo com o filtro abaixo:

![](assets/filter-services-fcm.png)


* Se qualquer um dos seus serviços de notificação por push ativos usar a API **HTTP (herdada)**, sua configuração será diretamente afetada por essa alteração. Você deve revisar suas configurações atuais e migrar para as APIs mais recentes conforme descrito abaixo.

* Se a configuração usar exclusivamente a API **HTTP v1** para notificações por push do Android, você já estará em conformidade e nenhuma outra ação será necessária da sua parte.

### Como atualizar? {#fcm-transition-procedure}

#### Pré-requisitos {#fcm-transition-prerequisites}

* O arquivo JSON da conta do serviço Android Firebase Admin SDK é necessário para mover o aplicativo móvel para HTTP v1. Saiba como obter este arquivo na [documentação do Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Para o Campaign Classic v7, o suporte do HTTP v1 foi adicionado à versão 20.3.1. Se seu ambiente estiver sendo executado em uma versão mais antiga, um pré-requisito para a transição para HTTP v1 é atualizar seu ambiente para a [compilação mais recente do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Para o Campaign v8, o HTTP v1 é compatível com todas as versões, e nenhuma atualização é necessária.

* Como usuário no local do Campaign Classic v7, você deve atualizar os servidores Marketing e Execução em tempo real.

* Para implantações híbridas, hospedadas e gerenciadas do Cloud Services, além do procedimento de transição abaixo, entre em contato com a Adobe para atualizar o servidor de execução em tempo real (RT).

* Sobre a conta externa Android routing:

   * Como usuário no local ou híbrido do Campaign Classic v7, verifique se a conta externa do Android Routing está configurada com `androidPushConnectorV2.js`. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android#configuring-external-account-android){target="_blank"}.

   * Para implantações híbridas, hospedadas e gerenciadas do Cloud Services, você também deve se conectar com a equipe de Atendimento ao cliente da Adobe para validar se o conector `androidPushConnectorV2.js (nms)` está selecionado na conta externa de roteamento do Android do seu servidor Mid-sourcing.

#### Procedimento de transição {#fcm-transition-steps}

Para mover seu ambiente para HTTP v1, siga estas etapas:

1. Navegue até a sua lista de **Serviços e Assinaturas**.
1. Liste todos os aplicativos móveis usando a versão da API **HTTP (herdada)**.
1. Para cada um desses aplicativos móveis, defina a **versão da API** como **HTTP v1**.
1. Clique no link **[!UICONTROL Load project json file to extract project details...]** para carregar diretamente seu arquivo de chave JSON.

   Você também pode inserir manualmente os seguintes detalhes:

   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. Clique em **[!UICONTROL Test the connection]** para verificar se a configuração está correta e se o servidor de marketing tem acesso ao FCM. Observe que, para implantações de Mid-Sourcing, o botão **[!UICONTROL Test connection]** não pode verificar se o servidor tem acesso ao serviço Android Firebase Cloud Messaging (FCM).
1. Como opção, você pode enriquecer um conteúdo de mensagem de push com alguns **[!UICONTROL Application variables]** se necessário. Eles são totalmente personalizáveis e uma parte da carga da mensagem é enviada para o dispositivo móvel.
1. Clique em **[!UICONTROL Finish]** e em **[!UICONTROL Save]**.

   Abaixo estão os nomes de payload do FCM para personalizar ainda mais sua notificação por push. Estas opções estão detalhadas [aqui](#fcm-apps).

   | Tipo de mensagem | Elemento de mensagem configurável (nome da carga FCM) | Opções configuráveis (nome da carga do FCM) |
   |:-:|:-:|:-:|
   | mensagem de dados | N/D | validate_only |
   | mensagem de notificação | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Depois que essas alterações forem aplicadas em todo o servidor, todos os **novos** deliveries de notificação por push para dispositivos Android usarão a API HTTP v1. Os deliveries de push existentes em repetição, em andamento e em uso ainda usam a API HTTP (herdada). Saiba como atualizá-los na seção abaixo.

#### Atualizar modelos existentes {#fcm-transition-update}

Quando a transição HTTP v1 estiver concluída, você deverá atualizar seus **modelos de entrega** para as notificações por push do Android para aumentar o número de mensagens em lote. Para fazer isso, navegue até as propriedades do modelo de entrega do Android e, na guia **Entrega**, defina a [Quantidade do lote de mensagens](../../v8/send/configure-and-send.md#delivery-batch-quantity) como **256**. Aplique essa alteração a todos os templates de delivery usados para seus deliveries do Android e a todos os deliveries existentes do Android.

Você também pode atualizar deliveries e templates de delivery existentes criados antes da atualização para uma versão compatível com HTTP v1. Para fazer isso:

* Como um cliente do Managed Cloud Services ou hospedado, entre em contato com a Adobe para atualizar seus modelos de entrega do Android existentes.

* Para ambientes locais, baixe o script `fcm-httpv1-migration.js` e execute-o conforme detalhado abaixo.

  Baixe [fcm-httpv1-migration.zip](assets/do-not-localize/fcm-httpv1-migration-js.zip).

  >[!CAUTION]
  >
  >O script deve ser executado na instância de marketing local.


  +++Etapas para atualizar deliveries e modelos existentes (somente no local)

  Para corrigir todos os deliveries e templates de deliveries criados antes da atualização para uma versão compatível com HTTP v1, siga estas etapas:

   1. Exporte seus deliveries e templates de delivery existentes em um pacote para poder restaurá-los caso ocorra um problema inesperado durante a aplicação de patches.
   1. Execute o seguinte comando no Posgresql:

      ```sql
      pg_dump -Fp -f /sftp/<db_name>-nmsdelivery-before_rd_script.sql -t nmsdelivery -d <db_name>
      ```

   1. Por padrão, o script está no modo `dryrun`. Você pode iniciá-lo nesse modo para verificar se alguma entrega precisa ser corrigida.

      Comando

      ```sql
      nlserver javascript -instance:<instance_name> -file fcm-httpv1-migration.js 
      ```

      Output

      ```sql
      ...
      HH:MM:SS >   Processing delivery (id:123456,  label:'Deliver on Android - New', name:'DM1234')
      HH:MM:SS >   Dry run: Would update androidCheckParams for delivery (id:123456,  label:'Deliver on Android - New', name:'DM1234')
      HH:MM:SS >   Processing delivery (id:567890,  label:'Deliver on Android - New', name:'DM5678')
      HH:MM:SS >   Dry run: Would update androidCheckParams for delivery (id:567890,  label:'Deliver on Android - New', name:'DM5678')
      ...
      HH:MM:SS >   Summary (XYZ processed deliverie(s) or delivery template(s)):
      HH:MM:SS >>  - X had not patchable androidCheckParams formula!
      HH:MM:SS >   - Y had androidCheckParams formula patched.
      HH:MM:SS >   - Z ignored as alreading having androidCheckParams formula patched.
      ```

      >[!NOTE]
      >
      >As entregas `not patchable` precisam ser atualizadas manualmente. A ID pode ser encontrada no log de.

   1. Execute o script no modo de execução da seguinte maneira para atualizar deliveries:

      ```sql
      nlserver javascript -instance:<instance_name> -file fcm-httpv1-migration.js -arg:run
      ```

  +++

### Qual é o impacto para meus aplicativos do Android? {#fcm-apps}

Não são necessárias alterações específicas no código dos aplicativos Android Mobile e o comportamento da notificação não deve ser alterado.

No entanto, com HTTP v1, você pode personalizar ainda mais sua notificação por push com **[!UICONTROL HTTPV1 additional options]**.

![](assets/android-push-additional-options.png)

Você pode:

* Use o campo **[!UICONTROL Ticker]** para definir o texto do ticker da sua notificação.
* Use o campo **[!UICONTROL Image]** para definir a URL da imagem a ser exibida na sua notificação.
* Use o campo **[!UICONTROL Notification Count]** para definir o número de novas informações não lidas a serem exibidas diretamente no ícone do aplicativo.
* Defina a opção **[!UICONTROL Sticky]** como false para que a notificação seja automaticamente descartada quando o usuário clicar nela. Se definida como verdadeiro, a notificação ainda será exibida mesmo quando o usuário clicar nela.
* Defina o nível **[!UICONTROL Notification Priority]** da sua notificação como padrão, mínimo, baixo ou alto.
* Defina o nível **[!UICONTROL Visibility]** da sua notificação como público, privado ou secreto.

Para obter mais informações sobre **[!UICONTROL HTTP v1 additional options]** e como preencher esses campos, consulte a [documentação do FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.



## Serviço de notificação por push (APNs) do Apple iOS {#apns-push-upgrade}

### O que mudou? {#ios-changes}

Conforme recomendado pela Apple, você deve proteger suas comunicações com o serviço de notificação por push (APNs) da Apple usando tokens de autenticação sem estado.

A autenticação baseada em token oferece uma maneira sem estado de se comunicar com APNs. A comunicação sem estado é mais rápida do que a comunicação baseada em certificado porque não requer que APNs consultem o certificado ou outras informações relacionadas ao servidor do provedor. Há outras vantagens em usar a autenticação baseada em token:

* Você pode usar o mesmo token de vários servidores de provedores.

* Você pode usar um token para distribuir notificações para todos os aplicativos de sua empresa.

Saiba mais sobre conexões baseadas em token com APNs em [Documentação para desenvolvedores do Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

O Adobe Campaign Classic v7 e o Adobe Campaign v8 oferecem suporte a conexões baseadas em token e em certificado. Se sua implementação depende de uma conexão baseada em certificados, a Adobe recomenda que você atualize-a para uma conexão baseada em token.

### Você será afetado? {#ios-impact}

Se sua implementação atual depender de solicitações baseadas em certificado para se conectar a APNs, você será afetado. Recomenda-se a transição para uma conexão baseada em token.

Para verificar se você foi afetado, você pode filtrar seus **Serviços e Assinaturas** de acordo com o filtro abaixo:

![](assets/filter-services-ios.png)


* Se qualquer um dos seus serviços de notificação por push ativos usar o **modo de autenticação baseada em certificado** (.p12), suas implementações atuais deverão ser revisadas e movidas para um **modo de autenticação baseada em token** (.p8) conforme descrito abaixo.

* Se sua configuração usar exclusivamente o modo de **autenticação baseada em token** para notificações por push do iOS, sua implementação já estará atualizada e nenhuma outra ação será necessária da sua parte.

### Como atualizar? {#ios-transition-procedure}

#### Pré-requisitos {#ios-transition-prerequisites}

* Para o Campaign Classic v7, o suporte ao modo de **Autenticação baseada em token** foi adicionado na versão 20.2. Se seu ambiente estiver sendo executado em uma versão mais antiga, um pré-requisito para essa alteração é atualizar seu ambiente para a [compilação mais recente do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Para o Campaign v8, o modo de **autenticação baseada em token** é compatível com todas as versões, e nenhuma atualização é necessária.

* Você precisa de uma chave de assinatura de token de autenticação APNs para gerar os tokens que seu servidor usa. Você solicita essa chave da sua conta de desenvolvedor do Apple, conforme explicado na [Documentação do desenvolvedor do Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

* Para implantações híbridas, hospedadas e Managed Services, além do procedimento de transição abaixo, entre em contato com a Adobe para atualizar o servidor de execução em tempo real (RT). O servidor Mid-Sourcing não é afetado.

* Como usuário no local do Campaign Classic v7, você deve atualizar os servidores Marketing e Execução em tempo real. O servidor Mid-Sourcing não é afetado.

#### Procedimento de transição {#ios-transition-steps}

Para mover seus aplicativos móveis da iOS para o modo de autenticação baseada em token, siga estas etapas:

1. Navegue até a sua lista de **Serviços e Assinaturas**.
1. Liste todos os aplicativos móveis usando o **Modo de autenticação baseada em certificado** (.p12).
1. Edite cada um desses aplicativos móveis e navegue até a guia **Chave de certificado/privada**.
1. No menu suspenso **Modo de Autenticação**, selecione o modo **Autenticação baseada em token** (.p8).
1. Preencha as configurações de conexão APNs **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** e **[!UICONTROL Bundle Id]** e selecione seu certificado p8 clicando em **[!UICONTROL Enter the private key...]**.

   ![](assets/token-based-certif.png)

1. Clique em **[!UICONTROL Test the connection]** para verificar se a configuração está correta e se o servidor tem acesso a APNs. Observe que, para implantações de Mid-Sourcing, o botão **[!UICONTROL Test connection]** não pode verificar se o servidor tem acesso a APNs.
1. Clique em **[!UICONTROL Next]** para configurar o aplicativo de produção e siga as mesmas etapas descritas acima.
1. Clique em **[!UICONTROL Finish]** e em **[!UICONTROL Save]**.

Seu aplicativo iOS agora está sendo movido para o modo de autenticação baseado em token.
