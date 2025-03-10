---
title: Enviar SMS com o Adobe Campaign
description: Introdução ao SMS no Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 95dca48ae0e2ee82b80464cdf9414538776969ad
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 12%

---

# Introdução a SMS {#gs-sms-channel}

Use o Adobe Campaign para enviar mensagens de texto aos seus clientes em seus dispositivos móveis. Você pode criar, personalizar e visualizar mensagens no formato de texto do editor de SMS.

Para enviar SMS para dispositivos móveis com o Adobe Campaign, é necessário:

* Uma conta externa configurada no canal **[!UICONTROL Mobile (SMS)]**. Saiba como configurar o canal de SMS na sua [infraestrutura de mid-sourcing](sms-mid-sourcing.md). Para esta configuração, você precisa entender os [parâmetros de conta externa SMPP](smpp-external-account.md) e as [características do canal SMS](sms-channel.md).
Após essa configuração, verifique a conexão SMPP e saiba como solucionar problemas, se necessário. [Saiba mais](smpp-connection.md).

* Um template do delivery de SMS que esteja vinculado corretamente a essa conta externa.


>[!NOTE]
>
>Você também pode usar o Adobe Campaign para enviar [notificações por push](../push.md) e [LINE](../line.md) mensagens para dispositivos móveis.


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
<a href="sms-audience.md"><strong>Selecionar a audiência</strong></a>
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
