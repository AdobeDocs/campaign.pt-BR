---
title: Enviar SMS com o Adobe Campaign
description: Introdução ao SMS no Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 18%

---

# Criar e enviar SMS

Use o Adobe Campaign para enviar mensagens SMS personalizadas.

Saiba como começar a usar o canal de SMS na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target="_blank"}

>[!NOTE]
>
>O Adobe Campaign também permite enviar notificações por push em dispositivos móveis, através da sua opção **Adobe Campaign Mobile App Channel (NMAC)**. Saiba mais [nesta seção](push.md).

## Configurar canal de SMS

Para enviar para um celular, você precisa:

* Uma conta externa especificando um conector e tipo de mensagem.

* Um template da entrega no qual essa conta externa é referenciada.

Saiba como configurar um canal de SMS na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#sending-messages){target="_blank"}

Antes de começar a enviar SMS:

* Verifique se os perfis de destinatário contêm pelo menos um celular em seus perfis.
* Revise as [Práticas recomendadas de entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=pt-BR#sending-messages){target="_blank"} do Adobe Campaign Classic que também se aplicam ao Campaign v8.

Além disso, você precisa conhecer o protocolo e as configurações de SMS. Percorra a conexão configurada entre o Adobe Campaign e um provedor SMPP em [este documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html#sending-messages){target="_blank"}.

## Criar sua primeira entrega de SMS

1. Para criar uma nova entrega, navegue até a guia **[!UICONTROL Campaigns]**, clique em **[!UICONTROL Deliveries]** e no botão **[!UICONTROL Create]** acima da lista de entregas existentes.

   ![](assets/delivery_step_1.png)

   Para obter informações globais sobre como criar um delivery, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html#sending-messages){target="_blank"}.

1. Selecione um template do delivery que faça referência à conta externa relevante para enviar deliveries de SMS.

   ![](assets/sms-template-list.png)

   Saiba como criar uma conta externa SMPP na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#creating-an-smpp-external-account){target="_blank"}

   Saiba como criar um modelo de entrega para dispositivos móveis na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#changing-the-delivery-template){target="_blank"}

1. Identifique o delivery com um rótulo, código e descrição.

1. Clique em **[!UICONTROL Continue]** para confirmar e exibir a janela de configuração de mensagem.

1. Insira o conteúdo da mensagem na seção **[!UICONTROL Text content]** do assistente, incluindo campos de personalização, conforme necessário.

   ![](assets/sms-content.png)

1. Selecione a população do target.

As principais etapas para criar e projetar um SMS estão detalhadas na documentação do Campaign Classic v7:

* Criar um SMS

  [Saiba como criar uma entrega de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#sending-messages){target="_blank"}

* Criar o conteúdo do SMS

  [Saiba como definir o conteúdo de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#defining-the-sms-content){target="_blank"}

* Selecionar a audiência do seu email

  [Saiba como definir a população alvo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

As etapas para definir um público estão detalhadas em [esta página](../start/audiences.md).

## Testar o SMS

Para exibir a renderização da mensagem com sua personalização, clique em **[!UICONTROL Preview]** e selecione um destinatário.

![](assets/sms-preview.png)

Para enviar uma prova, consulte estas seções da documentação do Campaign Classic v7:

* Validar um delivery e enviar provas
  [Saiba mais sobre as principais etapas para validar uma entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=pt-BR){target="_blank"}
* Adicionar seed addresses
  [Saiba mais sobre seed addresses](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## Enviar e monitorar deliveries de SMS

As principais etapas para enviar e monitorar um SMS estão detalhadas na documentação do Campaign Classic v7:

* Enviar, monitorar e rastrear entregas de SMS

  [Saiba mais sobre as ferramentas para enviar, monitorar e rastrear SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html#sending-messages){target="_blank"}

* Solução de problemas de deliveries de SMS

  [Saiba mais sobre Solução de Problemas de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html#sending-messages){target="_blank"}
