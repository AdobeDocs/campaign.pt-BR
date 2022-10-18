---
title: Matriz de compatibilidade do Campaign v8
description: Conheça os sistemas e as versões compatíveis com o Campaign v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 9ae93ce4e2b0424bb3b3862b2c7d016309bd630e
workflow-type: ht
source-wordcount: '374'
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

### Sistemas operacionais

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11 (a partir do Campaign v8.3), 10, 8

>[!NOTE]
>
>O Microsoft Windows 10 é recomendado para instâncias em japonês.

### Navegador

**Microsoft Edge**

### Microsoft WebView2 Runtime

<table>
<tbody>
<tr>
<td>
<p>WebView2 Runtime do Microsoft Edge
</p>
</td>
<td>
<p>Versão mais recente</p>
</td>
<td>
<p><a href="http://www.adobe.com/go/acc-ms-webview2-runtime-download_br">Baixar do site Desenvolvedor Microsoft</a></p>
</td>
</tr>
</tbody>
</table>

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

* **Android** 12 (a partir do Campaign v8.3), 9.0, 8.x e 7.x com o SDK Campaign Android build 1.1.1.
* **Apple iOS** 9 - 16 com o SDK Campaign iOS build 1.0.26, compatível com versões de 32 e 64 bits. O iOS 16 é compatível a partir do Campaign v8.4.


## Acesso à Web

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
