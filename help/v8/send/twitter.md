---
title: Publicar mensagens no Twitter com o Adobe Campaign
description: Saiba como usar o módulo Adobe Campaign Social Marketing para postar mensagens no Twitter e enviar mensagens diretas aos seus seguidores
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 37%

---


# Publicar mensagens no Twitter com o Adobe Campaign {#post-tw-messages}

O Adobe Campaign vem com uma **Marketing social** módulo que permite interagir com seus clientes atuais e potenciais via Twitter.

Após configurar a integração, é possível:

* Enviar mensagens diretas aos seus seguidores
* Postar tweets na sua conta do Twitter
* Colete novos contatos recuperando os dados do perfil, o que permite realizar campanhas de direcionamento e, quando possível, implementar estratégias entre canais. Esta ação requer o consentimento do usuário.


As etapas de configuração para integrar sua conta do Twitter com o Adobe Campaign estão descritas em [esta página](../connect/ac-tw.md).

## Criar e publicar uma publicação do Twitter {#publish-on-tw}

Siga as etapas abaixo para postar uma mensagem em sua conta da Twitter:

1. Criar uma entrega do Twitter

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

   Conforme detalhado no [etapas de configuração](../connect/ac-tw.md#tw-test-account), você deve criar uma conta privada de teste do Twitter dedicada ao envio de provas.

   >[!NOTE]
   >
   >Se estiver usando a mesma conta de teste do Twitter para todos os deliveries, você pode salvar o target de prova no template de delivery **[!UICONTROL Tweet]**, acessível pelo nó **[!UICONTROL Resources > Templates > Delivery templates]**. O target de prova será preenchido por padrão para cada novo delivery.

1. Definir o conteúdo da publicação

   Insira o conteúdo da sua publicação no **[!UICONTROL Content]** guia.

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >Ao postar no Twitter, as limitações se aplicam:
   >
   >* A mensagem não pode exceder 140 caracteres.
   >* Formato HTML não suportado.


1. Visualizar sua publicação

   Navegue pelo **[!UICONTROL Preview]** para verificar a renderização da publicação.

   ![](assets/tw-delivery-preview.png)

   1. Clique na guia **[!UICONTROL Preview]**.
   1. Clique no menu suspenso **[!UICONTROL Test personalization]** e selecione **[!UICONTROL Service]**.
   1. No campo **[!UICONTROL Folder]**, selecione a pasta de serviço que contém a conta do Twitter.

1. Enviar uma prova

   Antes de publicar seu tweet, valide-o enviando uma prova de sua publicação: você pode obter uma renderização exata da publicação em uma página de teste privada do Twitter.

1. Postar a mensagem

   1. Depois que o conteúdo for aprovado, clique no botão **[!UICONTROL Send]**.
   1. Selecione **[!UICONTROL Deliver as soon as possible]** e clique no botão **[!UICONTROL Analyze]**.
   1. Quando a análise for concluída, verifique o resultado.
   1. Clique em **[!UICONTROL Confirm delivery]** e depois em **[!UICONTROL Yes]**.

## Enviar mensagens diretas aos seguidores {#direct-tw-messages}

A variável **[!UICONTROL Synchronize Twitter accounts]** o workflow técnico recupera a lista de seguidores do Twitter para que você possa enviar mensagens diretas a eles. [Saiba mais](../connect/ac-tw.md#synchro-tw-accounts)

Para enviar mensagens diretas aos seus seguidores, siga as etapas abaixo:

1. Crie um delivery do Twitter com base na **[!UICONTROL Tweet (Direct Message)]** modelo de entrega integrado.

1. Seleção do público alvo principal

   ![](assets/tw-dm-define-target.png)

   1. Selecione o **[!UICONTROL To]** e o link **[!UICONTROL Add]** botão.

   1. Escolha um tipo de direcionamento

      * Selecionar **[!UICONTROL Twitter subscribers]** para enviar uma mensagem direta a todos os seus seguidores.

      * Selecione **[!UICONTROL Filter conditions]** para definir uma consulta e visualizar seu resultado. Saiba como criar um filtro no [nesta seção](../audiences/create-filters.md#advanced-filters).

1. Selecione o público alvo da prova na **[!UICONTROL Target of the proofs]** guia: essa conta receberá a prova da mensagem direta.

   Conforme detalhado no [etapas de configuração](../connect/ac-tw.md#tw-test-account), você deve criar uma conta privada de teste do Twitter dedicada ao envio de provas.


   >[!NOTE]
   >
   >Se desejar enviar todas as provas de mensagem direta para a mesma conta do Twitter, você pode salvar o target de prova na variável **[!UICONTROL Tweet (Direct Message)]** template do delivery, acessado pelo **[!UICONTROL Resources > Templates > Delivery templates]** nó.

1. Insira o conteúdo da mensagem nas **[!UICONTROL Content]** guia.

   ![](assets/tw-dm-content.png)

   Campos de personalização podem ser usados da mesma forma que para deliveries por email, por exemplo, para adicionar o nome do seguidor no corpo da mensagem. Saiba mais [nesta seção](../send/personalize.md).

1. Visualizar sua mensagem

   Navegue pelo **[!UICONTROL Preview]** para verificar a renderização da publicação.

   ![](assets/tw-dm-preview.png)

   1. Clique na guia **[!UICONTROL Preview]**.
   1. Clique no menu suspenso **[!UICONTROL Test personalization]** e selecione **[!UICONTROL Visitor Subscription]**.
   1. Escolha uma conta do Twitter com a qual deseja testar a visualização.

1. Enviar uma prova

   Antes de enviar a mensagem, valide-a enviando [envio de uma prova para uma conta de teste](../send/preview-and-proof.md): você pode obter uma renderização exata da mensagem em uma conta privada do Twitter e verificar o conteúdo e a personalização.

1. Enviar a mensagem direta

   1. Depois que o conteúdo for aprovado, clique no botão **[!UICONTROL Send]**.
   1. Selecione **[!UICONTROL Deliver as soon as possible]** e clique no botão **[!UICONTROL Analyze]**.
   1. Quando a análise for concluída, verifique o resultado.
   1. Clique em **[!UICONTROL Confirm delivery]** e depois em **[!UICONTROL Yes]**.

>[!CAUTION]
>
>Não é possível enviar mais de 250 mensagens diretas por dia. Para não exceder esse limite, é possível entregar em ondas. Para obter mais informações, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target="_blank"}.


## Acessar dados de rastreamento {#tw-tracking}

No incorporado **[!UICONTROL Tweet]** template do delivery, o rastreamento é ativado por padrão.

Os dados de rastreamento podem ser exibidos nos relatórios do delivery e na **[!UICONTROL Edit > Tracking]** do delivery e do serviço.

A configuração de rastreamento é a mesma de um delivery de email. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=pt-BR){target="_blank"}.

