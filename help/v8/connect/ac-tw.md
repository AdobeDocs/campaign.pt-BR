---
title: Trabalhar com o Campaign e o Twitter
description: Saiba como integrar seu ambiente do Campaign com o Twitter
role: User, Admin
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 18%

---

# Trabalhar com o Campaign e o Twitter{#tw-ac-ovv}

O **Gerenciamento de redes sociais (Marketing Social)** permite interagir com seus clientes por meio da Twitter. Use este recurso para:

* Postar mensagens e enviar DMs - Use o Adobe Campaign Social Marketing para postar mensagens no Twitter. Você também pode enviar mensagens diretas a todos os seus seguidores.

* Colete novos contatos - O Adobe Campaign Social Marketing também facilita a aquisição de novos contatos: entre em contato com os usuários e pergunte se eles desejam compartilhar suas informações de perfil. Se eles aceitarem, o Adobe Campaign recuperará automaticamente os dados, o que permite realizar campanhas de direcionamento e, quando possível, implementar estratégias entre canais.

![](../assets/do-not-localize/speech.png) Como um usuário do Managed Cloud Services, [Adobe de contato](../start/campaign-faq.md#support) para conectar o Campaign com o Twitter. O  **Gerenciamento de redes sociais (Marketing Social)** deve ser instalado em seu ambiente, por meio do pacote dedicado, e a Conta externa do Twitter deve ser configurada.


Para configurar o Adobe Campaign para publicar tweets em suas contas do Twitter, delegue acesso de gravação ao Adobe Campaign para essas contas. Para fazer isso, você deve:

1. Crie uma conta do Twitter e cadastre-se em uma conta de desenvolvedor. [Saiba mais](#dev-account)
1. (opcional) Crie uma conta Twitter de teste para enviar provas. [Saiba mais](#tw-test-account)
1. Crie um aplicativo do Twitter (um aplicativo por conta da Twitter). [Saiba mais](#create-an-app-on-twitter)
1. Criar um novo serviço para **[!UICONTROL Twitter]** (um serviço por conta da Twitter). [Saiba mais](#create-tw-service)
1. Sincronize sua conta Twitter com o Campaign. [Saiba mais](#synchro-tw-accounts)

## Conta de desenvolvedor do twitter {#dev-account}

Para começar com essa integração, você deve se inscrever em um [Conta de desenvolvedor do twitter](https://developer.twitter.com){target="_blank"}.

O Campaign usa a versão 1.1 da API do Twitter. Para usá-lo, você precisa solicitar acesso Elevado por meio do Portal do desenvolvedor. Saiba mais sobre o Twitter Elevated Access [nesta página](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Criar um aplicativo no Twitter {#create-an-app-on-twitter}

Depois de ser aprovado com acesso Elevado, crie um aplicativo do Twitter para permitir que o Adobe Campaign poste tweets em sua conta do Twitter. Para fazer isso, siga as etapas abaixo:

1. Faça logon em sua conta do Twitter.
1. Conectar-se a [Portal do desenvolvedor do twitter](https://developer.twitter.com/en/apps).
1. Selecionar **Criar um aplicativo**.
1. Deixe o assistente do Twitter orientá-lo pelo processo.
1. Para permitir que o Adobe Campaign poste tweets em sua conta, edite no **Permissões do aplicativo** na seção Configuração de autenticação de usuário do seu aplicativo. Selecionar **Leitura, gravação e mensagens diretas**.

   ![](assets/tw-permissions.png)

1. No **Tipo de aplicativo** seção , selecione **Aplicativo da Web, Aplicativo automatizado ou Bot**. Você pode deixar o **URL de retorno** e salve a configuração.

   ![](assets/tw-app-type.png)

1. De volta ao painel do seu aplicativo, selecione seu aplicativo e navegue até o **Chaves e tokens** guia . Em **Token de acesso e segredo**, se a variável **Leitura, gravação e mensagens diretas** não for mencionada, você deve gerar novamente o token e o segredo do seu aplicativo. Observe que todas as chaves e tokens devem ser salvos na criação. Você precisará delas para configurar o serviço Campaign Twitter.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>Você precisa de um aplicativo por conta da Twitter. Como consequência, você deve criar outro aplicativo de teste para enviar provas para sua conta de teste.

## Criar um serviço Twitter no Campaign {#create-tw-service}

Para vincular a instância do Campaign à conta da Twitter, crie um **Twitter** e delegar acesso de gravação ao Campaign.

>[!CAUTION]
>
>Criar um **Twitter** por conta da Twitter. Como consequência, você deve criar outro serviço de teste para enviar provas para o [conta de teste](#tw-test-account).
>
>Cada **Twitter** O serviço também deve ser criado pelo Adobe na instância da MID. Entre em contato com o representante do Adobe para configurar o ambiente.

Para inserir configurações, você deve acessar o console do Adobe Campaign e as permissões do aplicativo Twitter.

1. Em **Adobe Campaign**, navegue até o **[!UICONTROL Profiles and targets]** e selecione a **[!UICONTROL Services and Subscriptions]** link
1. Crie um novo serviço.
1. Selecione o tipo **[!UICONTROL Twitter]**.
1. Insira o rótulo e o nome interno do serviço.

   >[!CAUTION]
   >
   >O **[!UICONTROL Internal name]** do serviço deve ter exatamente o mesmo nome de sua conta do Twitter.

1. Por padrão, os seguidores são salvos na pasta **[!UICONTROL Visitors]**. Você pode selecionar outro local no **[!UICONTROL Visitor folder]** campo. [Saiba mais](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >O **[!UICONTROL Synchronize subscriptions]** está ativada por padrão: essa opção recupera automaticamente a lista de seus seguidores do Twitter para que você possa [enviar mensagens diretas a eles](../send/twitter.md#direct-tw-messages). A sincronização é executada por uma [fluxo de trabalho técnico dedicado](#synchro-tw-accounts).

1. No aplicativo Twitter, copie o conteúdo da variável **Chave da API** e **[Segredo da chave da API]** e os cole no **[!UICONTROL Consumer key]** e **[!UICONTROL Consumer secret]** campos de sua campanha **Twitter** serviço.

1. No aplicativo Twitter, copie o conteúdo da variável **Token de acesso** e **Segredo do token de acesso** e os cole no **[!UICONTROL Access token]** e **[!UICONTROL Access token secret]** campos de sua campanha **Twitter** serviço.

1. No console do cliente do Campaign, clique em **[!UICONTROL Save]**. Agora você delegou acesso de gravação ao Adobe Campaign.

Para verificar suas configurações, é possível:

* Edite o **Twitter** serviço que acabou de criar.
* Navegue pelo **[!UICONTROL Twitter page]** guia : sua conta do Twitter deve ser exibida.
   ![](assets/tw-page.png)


## Sincronizar sua conta do Twitter {#synchro-tw-accounts}

A sincronização entre o Campaign e o Twitter é gerenciada por meio de workflows técnicos dedicados. Esses workflows são armazenados no **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** pasta.

Eles são interrompidos por padrão: você deve iniciá-los manualmente ao começar a usar o **Marketing social** módulo.

O **[!UICONTROL Synchronization of Twitter accounts]** o workflow técnico sincroniza contas do Twitter no Adobe Campaign. Esse workflow recupera a lista de seguidores do Twitter para que você possa enviar mensagens diretas a eles. [Saiba mais](../send/twitter.md#direct-tw-messages)

Por padrão, esse fluxo de trabalho é acionado todas as quintas-feiras às 7h30. Você pode usar o **[!UICONTROL Execute pending task(s) now]** para iniciar o workflow a qualquer momento enquanto estiver implementando essa integração.  Também é possível editar o scheduler para alterar a frequência de acionamento do workflow. Saiba mais [nesta página](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Para recuperar a lista de assinantes do Twitter, a variável **[!UICONTROL Twitter account synchronization]** deve ser marcada para o serviço vinculado à conta. [Saiba mais](#create-tw-service)

Os seguidores são armazenados em uma tabela específica: a tabela de visitantes. Para exibir a lista de seguidores do Twitter, navegue até o **[!UICONTROL Profiles and Targets > Visitors]**.

Para cada seguidor, o Adobe Campaign armazena as seguintes informações:

* **[!UICONTROL Origin]**: Twitter
* **[!UICONTROL External ID]**: identificador do usuário
* **[!UICONTROL Username]**: nome da conta do usuário
* **[!UICONTROL Full name]**: nome do usuário
* **[!UICONTROL Number of friends]**: número de seguidores
* **[!UICONTROL Checked]**: este campo indica se o usuário tem uma conta verificada do Twitter

Quando essa configuração for concluída, você poderá postar tweets nas suas contas do Twitter e enviar mensagens diretas aos seus seguidores. [Saiba mais](../send/twitter.md)

## Criar uma conta de teste no Twitter {#tw-test-account}

Além da conta do Twitter, crie uma conta Twitter privada que possa ser usada para enviar [provas de tweet](../send/twitter.md#send-tw-proofs). Para fazer isso, siga as etapas abaixo:

1. Crie uma nova conta do Twitter.
1. Acessar a conta  **Configurações**.
1. Navegue até **Privacidade e segurança** e **Público-alvo e marcação** e verifique a **Protect em seus tweets** opção. Seus tweets e outras informações da conta são visíveis apenas para as pessoas que seguem você.

![](assets/social_tw_test_page.png)

Configure seu aplicativo Twitter e serviço do Campaign para funcionar com essa conta de teste, conforme descrito acima.
