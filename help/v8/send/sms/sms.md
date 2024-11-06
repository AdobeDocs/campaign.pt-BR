---
title: Enviar SMS com o Adobe Campaign
description: Introdução ao SMS no Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 5b2638927e39b6f839fb3a8639fe106d2c519fbf
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---

# Introdução a SMS {#gs-sms-channel}

O Adobe Campaign permite entregar [SMS](../send/sms/sms.md) personalizado em dispositivos móveis.

Para mensagens SMS, você poderá criar, modificar e personalizar mensagens somente no formato de texto. Você também poderá visualizar suas mensagens SMS antes de enviá-las.

>[!NOTE]
>
>Você também pode usar o Adobe Campaign para enviar mensagens de [LINE](../send/line.md), com texto e/ou imagens e links.

Para enviar SMS para um telefone celular com o Adobe Campaign, é necessário:

* Uma conta externa configurada no canal **[!UICONTROL Mobile (SMS)]** ou no canal **[!UICONTROL LINE]**.
* Um template do delivery de SMS que esteja vinculado corretamente a essa conta externa.

Você pode ver nesta documentação as etapas para configurar, enviar e monitorar um delivery de SMS:

* **Configurar canal de SMS**

Primeiro, você precisa configurar o canal de SMS na sua [infraestrutura de mid-sourcing](sms-mid-sourcing.md).

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

Para esta configuração, você precisa entender os [parâmetros de conta externa SMPP](smpp-external-account.md) e as [características do canal SMS](sms-channel.md).

Após esta configuração, verifique sua conexão [SMPP e saiba como solucionar problemas, se necessário](smpp-connection.md).

* **Criar sua primeira entrega de SMS**

Para começar a configuração do delivery de SMS:

1. Crie sua entrega e preencha as [configurações de entrega de SMS](sms-delivery-settings.md),

1. [Definir o conteúdo](sms-content.md) da sua entrega,

1. [Selecione a audiência](sms-audience.md).

As etapas para definir um público estão detalhadas em [esta página](../../audiences/create-audiences.md).

* **Validar e enviar SMS**

Após a criação do delivery:

1. [Enviar provas](sms-proofs.md) para validar a renderização e o conteúdo,

1. Em seguida, [envie para o público final](sms-send.md).

* **Monitorar e rastrear SMS**

Após o envio, [saiba como monitorar e rastrear o SMS](sms-monitor.md).
