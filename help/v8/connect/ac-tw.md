---
title: Trabalhar com o Campaign e o Twitter
description: Saiba como integrar seu ambiente do Campaign com o Twitter
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 0f15112f0eec1d7cba26523adc1e88fc5d26997c
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 26%

---

# Trabalhar com o Campaign e o Twitter{#tw-ac-ovv}

O **Gerenciamento de redes sociais (Marketing Social)** permite interagir com seus clientes por meio da Twitter. Use este recurso para:

* Enviar mensagens - Use o Adobe Campaign Social Marketing para postar mensagens no Twitter. Você também pode enviar mensagens diretas a todos os seus seguidores do 

* Colete novos contatos - O Adobe Campaign Social Marketing também facilita a aquisição de novos contatos: entre em contato com os usuários e pergunte se eles desejam compartilhar suas informações de perfil. Se eles aceitarem, o Adobe Campaign recuperará automaticamente os dados, o que permite realizar campanhas de direcionamento e, quando possível, implementar estratégias entre canais.

![](../assets/do-not-localize/speech.png)  Como um usuário do Managed Cloud Services, [Adobe de contato](../start/campaign-faq.md#support) para conectar o Campaign com o Twitter. O  **Gerenciamento de redes sociais (Marketing Social)** deve ser instalado em seu ambiente, por meio do pacote dedicado.


Para configurar o Adobe Campaign para publicar tweets em suas contas do Twitter, delegue acesso de gravação ao Adobe Campaign para essas contas. Para fazer isso:

1. Crie uma conta do Twitter
1. Crie uma conta do Twitter de teste para enviar provas
1. Criar um aplicativo do Twitter (um aplicativo por conta da Twitter)
1. Criar um novo serviço para **[!UICONTROL Twitter]** (um serviço por conta da Twitter)

## Criar uma conta de teste no Twitter {#tw-test-account}

Além da conta do Twitter, crie uma conta Twitter privada que possa ser usada para enviar [provas de tweet](../send/twitter.md#send-tw-proofs). Para fazer isso, siga as etapas abaixo:

1. Crie uma nova conta do Twitter.
1. Acessar a conta  **Configurações**.
1. Navegue até **Privacidade e segurança** e **Público-alvo e marcação** e verifique a **Protect em seus tweets** opção. Seus tweets e outras informações da conta são visíveis apenas para as pessoas que seguem você.

![](assets/social_tw_test_page.png)

## Criar um aplicativo no Twitter {#create-an-app-on-twitter}

Crie um aplicativo do Twitter para permitir que o Adobe Campaign publique tweets em sua conta do Twitter.  Para fazer isso, siga as etapas abaixo:

1. Faça logon em sua conta do Twitter.
1. Conectar-se a [Portal do desenvolvedor do twitter](https://developer.twitter.com/en/apps).
1. Selecionar **Criar um aplicativo**.
1. Deixe o assistente do Twitter orientá-lo pelo processo.

   Para permitir que o Adobe Campaign poste tweets em sua conta, edite no **Permissões** do aplicativo e selecione **Leitura e gravação** para **Acesso** seção. Na guia **Settings**, também é necessário deixar o campo **Callback URL** vazio.

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>Você precisa de um aplicativo por conta da Twitter. Como consequência, você deve criar outro aplicativo de teste para enviar provas para sua conta de teste.

## Criar um serviço Twitter no Campaign {#create-tw-service}

Para vincular a instância do Campaign à conta da Twitter, crie um **Twitter** e delegar acesso de gravação ao Campaign.

Para inserir configurações, você deve acessar o console do Adobe Campaign e uma conta do Twitter:

1. Abrir **Twitter** e de [a página Projeto e Aplicativos](https://developer.twitter.com/en/portal/projects-and-apps), selecione o aplicativo criado anteriormente. Acesse o **Permissões do aplicativo**.

   ![](assets/social_tw_service.png)

   Edite a guia **Chaves e tokens** para acessar os detalhes do aplicativo.

1. Em **Adobe Campaign**, navegue até o **[!UICONTROL Profiles and targets]** e selecione a **[!UICONTROL Services and Subscriptions]** link
1. Crie um novo serviço.
1. Selecione o tipo **[!UICONTROL Twitter]**.

   >[!NOTE]
   >
   >O **[!UICONTROL Synchronize subscriptions]** está ativada por padrão: essa opção recupera automaticamente a lista de seus seguidores do Twitter para que você possa [enviar mensagens diretas a eles](../send/twitter.md#direct-tw-messages). A sincronização é executada por uma [fluxo de trabalho técnico dedicado](#synchro-tw-accounts).

1. Insira o rótulo e o nome interno do serviço.

   >[!CAUTION]
   >
   >O **[!UICONTROL Internal name]** do serviço deve ter exatamente o mesmo nome de sua conta do Twitter.

   Para verificar suas configurações, é possível:

   * Clique no botão **[!UICONTROL Save]**.
   * Na visão geral dos serviços, selecione a variável **Twitter** serviço que acabou de criar.
   * Navegue pelo **[!UICONTROL Twitter page]** guia : sua conta do Twitter deve ser exibida.

1. Por padrão, os seguidores são salvos na pasta **[!UICONTROL Visitors]**. Você pode selecionar outro local no **[!UICONTROL Visitor folder]** campo. [Saiba mais](../send/twitter.md#direct-tw-messages)

1. No aplicativo Twitter, copie o conteúdo da variável **[!UICONTROL Consumer Key (API Key)]** e **[!UICONTROL Consumer Secret (API Secret)]** e os cole no **[!UICONTROL Consumer key]** e **[!UICONTROL Consumer secret]** campos de sua campanha **Twitter** serviço.

1. No aplicativo Twitter, copie o conteúdo da variável **[!UICONTROL Access Token]** e **[!UICONTROL Access Token Secret]** e os cole no **[!UICONTROL Access token]** e **[!UICONTROL Access token secret]** campos de sua campanha **Twitter** serviço.

1. No console do cliente do Campaign, clique em **[!UICONTROL Save]**. Agora você delegou acesso de gravação ao Adobe Campaign.


>[!NOTE]
>
>Criar um **Twitter** por conta da Twitter. Como consequência, você deve criar outro serviço de teste para enviar provas para sua conta de teste.

## Sincronizar sua conta do Twitter {#synchro-tw-accounts}

A sincronização entre o Campaign e o Twitter é gerenciada por meio de workflows técnicos dedicados. Esses workflows são armazenados no **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** pasta.

Eles são interrompidos por padrão: você deve iniciá-los manualmente ao começar a usar o **Marketing social** módulo.

O **[!UICONTROL Twitter account synchronization]** o workflow técnico sincroniza contas do Twitter no Adobe Campaign. Esse workflow recupera a lista de seguidores do Twitter para que você possa enviar mensagens diretas a eles. [Saiba mais](../send/twitter.md#direct-tw-messages)

Por padrão, esse fluxo de trabalho é acionado todas as quintas-feiras às 7h30. Você pode usar o **[!UICONTROL Execute pending task(s) now]** para iniciar o workflow a qualquer momento enquanto estiver implementando essa integração.  Também é possível editar o scheduler para alterar a frequência de acionamento do workflow. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}.

>[!CAUTION]
>
>Para recuperar a lista de assinantes do Twitter, a variável **[!UICONTROL Twitter account synchronization]** deve ser marcada para o serviço vinculado à conta. [Saiba mais](#create-tw-service)

Os seguidores são armazenados em uma tabela específica: a tabela de visitantes. Para exibir a lista de seguidores do Twitter, navegue até o **[!UICONTROL Profiles and Targets > Visitors]**.

Para cada seguidor, o Adobe Campaign armazena as seguintes informações:

* **[!UICONTROL Origin]**: nome da rede social (Twitter)
* **[!UICONTROL External ID]**: identificador do usuário
* **[!UICONTROL User name]**: nome da conta do usuário
* **[!UICONTROL Full name]**: nome do usuário
* **[!UICONTROL Language]**: idioma do usuário
* **[!UICONTROL Number of friends]**: número de seguidores
* **[!UICONTROL Time zone]**: fuso horário do usuário
* **[!UICONTROL Verified]**: este campo indica se o usuário tem uma conta verificada do Twitter

Quando essa configuração for concluída, você poderá postar tweets nas suas contas do Twitter e enviar mensagens diretas aos seus seguidores. [Saiba mais](../send/twitter.md)
