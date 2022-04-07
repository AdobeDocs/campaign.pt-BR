---
title: Enviar SMS com o Adobe Campaign
description: Introdução ao SMS no Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 15%

---

# Criar e enviar SMS

Use o Adobe Campaign para enviar mensagens SMS personalizadas.

![](../assets/do-not-localize/book.png) Saiba como começar a usar o canal SMS em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;}

>[!NOTE]
>
>O Adobe Campaign também permite enviar notificações por push em dispositivos móveis, por meio de **Canal de Aplicativo Adobe Campaign Mobile (NMAC)** opção. Saiba mais [nesta seção](push.md).

## Configurar canal de SMS

Para enviar para um celular, você precisa:

* Uma conta externa especificando um conector e tipo de mensagem.

* Um template do delivery no qual essa conta externa é referenciada.

![](../assets/do-not-localize/book.png)  Saiba como configurar um canal SMS em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;}

Antes de começar a enviar SMS:

* Verifique se os perfis de recipient contêm pelo menos um celular em seus perfis.
* Revisar a Adobe Campaign Classic [Práticas recomendadas para delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target=&quot;_blank&quot;} que também se aplica ao Campaign v8.

Além disso, você precisa conhecer o protocolo e as configurações do SMS. Percorra a conexão configurada entre o Adobe Campaign e um provedor SMPP em [este documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

## Criar seu primeiro delivery de SMS

1. Para criar um novo delivery, navegue até o **[!UICONTROL Campaigns]** clique em **[!UICONTROL Deliveries]** e clique no botão **[!UICONTROL Create]** acima da lista de deliveries existentes.

   ![](assets/delivery_step_1.png)

   ![](../assets/do-not-localize/book.png) Para obter informações globais sobre como criar um delivery, consulte [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

1. Selecione um template do delivery que faça referência à conta externa relevante para enviar deliveries de SMS.

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) Saiba como criar uma conta externa SMPP em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}

   ![](../assets/do-not-localize/book.png) Saiba como criar um template do delivery para delivery em dispositivos móveis no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}

1. Identifique o delivery com um rótulo, código e descrição.

1. Clique em **[!UICONTROL Continue]** para confirmar e exibir a janela de configuração de mensagem.

1. Insira o conteúdo da mensagem no **[!UICONTROL Text content]** seção do assistente, incluindo campos de personalização, conforme necessário.

   ![](assets/sms-content.png)

1. Selecionar o público-alvo.

As principais etapas para criar e projetar um SMS são detalhadas na documentação do Campaign Classic v7:

* Criar um SMS

   ![](../assets/do-not-localize/book.png) [Saiba como criar um delivery de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Design do conteúdo do SMS

   ![](../assets/do-not-localize/book.png) [Saiba como definir o conteúdo do SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* Selecione o público do seu email

   ![](../assets/do-not-localize/book.png) [Saiba como definir a população do target](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) As etapas para definir um público-alvo são detalhadas em [esta página](../start/audiences.md).

## Testar o SMS

Para exibir a renderização da mensagem com sua personalização, clique em **[!UICONTROL Preview]** e selecione um recipient.

![](assets/sms-preview.png)

Para enviar uma prova, consulte estas seções da documentação do Campaign Classic v7:

* Validar um delivery e enviar provas
   ![](../assets/do-not-localize/book.png) [Saiba mais sobre as principais etapas para validar um delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* Adicionar seed addresses
   ![](../assets/do-not-localize/book.png) [Saiba mais sobre seed addresses](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## Enviar e monitorar deliveries de SMS

As principais etapas para enviar e monitorar um SMS estão detalhadas na documentação do Campaign Classic v7:

* Enviar, monitorar e rastrear entregas de SMS

   ![](../assets/do-not-localize/book.png) [Saiba mais sobre as ferramentas para enviar, monitorar e rastrear o SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Solução de problemas de deliveries de SMS

   ![](../assets/do-not-localize/book.png) [Saiba mais sobre a solução de problemas de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
