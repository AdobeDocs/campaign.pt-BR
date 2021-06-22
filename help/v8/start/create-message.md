---
product: Adobe Campaign
title: Introdução a mensagens
description: Introdução a mensagens
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 83%

---

# Introdução a mensagens{#gs-ac-audiences}

Com o Adobe Campaign, você pode enviar campanhas entre canais, incluindo e-mails, SMS, notificações push e correspondências diretas e medir a eficiência usando vários relatórios dedicados. Essas mensagens são projetadas e enviadas por deliveries, além disso podem ser personalizadas para cada recipient.

As funcionalidades principais incluem definição de metas, definição e personalização de mensagens, execução de comunicações e relatórios operacionais associados. O principal ponto de acesso funcional é o assistente de entrega. Esse ponto de acesso leva a vários recursos cobertos pelo Adobe Campaign.

Saiba mais sobre as principais etapas para criar uma entrega na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=pt-BR).

O Adobe Campaign v8 vem com os seguintes canais de entrega:

* **Canal de email**: entregas de email permitem enviar emails personalizados para a população do target. Saiba mais [nesta página](../send/email.md).

* **Canal de correspondência direta**: entregas de correspondência direta permitem gerar um arquivo de extração que contém dados sobre a população do target.  Saiba mais [nesta página](../send/direct-mail.md)

* **Canal móvel**: entregas em canais móveis permitem enviar SMS personalizado para a população do target.  Saiba mais [nesta página](../send/sms.md)

* **Canal de aplicativo móvel**: as entregas por aplicativo móvel permitem enviar as notificações para sistemas iOS e Android.  Saiba mais [nesta página](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Escolha como enviar suas mensagens

Depois que a mensagem for criada e o conteúdo testado, você poderá escolher como deseja enviá-la. O Campaign oferece um conjunto de recursos para:

* Enviar mensagens manualmente para o target principal

   ![](assets/send-email.png)

   [!DNL :arrow_upper_right:] Saiba como enviar mensagens na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=pt-BR){target=&quot;_blank&quot;}

* Enviar mensagens associadas a uma [campanha de marketing](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png)

   [!DNL :arrow_upper_right:] Saiba como enviar mensagens no contexto de uma campanha na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=pt-BR){target=&quot;_blank&quot;}

* Enviar mensagens por meio de um [fluxo de trabalho](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   [!DNL :arrow_upper_right:] Saiba como automatizar deliveries de email na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=pt-BR){target=&quot;_blank&quot;}

* [Acionar mensagens ](../send/transactional.md) de um evento
   [!DNL :arrow_upper_right:] [Caso de uso: saiba como enviar um email transacional com um anexo](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=en){target=&quot;_blank&quot;}

* Agendar suas mensagens

   ![](assets/schedule-send.png)

   [!DNL :arrow_upper_right:] [Caso de uso: saiba como agendar e enviar um email de aniversário](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=pt-BR){target=&quot;_blank&quot;}


## Adicionar personalização

As mensagens entregues pelo Adobe Campaign podem ser personalizadas de várias maneiras.

Você pode:

* Inserir campos de personalização dinâmicos.
   [!DNL :arrow_upper_right:] Saiba como usar campos de personalização na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=pt-BR){target=&quot;_blank&quot;}
* Inserir blocos de personalização predefinidos.
   [!DNL :arrow_upper_right:] Saiba o que é um bloco de personalização e como usá-lo na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=pt-BR){target=&quot;_blank&quot;}
* Criar conteúdo condicional.
   [!DNL :arrow_upper_right:] Saiba como inserir conteúdo condicional na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=pt-BR){target=&quot;_blank&quot;}

## Enviar mensagens transacionais

O envio de mensagens transacionais (Centro de mensagens) é o módulo do Campaign criado para gerenciar mensagens de acionador.

[!DNL :bulb:] Saiba mais sobre o recurso de mensagens transacionais [nesta seção](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] As etapas para configurar e enviar mensagens transacionais são detalhadas [nesta página](../send/transactional.md)

[!DNL :arrow_upper_right:] Conheça esse recurso em um caso de uso completo na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=pt-BR){target=&quot;_blank&quot;}

## Logs de rastreamento e entrega

O monitoramento de entregas após serem enviados é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes. Você pode monitorar após enviar uma entrega, bem como entender como as falhas de entrega e as quarentenas são gerenciadas.

[!DNL :arrow_upper_right:] Saiba como monitorar seus deliveries na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html#sending-messages){target=&quot;_blank&quot;}


**Documentação relacionada** do Campaign Classic v7:

[!DNL :arrow_upper_right:]  [Práticas recomendadas para delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=pt-BR){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:]  [Teste e envie um email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:]  [Enviar provas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=pt-BR){target=&quot;_blank&quot;}
