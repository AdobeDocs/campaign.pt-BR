---
title: Matriz de compatibilidade do Campaign v8
description: Conheça os sistemas e as versões compatíveis com o Campaign v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: dcb12339d891c61f308cf7b7e518784f3ba1ff31
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 88%

---

# Matriz de compatibilidade do Campaign v8

Este documento lista todos os sistemas e componentes compatíveis com o último build do **Adobe Campaign v8**. Salvo indicação em contrário, todas as versões secundárias são compatíveis. Os produtos e as versões que não estão nessa lista não são compatíveis com o Adobe Campaign.

À medida que versões específicas desses sistemas e ferramentas de terceiros atingirem o fim da vida útil (EOL), o Adobe Campaign não será mais compatível com essas versões, e elas serão removidas da matriz de compatibilidade. Verifique se você está usando as versões compatíveis dos sistemas listados na matriz de compatibilidade para evitar problemas.

>[!NOTE]
>
>O Servidor e o Console do Cliente do Adobe Campaign devem estar na mesma versão. [Saiba como verificar sua versão](#version).

## Console do cliente{#ClientConsoleoperatingsystems}

Os sistemas operacionais e navegadores a seguir são necessários para usar o Console do Cliente do Campaign. [Saiba mais](connect.md).

>[!NOTE]
>
>Observe que a versão de 32 bits do Console do cliente será substituída na versão 8.5. A partir do 8.6, o Console do cliente só estará disponível em 64 bits. Para obter mais informações sobre como atualizar seu sistema operacional, consulte esta seção [nota técnica](https://experienceleague.corp.adobe.com/docs/campaign/technotes-ac/tn-new/console.html).

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

Para enviar [notificações por push](../send/push.md) com o Campaign, use o SDK móvel da Adobe Experience Platform configurando a extensão do Adobe Campaign Classic na interface da coleção de dados.


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
