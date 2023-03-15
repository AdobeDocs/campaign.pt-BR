---
title: Matriz de compatibilidade do Campaign v8
description: Conheça os sistemas e as versões compatíveis com o Campaign v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 2ec240b139394ce8f54a5835a4fa7bd377d226eb
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 100%

---

# Matriz de compatibilidade do Campaign v8

Este documento lista todos os sistemas e componentes compatíveis com o último build do **Adobe Campaign v8**. Salvo indicação em contrário, todas as versões secundárias são compatíveis. Os produtos e as versões que não estão nessa lista não são compatíveis com o Adobe Campaign.

À medida que versões específicas desses sistemas e ferramentas de terceiros atingirem o fim da vida útil (EOL), o Adobe Campaign não será mais compatível com essas versões, e elas serão removidas da matriz de compatibilidade. Verifique se você está usando as versões compatíveis dos sistemas listados na matriz de compatibilidade para evitar problemas.

>[!NOTE]
>
>O Servidor e o Console do Cliente do Adobe Campaign devem estar na mesma versão. [Saiba como verificar sua versão](#version).

## Console do cliente{#ClientConsoleoperatingsystems}

Os sistemas operacionais e navegadores a seguir são necessários para usar o Console do Cliente do Campaign. [Saiba mais](connect.md).

### Sistemas operacionais{#op-systems}

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11, 10, 8

### Navegador da Web{#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, versão mais recente. Baixe do [Site do desenvolvedor da Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_br){target="_blank"}.

## Conectores CRM{#CRMconnectors}

Os sistemas de gerenciamento de relacionamento com o cliente (CRM) compatíveis com o Adobe Campaign estão listados abaixo. [Saiba mais](../connect/crm.md).

* API do conector **Salesforce** versão 49
* Conector do **Microsoft Dynamics**, API da Web: Dynamics 365 local e online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Os bancos de dados externos compatíveis com o módulo Federated Data Access (FDA) do Adobe Campaign estão listados abaixo. [Saiba mais](../connect/fda.md).

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## SDK móvel{#MobileSDK}

Você pode usar o Campaign para enviar [notificações por push](../send/push.md) nos sistemas operacionais listados abaixo, usando o SDK para dispositivos móveis associado.

* **Android** 12, 9.0, 8.x, 7.x, com o Campaign Android SDK build 1.1.1.
* **Apple iOS** 9 - 16 com o SDK Campaign iOS build 1.0.26, compatível com versões de 32 e 64 bits. O Apple iOS 16 é compatível a partir do Campaign v8.4.


## Acesso à Web{#web-access}

Os seguintes navegadores são compatíveis com o Campaign para [acesso via web](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versões mais recentes)

## Como verificar a versão e build do Campaign{#version}

Use o menu **Ajuda > Sobre...** para verificar sua versão.

![](assets/ac-version.png)

Você acessa as seguintes informações:

* O número da **versão** do console do cliente e do servidor de aplicativos. Na amostra acima, a versão é 8.1.5 para o console do cliente e para o servidor de aplicativos.
* O número SHA, entre parênteses.
* Um link para entrar em contato com o Atendimento ao cliente da Adobe.
* Links para Política de privacidade da Adobe, Termos de uso e Política de cookies.
