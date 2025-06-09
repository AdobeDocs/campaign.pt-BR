---
title: Postar mensagens no X (Twitter) com o Adobe Campaign
description: Saiba como usar o módulo Adobe Campaign Social Marketing para postar mensagens no X (antigo Twitter) e enviar mensagens diretas aos seus seguidores
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 24%

---


# Postar mensagens no X (Twitter) com o Adobe Campaign {#post-tw-messages}

O Adobe Campaign vem com um módulo de **Marketing Social** que permite interagir com seus clientes e clientes potenciais via X (anteriormente conhecido como Twitter).

Após configurar a integração, é possível:

* Enviar mensagens diretas aos seus seguidores
* Publicar em sua conta do X
* Colete novos contatos recuperando os dados do perfil, o que permite realizar campanhas de direcionamento e, quando possível, implementar estratégias entre canais. Esta ação requer o consentimento do usuário.


As etapas de configuração para integrar sua conta X com o Adobe Campaign estão descritas em [esta página](../connect/ac-tw.md).

## Criar e publicar uma publicação no X {#publish-on-tw}

Siga as etapas abaixo para postar uma mensagem em sua conta X:

1. Criar um delivery X

   Crie uma nova entrega com base no template de entrega **[!UICONTROL Tweet (twitter)]**.

   ![](assets/tw-new-delivery.png)

1. Seleção do público alvo principal

   Selecione as contas para as quais deseja enviar publicações.

   ![](assets/tw-define-target.png)

   1. Clique no link **[!UICONTROL To]**.
   1. Clique no botão **[!UICONTROL Add]**.
   1. Selecione **[!UICONTROL A Twitter account]**.
   1. No campo **[!UICONTROL Folder]**, selecione a pasta de serviço que contém a conta X. Em seguida, selecione a conta X para a qual deseja enviar o tweet.

1. Selecionar o público alvo da prova

   A guia **[!UICONTROL Target of the proofs]** permite definir a conta X a ser usada para deliveries de teste antes do delivery final.

   Conforme detalhado nas [etapas de configuração](../connect/ac-tw.md#tw-test-account), você deve criar uma conta X de teste privada dedicada ao envio de provas.

   >[!NOTE]
   >
   >Se estiver usando a mesma conta de teste X para todas as entregas, você pode salvar o público alvo de prova no modelo de entrega **[!UICONTROL Tweet]**, acessível através do nó **[!UICONTROL Resources > Templates > Delivery templates]**. O target de prova será preenchido por padrão para cada nova entrega.

1. Definir o conteúdo da publicação

   Insira o conteúdo da sua publicação na guia **[!UICONTROL Content]**.

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >Ao fazer uma postagem em X, as limitações se aplicam:
   >
   >* A mensagem não pode exceder 140 caracteres.
   >* O formato HTML não é compatível.
   >

1. Visualizar sua publicação

   Navegue pela guia **[!UICONTROL Preview]** para verificar a renderização da sua publicação.

   ![](assets/tw-delivery-preview.png)

   1. Clique na guia **[!UICONTROL Preview]**.
   1. Clique no menu suspenso **[!UICONTROL Test personalization]** e selecione **[!UICONTROL Service]**.
   1. No campo **[!UICONTROL Folder]**, selecione a pasta de serviço que contém a conta X.

1. Enviar uma prova

   Antes de publicar seu tweet, valide-o enviando uma prova de sua publicação: você pode obter uma renderização exata da publicação em uma página de teste X privada.

1. Postar a mensagem

   1. Depois que o conteúdo for aprovado, clique no botão **[!UICONTROL Send]**.
   1. Selecione **[!UICONTROL Deliver as soon as possible]** e clique no botão **[!UICONTROL Analyze]**.
   1. Quando a análise for concluída, verifique o resultado.
   1. Clique em **[!UICONTROL Confirm delivery]** e depois em **[!UICONTROL Yes]**.

## Enviar mensagens diretas aos seguidores {#direct-tw-messages}

O fluxo de trabalho técnico **[!UICONTROL Synchronize Twitter accounts]** recupera a lista de X seguidores para que você possa enviar mensagens diretas a eles. [Saiba mais](../connect/ac-tw.md#synchro-tw-accounts)

Para enviar mensagens diretas aos seus seguidores, siga as etapas abaixo:

1. Crie uma entrega X com base no modelo de entrega interno **[!UICONTROL Tweet (Direct Message)]**.

1. Seleção do público alvo principal

   ![](assets/tw-dm-define-target.png)

   1. Selecione o link **[!UICONTROL To]** e o botão **[!UICONTROL Add]**.

   1. Escolha um tipo de direcionamento

      * Selecione **[!UICONTROL Twitter subscribers]** para enviar uma mensagem direta a todos os seus seguidores.

      * Selecione **[!UICONTROL Filter conditions]** para definir uma consulta e visualizar seu resultado. Saiba como criar um filtro em [esta seção](../audiences/create-filters.md#advanced-filters).

1. Selecione o público alvo da prova na guia **[!UICONTROL Target of the proofs]**: essa conta receberá a prova da sua mensagem direta.

   Conforme detalhado nas [etapas de configuração](../connect/ac-tw.md#tw-test-account), você deve criar uma conta X de teste privada dedicada ao envio de provas.


   >[!NOTE]
   >
   >Se desejar enviar todas as provas de mensagem direta para a mesma conta X, você pode salvar o público alvo de prova no modelo de entrega **[!UICONTROL Tweet (Direct Message)]**, acessível através do nó **[!UICONTROL Resources > Templates > Delivery templates]**.

1. Insira o conteúdo da mensagem na guia **[!UICONTROL Content]**.

   ![](assets/tw-dm-content.png)

   Campos de personalização podem ser usados da mesma forma que para entregas por email, por exemplo, para adicionar o nome do seguidor no corpo da mensagem. Saiba mais [nesta seção](../send/personalize.md).

1. Visualizar sua mensagem

   Navegue pela guia **[!UICONTROL Preview]** para verificar a renderização da sua publicação.

   ![](assets/tw-dm-preview.png)

   1. Clique na guia **[!UICONTROL Preview]**.
   1. Clique no menu suspenso **[!UICONTROL Test personalization]** e selecione **[!UICONTROL Visitor Subscription]**.
   1. Escolha uma conta X com a qual deseja testar a visualização.

1. Enviar uma prova

   Antes de enviar a mensagem, valide-a [enviando uma prova para uma conta de teste](../send/preview-and-proof.md): você pode obter uma renderização exata da mensagem em uma conta X privada e verificar o conteúdo e a personalização.

1. Enviar a mensagem direta

   1. Depois que o conteúdo for aprovado, clique no botão **[!UICONTROL Send]**.
   1. Selecione **[!UICONTROL Deliver as soon as possible]** e clique no botão **[!UICONTROL Analyze]**.
   1. Quando a análise for concluída, verifique o resultado.
   1. Clique em **[!UICONTROL Confirm delivery]** e depois em **[!UICONTROL Yes]**.

>[!CAUTION]
>
>Não é possível enviar mais de 250 mensagens diretas por dia. Para não exceder esse limite, é possível entregar em ondas. Para obter mais informações, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target="_blank"}.


## Acessar dados de rastreamento {#tw-tracking}

No modelo de entrega **[!UICONTROL Tweet]** interno, o rastreamento é habilitado por padrão.

Os dados de rastreamento podem ser exibidos nos relatórios do delivery e na guia **[!UICONTROL Edit > Tracking]** do delivery e do serviço.

A configuração de rastreamento é a mesma de uma entrega de email. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=pt-BR){target="_blank"}.

