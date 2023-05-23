---
title: Trabalhar com o Campaign e o Twitter
description: Saiba como integrar seu ambiente do Campaign ao Twitter
role: User, Admin
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 18%

---

# Trabalhar com o Campaign e o Twitter{#tw-ac-ovv}

A variável **Gerenciamento de redes sociais (Marketing social)** permite interagir com os clientes por meio do Twitter. Use esse recurso para:

* Publicar mensagens e enviar DMs - Use o Adobe Campaign Social Marketing para publicar mensagens no Twitter. Você também pode enviar mensagens diretas a todos os seus seguidores.

* Coletar novos contatos - O Adobe Campaign Social Marketing também facilita a aquisição de novos contatos: entre em contato com os usuários e pergunte se desejam compartilhar suas informações de perfil. Se eles aceitarem, o Adobe Campaign recuperará automaticamente os dados, o que permite realizar campanhas de direcionamento e, quando possível, implementar estratégias entre canais.

![](../assets/do-not-localize/speech.png) Como usuário do Managed Cloud Services, [Adobe de contato](../start/campaign-faq.md#support) para conectar o Campaign com o Twitter. A variável  **Gerenciamento de redes sociais (Marketing social)** O complemento do deve ser instalado no ambiente, por meio do pacote dedicado, e a Conta externa do Twitter deve ser configurada.


Para configurar o Adobe Campaign para publicar tweets em suas contas do Twitter, delegue acesso de gravação ao Adobe Campaign para essas contas. Para fazer isso, você deve:

1. Crie uma conta do Twitter e cadastre-se em uma conta de desenvolvedor. [Saiba mais](#dev-account)
1. (opcional) Crie uma conta do Twitter de teste para enviar provas. [Saiba mais](#tw-test-account)
1. Crie um aplicativo do Twitter (um aplicativo por conta do Twitter). [Saiba mais](#create-an-app-on-twitter)
1. Criar um novo serviço para **[!UICONTROL Twitter]** (um serviço por conta da Twitter). [Saiba mais](#create-tw-service)
1. Sincronize sua conta da Twitter com o Campaign. [Saiba mais](#synchro-tw-accounts)

## Conta de desenvolvedor do twitter {#dev-account}

Para começar com essa integração, você deve se inscrever para uma [Conta de desenvolvedor do twitter](https://developer.twitter.com){target="_blank"}.

O Campaign usa a versão 1.1 da API do Twitter. Para usá-lo, você precisa solicitar acesso elevado por meio do Portal do desenvolvedor. Saiba mais sobre o Acesso elevado ao Twitter [nesta página](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Criar um aplicativo no Twitter {#create-an-app-on-twitter}

Depois de ter sido aprovado com Acesso elevado, crie um aplicativo do Twitter para permitir que o Adobe Campaign publique tweets em sua conta do Twitter. Para fazer isso, siga as etapas abaixo:

1. Faça logon em sua conta do Twitter.
1. Conectar a [portal do desenvolvedor do twitter](https://developer.twitter.com/en/apps).
1. Selecionar **Criar um aplicativo**.
1. Deixe o assistente do Twitter orientá-lo pelo processo.
1. Para permitir que o Adobe Campaign publique tweets em sua conta, edite em **Permissões do aplicativo** na seção Configuração de autenticação de usuário do aplicativo. Selecionar **Mensagens de leitura, gravação e diretas**.

   ![](assets/tw-permissions.png)

1. No **Tipo de aplicativo** , selecione **Aplicativo da Web, aplicativo automatizado ou bot**. Você pode deixar a variável **URL de retorno** vazio e salve a configuração.

   ![](assets/tw-app-type.png)

1. De volta ao painel do aplicativo, selecione seu aplicativo e navegue até o **Chaves e tokens** guia. Em **Token de acesso e segredo**, se a variável **Mensagens de leitura, gravação e diretas** não for mencionada, você deverá regenerar o token e o segredo do aplicativo. Observe que todas as chaves e tokens devem ser salvas após a criação. Você precisará deles para configurar o serviço Campaign Twitter.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>Você precisa de um aplicativo por conta do Twitter. Como consequência, você deve criar outra aplicação de teste para enviar provas para sua conta de teste.

## Criar um serviço Twitter no Campaign {#create-tw-service}

Para vincular a instância do Campaign à conta da Twitter, crie um **Twitter** serviço e delegar acesso de gravação ao Campaign.

>[!CAUTION]
>
>Criar um **Twitter** por conta da Twitter. Como consequência, você deve criar outro serviço de teste para enviar provas para o [testar conta](#tw-test-account).
>
>Each **Twitter** O serviço também deve ser criado pelo Adobe na instância MID. Entre em contato com o representante da Adobe para configurar seu ambiente.

Para inserir configurações, você deve acessar o console do Adobe Campaign e as permissões do aplicativo Twitter.

1. Entrada **Adobe Campaign**, navegue até o **[!UICONTROL Profiles and targets]** e selecione a guia **[!UICONTROL Services and Subscriptions]** link
1. Crie um novo serviço.
1. Selecione o tipo **[!UICONTROL Twitter]**.
1. Insira o rótulo e o nome interno do serviço.

   >[!CAUTION]
   >
   >A variável **[!UICONTROL Internal name]** do serviço deve ser exatamente o mesmo nome da sua conta da Twitter.

1. Por padrão, os seguidores são salvos na pasta **[!UICONTROL Visitors]**. Você pode selecionar outro local no **[!UICONTROL Visitor folder]** campo. [Saiba mais](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >A variável **[!UICONTROL Synchronize subscriptions]** estiver ativada por padrão: essa opção recupera automaticamente a lista de seguidores do Twitter para que você possa [enviar mensagens diretas a eles](../send/twitter.md#direct-tw-messages). A sincronização é executada por um [fluxo de trabalho técnico dedicado](#synchro-tw-accounts).

1. No aplicativo Twitter, copie o conteúdo do **Chave de API** e **[Segredo da chave de API]** campos e os cole na **[!UICONTROL Consumer key]** e **[!UICONTROL Consumer secret]** campos da sua campanha **Twitter** serviço.

1. No aplicativo Twitter, copie o conteúdo do **Token de acesso** e **Senha do token de acesso** campos e os cole na **[!UICONTROL Access token]** e **[!UICONTROL Access token secret]** campos da sua campanha **Twitter** serviço.

1. No console do cliente do Campaign, clique em **[!UICONTROL Save]**. Agora você delegou acesso de gravação ao Adobe Campaign.

Para verificar as configurações, é possível:

* Edite o **Twitter** serviço que acabou de criar.
* Navegue pelo **[!UICONTROL Twitter page]** guia: a conta do Twitter deve ser exibida.
   ![](assets/tw-page.png)


## Sincronizar a conta do Twitter {#synchro-tw-accounts}

A sincronização entre o Campaign e o Twitter é gerenciada por meio de workflows técnicos dedicados. Esses workflows são armazenados no **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** pasta.

Elas são interrompidas por padrão: você deve iniciá-las manualmente ao começar a usar o **Marketing social** módulo.

A variável **[!UICONTROL Synchronization of Twitter accounts]** o fluxo de trabalho técnico sincroniza as contas do Twitter no Adobe Campaign. Esse workflow recupera a lista de seguidores do Twitter para que você possa enviar mensagens diretas a eles. [Saiba mais](../send/twitter.md#direct-tw-messages)

Por padrão, esse fluxo de trabalho é acionado todas as quintas-feiras às 7h30. Você pode usar o **[!UICONTROL Execute pending task(s) now]** opção para iniciar o workflow a qualquer momento enquanto estiver implementando essa integração.  Também é possível editar o scheduler para alterar a frequência de acionamento do workflow. Saiba mais [nesta página](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Para recuperar a lista de assinantes do Twitter, a variável **[!UICONTROL Twitter account synchronization]** deve ser marcada para o serviço vinculado à conta. [Saiba mais](#create-tw-service)

Os seguidores são armazenados em uma tabela específica: a tabela de visitantes. Para exibir a lista de seguidores do Twitter, navegue até a **[!UICONTROL Profiles and Targets > Visitors]**.

Para cada seguidor, o Adobe Campaign armazena as seguintes informações:

* **[!UICONTROL Origin]**: Twitter
* **[!UICONTROL External ID]**: identificador do usuário
* **[!UICONTROL Username]**: nome da conta do usuário
* **[!UICONTROL Full name]**: nome do usuário
* **[!UICONTROL Number of friends]**: número de seguidores
* **[!UICONTROL Checked]**: este campo indica se o usuário tem uma conta verificada do Twitter

Quando essa configuração estiver concluída, você poderá postar tweets em suas contas do Twitter e enviar mensagens diretas aos seus seguidores. [Saiba mais](../send/twitter.md)

## Criar uma conta de teste no Twitter {#tw-test-account}

Além da conta do Twitter, crie uma conta privada do Twitter que possa ser usada para enviar [provas de tweet](../send/twitter.md#send-tw-proofs). Para fazer isso, siga as etapas abaixo:

1. Crie uma nova conta do Twitter.
1. Acessar a conta  **Configurações**.
1. Navegue até **Privacidade e segurança** e **Público-alvo e marcação** e verifique a **Protect seus tweets** opção. Seus tweets e outras informações da conta são visíveis apenas para as pessoas que seguem você.

![](assets/social_tw_test_page.png)

Configure seu aplicativo do Twitter e o serviço do Campaign para funcionar com essa conta de teste, conforme descrito acima.
