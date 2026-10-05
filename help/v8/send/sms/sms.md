---
title: Enviar SMS com o Adobe Campaign
description: Introdução ao SMS no Campaign
feature: SMS
role: User, Developer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
TQID: 'https://experienceleague.adobe.com/7ChOYJmYScxaAoqnruyMv-8n0AkXgYAIlt1783hTjvY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 34%
---
# Introdução a SMS {#gs-sms-channel}

Use o Adobe Campaign para enviar mensagens de texto aos seus clientes em seus dispositivos móveis. Você pode criar, personalizar e visualizar mensagens em formato de texto no editor de SMS.

Para enviar SMS para dispositivos móveis com o Adobe Campaign, é necessário:

* Uma conta externa configurada no canal **[!UICONTROL Mobile (SMS)]**. Saiba como configurar o canal de SMS na sua [infraestrutura de mid-sourcing](sms-mid-sourcing.md). Para esta configuração, você precisa entender os [parâmetros de conta externa SMPP](smpp-external-account.md) e as [características do canal SMS](sms-channel.md).
Após essa configuração, verifique a conexão SMPP e saiba como solucionar problemas, se necessário. [Saiba mais](smpp-connection.md).

* Um template do delivery de SMS que esteja vinculado corretamente a essa conta externa.

O Adobe Campaign oferece suporte a dois conectores SMS usados para enviar mensagens SMS aos seus clientes. [Saiba mais](sms-connectors.md).

>[!NOTE]
>
>Você também pode usar o Adobe Campaign para enviar [notificações por push](../push.md) e [LINE](../line/line.md) mensagens para dispositivos móveis.

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="Criar SMS" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>Criar uma entrega de SMS</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="Conteúdo de SMS" src="../../assets/do-not-localize/sms-create.jpeg">
</a>
<div>
<a href="sms-content.md"><strong>Definir seu conteúdo de SMS</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="Público-alvo de SMS" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>Selecionar o público-alvo</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="Configuração de SMS" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>Configurar canal de SMS</strong></a>
</div>
<p>
</td>
</tr></table>
