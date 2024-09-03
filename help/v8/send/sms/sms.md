---
title: Enviar SMS com o Adobe Campaign
description: Introdução ao SMS no Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
badge: label="Disponibilidade limitada" type="Informative"
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: af1d453179c2d739eca243b435dec90a4b8e2dd5
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 7%

---

# Introdução a SMS {#gs-sms-channel}

Use o Adobe Campaign para enviar mensagens SMS personalizadas.

>[!IMPORTANT]
>
>Esta documentação é para o Adobe Campaign v8.7.2 e posteriores.
>
>Para versões mais antigas, leia a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

>[!NOTE]
>
>O Adobe Campaign também permite enviar notificações por push em dispositivos móveis, através da sua opção **Adobe Campaign Mobile App Channel (NMAC)**. Saiba mais [nesta seção](../push.md).

A simplicidade e a facilidade de uso do SMS fazem dele um canal de comunicação muito valioso, além de sua robustez e compatibilidade incomparável em bilhões de terminais.

Há duas maneiras principais de enviar um SMS:

* Enviá-lo manualmente por telefone. Essa é a maneira usual de se comunicar diretamente entre as pessoas.
* Enviá-lo pela Internet. É assim que o Adobe Campaign usa o para enviar mensagens. Para isso, você precisa de um provedor de serviço SMS que faça uma ponte da Internet para a rede móvel.

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
