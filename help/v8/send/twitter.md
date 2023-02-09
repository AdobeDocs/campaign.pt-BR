---
title: Postar mensagens no Twitter com o Adobe Campaign
description: Saiba como usar o módulo Marketing do Adobe Campaign Social para postar mensagens no Twitter e enviar mensagens diretas para seus seguidores
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: 9ae93ce4e2b0424bb3b3862b2c7d016309bd630e
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 37%

---


# Postar mensagens no Twitter com o Adobe Campaign {#post-tw-messages}

O Adobe Campaign vem com um **Marketing social** que permite interagir com seus clientes e clientes potenciais via Twitter.

Após configurar a integração, é possível:

* Enviar mensagens diretas aos seus seguidores
* Postar tweets em sua conta do Twitter
* Colete novos contatos recuperando os dados do perfil, o que permite realizar campanhas de definição de metas e, quando possível, implementar estratégias entre canais. Esta ação requer o consentimento do usuário.


As etapas de configuração para integrar sua conta do Twitter com o Adobe Campaign estão descritas em [esta página](../connect/ac-tw.md).

## Criar e publicar uma postagem do Twitter {#publish-on-tw}

Siga as etapas abaixo para postar uma mensagem em sua conta do Twitter:

1. Criar um delivery de Twitter

   Crie um novo delivery com base no template de delivery **[!UICONTROL Tweet (twitter)]**.

   ![](assets/tw-new-delivery.png)

1. Seleção do público alvo principal

   Selecione as contas para as quais deseja enviar tweets.

   ![](assets/tw-define-target.png)

   1. Clique no link **[!UICONTROL To]**.
   1. Clique no botão **[!UICONTROL Add]**.
   1. Selecione **[!UICONTROL A Twitter account]**.
   1. No campo **[!UICONTROL Folder]** selecione a pasta de serviço que contém a conta do Twitter. Em seguida selecione a conta do Twitter para a qual deseja enviar o tweet.

