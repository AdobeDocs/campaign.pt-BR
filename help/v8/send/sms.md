---
title: Enviar SMS com o Adobe Campaign
description: Introdução ao SMS no Campaign
feature: SMS
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 19%

---

# Criar e enviar SMS

Use o Adobe Campaign para enviar mensagens SMS personalizadas.

![](../assets/do-not-localize/book.png) Saiba como começar a usar o canal de SMS no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target="_blank"}

>[!NOTE]
>
>O Adobe Campaign também permite enviar notificações por push em dispositivos móveis, por meio de **Canal de aplicativo móvel Adobe Campaign (NMAC)** opção. Saiba mais [nesta seção](push.md).

## Configurar canal de SMS

Para enviar para um celular, você precisa:

* Uma conta externa especificando um conector e tipo de mensagem.

* Um template do delivery no qual essa conta externa é referenciada.

![](../assets/do-not-localize/book.png)  Saiba como configurar um canal de SMS no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#sending-messages){target="_blank"}

Antes de começar a enviar SMS:

* Verifique se os perfis de recipient contêm pelo menos um celular em seus perfis.
* Revisar a Adobe Campaign Classic [Práticas recomendadas de entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"} que também se aplicam ao Campaign v8.

Além disso, você precisa conhecer o protocolo e as configurações de SMS. Veja a conexão configurada entre o Adobe Campaign e um provedor SMPP no [este documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html#sending-messages){target="_blank"}.

## Criar sua primeira entrega de SMS

1. Para criar um novo delivery, navegue até o **[!UICONTROL Campaigns]** clique em **[!UICONTROL Deliveries]** e clique no link **[!UICONTROL Create]** acima da lista de deliveries existentes.

   ![](assets/delivery_step_1.png)

   ![](../assets/do-not-localize/book.png) Para obter informações gerais sobre como criar um delivery, consulte [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html#sending-messages){target="_blank"}.

1. Selecione um template do delivery que faça referência à conta externa relevante para enviar deliveries de SMS.

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) Saiba como criar uma conta externa SMPP no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#creating-an-smpp-external-account){target="_blank"}

   ![](../assets/do-not-localize/book.png) Saiba como criar um template do delivery para celulares no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#changing-the-delivery-template){target="_blank"}

1. Identifique o delivery com um rótulo, código e descrição.

1. Clique em **[!UICONTROL Continue]** para confirmar e exibir a janela de configuração de mensagem.

1. Insira o conteúdo da mensagem nas **[!UICONTROL Text content]** do assistente, incluindo campos de personalização, conforme necessário.

   ![](assets/sms-content.png)

1. Selecionar o público-alvo.

As principais etapas para criar e projetar um SMS estão detalhadas na documentação do Campaign Classic v7:

* Criar um SMS

   ![](../assets/do-not-localize/book.png) [Saiba como criar uma entrega de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#sending-messages){target="_blank"}

* Criar o conteúdo do SMS

   ![](../assets/do-not-localize/book.png) [Saiba como definir o conteúdo de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#defining-the-sms-content){target="_blank"}

* Selecionar a audiência do seu email

   ![](../assets/do-not-localize/book.png) [Saiba como definir a população alvo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

![](../assets/do-not-localize/glass.png) As etapas para definir um público são detalhadas em [esta página](../start/audiences.md).

## Testar o SMS

Para exibir a renderização da mensagem com sua personalização, clique em **[!UICONTROL Preview]** e selecione um recipient.

![](assets/sms-preview.png)

Para enviar uma prova, consulte estas seções da documentação do Campaign Classic v7:

* Validar um delivery e enviar provas
   ![](../assets/do-not-localize/book.png) [Saiba mais sobre as principais etapas para validar um delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=pt-BR){target="_blank"}
* Adicionar seed addresses
   ![](../assets/do-not-localize/book.png) [Saiba mais sobre seed addresses](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## Enviar e monitorar deliveries de SMS

As principais etapas para enviar e monitorar um SMS estão detalhadas na documentação do Campaign Classic v7:

* Enviar, monitorar e rastrear entregas de SMS

   ![](../assets/do-not-localize/book.png) [Saiba mais sobre as ferramentas para enviar, monitorar e rastrear SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html#sending-messages){target="_blank"}

* Solução de problemas de deliveries de SMS

   ![](../assets/do-not-localize/book.png) [Saiba mais sobre solução de problemas de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html#sending-messages){target="_blank"}
