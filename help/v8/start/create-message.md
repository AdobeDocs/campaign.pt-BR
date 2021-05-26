---
solution: Campaign v8
product: Adobe Campaign
title: Introdução a mensagens
description: Introdução a mensagens
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 25%

---

# Introdução a mensagens{#gs-ac-audiences}

Com o Adobe Campaign, você pode enviar campanhas em vários canais, incluindo emails, SMS, notificações por push e mala direta, e medir sua eficácia usando vários relatórios dedicados. Essas mensagens são projetadas e enviadas por deliveries, além disso podem ser personalizadas para cada recipient.

As funcionalidades principais incluem definição de metas, definição e personalização de mensagens, execução de comunicações e relatórios operacionais associados. O principal ponto de acesso funcional é o assistente de delivery. Esse ponto de acesso leva a vários recursos cobertos pelo Adobe Campaign.

Saiba mais sobre as principais etapas para criar um delivery na documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html).

O Adobe Campaign v8 vem com os seguintes canais de delivery:

* **Canal de email**: deliveries de email permitem enviar emails personalizados para a população do target. Saiba mais [nesta página](../send/email.md).

* **Canal de mala direta**: deliveries de mala direta permitem gerar um arquivo de extração que contém dados sobre a população do target.  Saiba mais [nesta página](../send/direct-mail.md)

* **Canal** móvel: deliveries em canais móveis permitem enviar SMS personalizado para a população do target.  Saiba mais [nesta página](../send/sms.md)

* **Canal de aplicativo móvel**: os deliveries por aplicativo móvel permitem enviar as notificações para sistemas iOs e Android.  Saiba mais [nesta página](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Escolha como enviar suas mensagens

Depois que a mensagem tiver sido criada e o conteúdo tiver sido criado e testado, você poderá escolher como deseja enviá-la. O Campaign oferece um conjunto de recursos para:

* Enviar mensagens manualmente para o target principal
   [!DNL :arrow_upper_right:] [Saiba como enviar mensagens](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* Enviar mensagens associadas a uma [campanha de marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)
   [!DNL :arrow_upper_right:] [Saiba como enviar mensagens no contexto de uma campanha](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html).
* Enviar mensagens por meio de um [workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
   [!DNL :arrow_upper_right:] [Saiba como automatizar deliveries de email](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [Acionar ](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) mensagens de um evento
   [!DNL :arrow_upper_right:] [Caso de uso: saiba como enviar um email transacional com um anexo](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* Agendar suas mensagens
   [!DNL :arrow_upper_right:] [Caso de uso: saiba como agendar e enviar email de aniversário](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## Adicionar personalização

As mensagens entregues pelo Adobe Campaign podem ser personalizadas de várias maneiras.

Você pode:

* Inserir campos de personalização dinâmicos.
   [!DNL :arrow_upper_right:] Saiba como usar campos de personalização na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* Inserir blocos de personalização predefinidos.
   [!DNL :arrow_upper_right:] Saiba o que é um bloco de personalização e como usá-lo na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)
* Criar conteúdo condicional.
   [!DNL :arrow_upper_right:] Saiba como inserir conteúdo condicional na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)

## Enviar mensagens transacionais

As mensagens transacionais (Centro de Mensagens) são o módulo do Campaign criado para gerenciar mensagens por disparo.

[!DNL :bulb:] Saiba mais sobre o recurso de mensagens transacionais  [nesta seção](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] As etapas para configurar e enviar mensagens transacionais estão detalhadas  [nesta página](../send/transactional.md)

[!DNL :arrow_upper_right:] Descubra esse recurso em um caso de uso completo na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)

## Logs de rastreamento e delivery

O monitoramento de deliveries após serem enviados é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes. Você pode monitorar após enviar um delivery, bem como entender como as falhas de delivery e as quarentenas são gerenciadas.

[!DNL :arrow_upper_right:] [Saiba como monitorar suas entregas nesta seção](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**Tópicos relacionados**

[!DNL :arrow_upper_right:]  [Práticas recomendadas de delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

[!DNL :arrow_upper_right:]  [Testar e enviar um email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

[!DNL :arrow_upper_right:]  [Enviar provas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