1. Selecionar o público alvo da prova

   A guia **[!UICONTROL Target of the proofs]** permite definir a conta do Twitter a ser usada para deliveries de teste antes do delivery final.

   Conforme detalhado na [etapas de configuração](../connect/ac-tw.md#tw-test-account), você deve criar uma conta Twitter de teste privada dedicada ao envio de provas.

   >[!NOTE]
   >
   >Se estiver usando a mesma conta de teste do Twitter para todos os deliveries, você pode salvar o target de prova no template de delivery **[!UICONTROL Tweet]**, acessível pelo nó **[!UICONTROL Resources > Templates > Delivery templates]**. O target de prova será preenchido por padrão para cada novo delivery.

1. Definir o conteúdo da publicação

   Insira o conteúdo da publicação no **[!UICONTROL Content]** guia .

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >Ao postar no Twitter, as limitações se aplicam:
   >
   >* A mensagem não pode exceder 140 caracteres.
   >* Não há suporte para o formato HTML.


1. Visualizar sua publicação

   Navegue pelo **[!UICONTROL Preview]** para verificar a renderização da publicação.

   ![](assets/tw-delivery-preview.png)

   1. Clique na guia **[!UICONTROL Preview]**.
   1. Clique no menu suspenso **[!UICONTROL Test personalization]** e selecione **[!UICONTROL Service]**.
   1. No campo **[!UICONTROL Folder]**, selecione a pasta de serviço que contém a conta do Twitter.

1. Enviar uma prova

   Antes de postar seu tweet, valide-o enviando uma prova de sua publicação: você pode obter uma renderização exata da publicação em uma página de teste privada do Twitter.

1. Postar a mensagem

   1. Depois que o conteúdo for aprovado, clique no botão **[!UICONTROL Send]**.
   1. Selecione **[!UICONTROL Deliver as soon as possible]** e clique no botão **[!UICONTROL Analyze]**.
   1. Quando a análise for concluída, verifique o resultado.
   1. Clique em **[!UICONTROL Confirm delivery]** e depois em **[!UICONTROL Yes]**.

## Enviar mensagens diretas aos seguidores {#direct-tw-messages}

O **[!UICONTROL Synchronize Twitter accounts]** o workflow técnico recupera a lista de seguidores do Twitter para que você possa enviar mensagens diretas a eles. [Saiba mais](../connect/ac-tw.md#synchro-tw-accounts)

Para enviar mensagens diretas aos seus seguidores, siga as etapas abaixo:

1. Crie um delivery de Twitter com base na variável **[!UICONTROL Tweet (Direct Message)]** template do delivery incorporado.

1. Seleção do público alvo principal

   ![](assets/tw-dm-define-target.png)

   1. Selecione o **[!UICONTROL To]** e o **[!UICONTROL Add]** botão.

   1. Escolha um tipo de direcionamento

      * Selecionar **[!UICONTROL Twitter subscribers]** para enviar uma mensagem direta a todos os seus seguidores.

      * Selecione **[!UICONTROL Filter conditions]** para definir uma consulta e visualizar seu resultado. Saiba como criar um filtro em [esta seção](../audiences/create-filters.md#advanced-filters).

1. Selecione o target da prova no **[!UICONTROL Target of the proofs]** guia : esta conta receberá a prova da sua mensagem direta.

   Conforme detalhado na [etapas de configuração](../connect/ac-tw.md#tw-test-account), você deve criar uma conta Twitter de teste privada dedicada ao envio de provas.


   >[!NOTE]
   >
   >Se desejar enviar todas as provas de mensagem direta para a mesma conta do Twitter, você pode salvar o target de prova no **[!UICONTROL Tweet (Direct Message)]** template do delivery , acessível pelo **[!UICONTROL Resources > Templates > Delivery templates]** nó .

1. Insira o conteúdo da mensagem no **[!UICONTROL Content]** guia .

   ![](assets/tw-dm-content.png)

   Campos de personalização podem ser usados da mesma forma que para deliveries por email, por exemplo, para adicionar o nome do seguidor no corpo da mensagem. Saiba mais [nesta seção](../start/create-message.md#personalization).

1. Visualizar sua mensagem

   Navegue pelo **[!UICONTROL Preview]** para verificar a renderização da publicação.

   ![](assets/tw-dm-preview.png)

   1. Clique na guia **[!UICONTROL Preview]**.
   1. Clique no menu suspenso **[!UICONTROL Test personalization]** e selecione **[!UICONTROL Visitor Subscription]**.
   1. Escolha uma conta do Twitter com a qual deseja testar a visualização.

1. Enviar uma prova

   Antes de enviar a mensagem, valide-a enviando uma prova para uma conta de teste: você pode obter uma renderização exata da mensagem em uma conta privada do Twitter e verificar o conteúdo e a personalização.

   ![](../assets/do-not-localize/book.png) [Saiba mais sobre as principais etapas para validar um delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=pt-BR){target="_blank"}

1. Enviar a mensagem direta

   1. Depois que o conteúdo for aprovado, clique no botão **[!UICONTROL Send]**.
   1. Selecione **[!UICONTROL Deliver as soon as possible]** e clique no botão **[!UICONTROL Analyze]**.
   1. Quando a análise for concluída, verifique o resultado.
   1. Clique em **[!UICONTROL Confirm delivery]** e depois em **[!UICONTROL Yes]**.

>[!CAUTION]
>
>Não é possível enviar mais de 250 mensagens diretas por dia. Para evitar exceder esse limite, é possível entregar em ondas. Para obter mais informações, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en#sending-using-multiple-waves){target="_blank"}.


## Acessar dados de rastreamento {#tw-tracking}

No **[!UICONTROL Tweet]** do delivery, o rastreamento é ativado por padrão.

Os dados de rastreamento podem ser exibidos nos relatórios do delivery e no **[!UICONTROL Edit > Tracking]** do delivery e do serviço.

A configuração de rastreamento é a mesma de um delivery de email. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=pt-BR){target="_blank"}.

