---
product: campaign
title: Alterações futuras no Canal de notificação por push
description: Alterações futuras no Canal de notificação por push
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="Também se aplica ao Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="Aplicável ao Campaign v8"
hide: true
hidefromtoc: true
source-git-commit: 65b8d84e600e1814484fa81fb814475c0a8b9296
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 19%

---

# Alterações futuras no Canal de notificação por push {#push-upgrade}

Você pode usar o Campaign para enviar notificações por push em dispositivos Android. Para fazer isso, o Campaign depende de serviços de assinatura específicos. Algumas alterações importantes no serviço Android Firebase Cloud Messaging (FCM) serão lançadas em 2024 e podem afetar sua implementação do Adobe Campaign. A configuração dos serviços de assinatura para mensagens por push do Android pode precisar ser atualizada para dar suporte a essa alteração.

## O que mudou? {#fcm-changes}

Como parte do esforço contínuo da Google para melhorar seus serviços, as APIs herdadas do FCM serão descontinuadas em **20 de junho de 2024**. Saiba mais sobre o protocolo HTTP do Firebase Cloud Messaging em [Documentação do Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

O Adobe Campaign Classic v7 e o Adobe Campaign v8 já oferecem suporte às APIs mais recentes para enviar mensagens de notificação por push. No entanto, algumas implementações antigas ainda dependem das APIs herdadas. Essas implementações devem ser atualizadas.

## Você será afetado? {#fcm-impact}

Se sua implementação atual suportar serviços de assinatura conectados ao FCM usando as APIs herdadas, você será afetado. A migração para as APIs mais recentes é obrigatória para evitar qualquer perturbação do serviço. Nesse caso, as equipes do Adobe entrarão em contato com você.

Para verificar se você foi afetado, é possível filtrar o **Serviços e assinaturas** de acordo com o filtro abaixo:

![](assets/filter-services-fcm.png)


* Se qualquer um dos serviços de notificação por push ativos usar o **HTTP (herdado)** , sua configuração será afetada diretamente por essa alteração. Você deve revisar suas configurações atuais e migrar para as APIs mais recentes conforme descrito abaixo.

* Se a configuração usar exclusivamente o **HTTP v1** API para notificações por push do Android, você já está em conformidade e nenhuma outra ação será necessária da sua parte.

## Como migrar? {#fcm-migration-procedure}

### Pré-requisitos {#fcm-migration-prerequisites}

* Para o Campaign Classic v7, o suporte de HTTP v1 foi adicionado na versão 20.3.1. Se o ambiente estiver sendo executado em uma versão mais antiga, um pré-requisito para a migração para HTTP v1 é atualizar o ambiente para o [build de Campaign Classic mais recente](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Para o Campaign v8, o HTTP v1 é compatível com todas as versões, e nenhuma atualização é necessária.

* O arquivo JSON da conta do serviço SDK de administrador do Firebase do Android é necessário para mover o aplicativo móvel para HTTP v1. Saiba como obter este arquivo no [Documentação do Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Para implantações híbridas, hospedadas e Managed Services, além do procedimento de migração abaixo, entre em contato com o Adobe para atualizar o servidor de execução em tempo real (RT). O servidor Mid-Sourcing não é afetado.

* Como usuário local do Campaign Classic v7, você deve atualizar os servidores de execução Marketing e Tempo real. O servidor Mid-Sourcing não é afetado.

### Procedimento de migração {#fcm-migration-steps}

Para migrar seu ambiente para HTTP v1, siga estas etapas:

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
>Depois que essas alterações forem aplicadas em todos os servidores, todos os novos deliveries de notificação por push para dispositivos Android usarão a API HTTP v1. Os deliveries de push existentes em repetição, em andamento e em uso ainda usam a API HTTP (herdada).

### Qual é o impacto para meus aplicativos Android? {#fcm-apps}

Não há alterações específicas necessárias no código dos aplicativos móveis do Android e o comportamento da notificação não deve ser alterado.

No entanto, com HTTP v1, você pode personalizar ainda mais sua notificação por push com **[!UICONTROL HTTPV1 additional options]**.

![](assets/android-push-additional-options.png)

Você pode:

* Use o **[!UICONTROL Ticker]** para definir o texto do ticker da sua notificação.
* Use o **[!UICONTROL Image]** para definir o URL da imagem que será exibido na sua notificação.
* Use o **[!UICONTROL Notification Count]** para definir o número de novas informações não lidas a serem exibidas diretamente no ícone do aplicativo.
* Defina o **[!UICONTROL Sticky]** para que a notificação seja automaticamente descartada quando o usuário clicar nela. Se definida como verdadeiro, a notificação ainda será exibida mesmo quando o usuário clicar nela.
* Defina o **[!UICONTROL Notification Priority]** nível da sua notificação para padrão, mínimo, baixo ou alto.
* Defina o **[!UICONTROL Visibility]** nível da sua notificação para público, privado ou secreto.

Para obter mais informações sobre **[!UICONTROL HTTP v1 additional options]** e como preencher esses campos, consulte a [documentação do FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.

