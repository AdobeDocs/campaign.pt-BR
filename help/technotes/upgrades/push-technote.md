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
source-git-commit: 24d9adddbc983a600f99dab8bab1235585b48ceb
workflow-type: tm+mt
source-wordcount: '1357'
ht-degree: 12%

---

# Alterações no Canal de notificação por push {#push-upgrade}

Você pode usar o Campaign para enviar notificações por push em dispositivos iOs e Android. Para fazer isso, o Campaign depende dos serviços de assinatura de aplicativo móvel.

Algumas alterações importantes no serviço Android Firebase Cloud Messaging (FCM) foram lançadas em 2024 e podem afetar sua implementação do Adobe Campaign. A configuração dos serviços de assinatura para mensagens por push do Android pode precisar ser atualizada para dar suporte a essa alteração.

Além disso, o Adobe recomenda mudar para a conexão baseada em token para APNs em vez de uma conexão baseada em certificado, que é mais segura e escalável.

## Serviço Google Android Firebase Cloud Messaging (FCM) {#fcm-push-upgrade}

### O que mudou? {#fcm-changes}

Como parte do esforço contínuo do Google para melhorar seus serviços, as APIs herdadas do FCM serão descontinuadas em **terça-feira, 22 de julho de 2024**. Saiba mais sobre o protocolo HTTP do Firebase Cloud Messaging em [Documentação do Google Firebase](https://firebase.google.com/docs/cloud-messaging/migrate-v1){target="_blank"}.

O Adobe Campaign Classic v7 e o Adobe Campaign v8 já oferecem suporte às APIs mais recentes para enviar mensagens de notificação por push. No entanto, algumas implementações antigas ainda dependem das APIs herdadas. Essas implementações devem ser atualizadas.

### Você será afetado? {#fcm-impact}

Se sua implementação atual suportar serviços de assinatura conectados ao FCM usando as APIs herdadas, você será afetado. A transição para as APIs mais recentes é obrigatória para evitar qualquer perturbação do serviço. Nesse caso, as equipes do Adobe entrarão em contato com você.

Para verificar se você foi afetado, é possível filtrar o **Serviços e assinaturas** de acordo com o filtro abaixo:

![](assets/filter-services-fcm.png)


* Se qualquer um dos serviços de notificação por push ativos usar o **HTTP (herdado)** , sua configuração será afetada diretamente por essa alteração. Você deve revisar suas configurações atuais e migrar para as APIs mais recentes conforme descrito abaixo.

* Se a configuração usar exclusivamente o **HTTP v1** API para notificações por push do Android, você já está em conformidade e nenhuma outra ação será necessária da sua parte.

### Como atualizar? {#fcm-transition-procedure}

#### Pré-requisitos {#fcm-transition-prerequisites}

* Para o Campaign Classic v7, o suporte de HTTP v1 foi adicionado na versão 20.3.1. Se o ambiente estiver sendo executado em uma versão mais antiga, um pré-requisito para a transição para HTTP v1 é atualizar o ambiente para o [build de Campaign Classic mais recente](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Para o Campaign v8, o HTTP v1 é compatível com todas as versões, e nenhuma atualização é necessária.

* O arquivo JSON da conta do serviço SDK do administrador do Android Firebase é necessário para mover o aplicativo móvel para HTTP v1. Saiba como obter este arquivo no [Documentação do Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Para implantações híbridas, hospedadas e Managed Services, além do procedimento de transição abaixo, entre em contato com o Adobe para atualizar o servidor de execução em tempo real (RT). O servidor Mid-Sourcing não é afetado.

* Como usuário local do Campaign Classic v7, você deve atualizar os servidores de execução Marketing e Tempo real. O servidor Mid-Sourcing não é afetado.

#### Procedimento de transição {#fcm-transition-steps}

Para mover seu ambiente para HTTP v1, siga estas etapas:

1. Navegue até a lista de **Serviços e assinaturas**.
1. Listar todos os aplicativos móveis usando o **HTTP (herdado)** Versão da API.
1. Para cada um desses aplicativos móveis, defina o **Versão da API** para **HTTP v1**.
1. Clique em **[!UICONTROL Load project json file to extract project details...]** para carregar diretamente seu arquivo de chave JSON.

   Você também pode inserir manualmente os seguintes detalhes:

   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. Clique em **[!UICONTROL Test the connection]** para verificar se a configuração está correta e se o servidor de marketing tem acesso ao FCM. Observe que para implantações de Mid-Sourcing, a variável **[!UICONTROL Test connection]** O botão não pode verificar se o servidor tem acesso ao serviço Android Firebase Cloud Messaging (FCM).
1. Como opção, você pode enriquecer um conteúdo de mensagem de push com alguns **[!UICONTROL Application variables]** se necessário. Eles são totalmente personalizáveis e uma parte da carga da mensagem é enviada para o dispositivo móvel.
1. Clique em **[!UICONTROL Finish]** e em **[!UICONTROL Save]**.

Abaixo estão os nomes de payload do FCM para personalizar ainda mais sua notificação por push. Essas opções são detalhadas [aqui](#fcm-apps).

| Tipo de mensagem | Elemento de mensagem configurável (nome da carga FCM) | Opções configuráveis (nome da carga do FCM) |
|:-:|:-:|:-:|
| mensagem de dados | N/D | validate_only |
| mensagem de notificação | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Depois que essas alterações forem aplicadas em todo o servidor, todos os novos deliveries de notificação por push para dispositivos Android usarão a API HTTP v1. Os deliveries de push existentes em repetição, em andamento e em uso ainda usam a API HTTP (herdada).

### Qual é o impacto para meus aplicativos do Android? {#fcm-apps}

Não são necessárias alterações específicas no código dos aplicativos Android Mobile e o comportamento da notificação não deve ser alterado.

No entanto, com HTTP v1, você pode personalizar ainda mais sua notificação por push com **[!UICONTROL HTTPV1 additional options]**.

![](assets/android-push-additional-options.png)

Você pode:

* Use o **[!UICONTROL Ticker]** para definir o texto do ticker da sua notificação.
* Use o **[!UICONTROL Image]** para definir o URL da imagem que será exibido na sua notificação.
* Use o **[!UICONTROL Notification Count]** para definir o número de novas informações não lidas a serem exibidas diretamente no ícone do aplicativo.
* Defina o **[!UICONTROL Sticky]** para que a notificação seja automaticamente descartada quando o usuário clicar nela. Se definida como verdadeiro, a notificação ainda será exibida mesmo quando o usuário clicar nela.
* Defina o **[!UICONTROL Notification Priority]** nível da sua notificação para padrão, mínimo, baixo ou alto.
* Defina o **[!UICONTROL Visibility]** nível da sua notificação para público, privado ou secreto.

Para saber mais sobre **[!UICONTROL HTTP v1 additional options]** e como preencher esses campos, consulte a [documentação do FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.




## Serviço de notificação por push (APNs) do Apple iOS {#apns-push-upgrade}

### O que mudou? {#ios-changes}

Conforme recomendado pela Apple, você deve proteger suas comunicações com o serviço de notificação por push (APNs) da Apple usando tokens de autenticação sem estado.

A autenticação baseada em token oferece uma maneira sem estado de se comunicar com APNs. A comunicação sem estado é mais rápida do que a comunicação baseada em certificado porque não requer que APNs consultem o certificado ou outras informações relacionadas ao servidor do provedor. Há outras vantagens em usar a autenticação baseada em token:

* Você pode usar o mesmo token de vários servidores de provedores.

* Você pode usar um token para distribuir notificações para todos os aplicativos de sua empresa.

Saiba mais sobre Conexões baseadas em token para APNs em [Documentação do desenvolvedor do Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

O Adobe Campaign Classic v7 e o Adobe Campaign v8 oferecem suporte a conexões baseadas em token e em certificado. Se sua implementação depende de uma conexão baseada em certificado, o Adobe recomenda que você atualize-a para uma conexão baseada em token.

### Você será afetado? {#ios-impact}

Se sua implementação atual depender de solicitações baseadas em certificado para se conectar a APNs, você será afetado. Recomenda-se a transição para uma conexão baseada em token.

Para verificar se você foi afetado, é possível filtrar o **Serviços e assinaturas** de acordo com o filtro abaixo:

![](assets/filter-services-ios.png)


* Se qualquer um dos serviços de notificação por push ativos usar o **Autenticação baseada em certificado** (.p12), suas implementações atuais devem ser revisadas e movidas para um **Autenticação baseada em token** (.p8) conforme descrito abaixo.

* Se a configuração usar exclusivamente o **Autenticação baseada em token** para notificações por push do iOS, sua implementação já está atualizada e nenhuma ação adicional será necessária da sua parte.

### Como atualizar? {#ios-transition-procedure}

#### Pré-requisitos {#ios-transition-prerequisites}

* Para o Campaign Classic v7, o suporte do **Autenticação baseada em token** O modo foi adicionado na versão 20.2. Se o ambiente estiver sendo executado em uma versão mais antiga, um pré-requisito para essa alteração será atualizar o ambiente para o [build de Campaign Classic mais recente](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Para o Campaign v8, **Autenticação baseada em token** O modo é compatível com todas as versões e nenhuma atualização é necessária.

* Você precisa de uma chave de assinatura de token de autenticação APNs para gerar os tokens que seu servidor usa. Essa chave é solicitada na sua conta de desenvolvedor do Apple, conforme explicado em [Documentação do desenvolvedor do Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

* Para implantações híbridas, hospedadas e Managed Services, além do procedimento de transição abaixo, entre em contato com o Adobe para atualizar o servidor de execução em tempo real (RT). O servidor Mid-Sourcing não é afetado.

* Como usuário local do Campaign Classic v7, você deve atualizar os servidores de execução Marketing e Tempo real. O servidor Mid-Sourcing não é afetado.

#### Procedimento de transição {#ios-transition-steps}

Para mover seus aplicativos móveis da iOS para o modo de autenticação baseada em token, siga estas etapas:

1. Navegue até a lista de **Serviços e assinaturas**.
1. Listar todos os aplicativos móveis usando o **Autenticação baseada em certificado** (.p12).
1. Edite cada um desses aplicativos móveis e navegue até o **Chave de certificado/privada** guia.
1. No **Modo de autenticação** selecione **Autenticação baseada em token** (.p8).
1. Preencha as configurações de conexão APNs **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** e **[!UICONTROL Bundle Id]** em seguida, selecione o certificado p8 clicando em **[!UICONTROL Enter the private key...]**.

   ![](assets/token-based-certif.png)

1. Clique em **[!UICONTROL Test the connection]** para verificar se a configuração está correta e se o servidor tem acesso aos APNs. Observe que para implantações de Mid-Sourcing, a variável **[!UICONTROL Test connection]** O botão não pode verificar se o servidor tem acesso a APNs.
1. Clique em **[!UICONTROL Next]** para configurar o aplicativo de produção e siga as mesmas etapas descritas acima.
1. Clique em **[!UICONTROL Finish]** e em **[!UICONTROL Save]**.

Seu aplicativo iOS agora está sendo movido para o modo de autenticação baseado em token.
