---
title: Matriz de compatibilidade do Campaign v8
description: Conheça os sistemas e as versões compatíveis com o Campaign v8
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: ht
source-wordcount: '406'
ht-degree: 100%

---

# Matriz de compatibilidade do Campaign v8 {#compat-matrix}

Este documento lista todos os sistemas e componentes compatíveis com a última build do console do cliente do **Adobe Campaign v8**. Salvo indicação em contrário, todas as versões secundárias são compatíveis. Os produtos e as versões que não estão nessa lista não são compatíveis com o Adobe Campaign.

À medida que versões específicas desses sistemas e ferramentas de terceiros atingirem o fim da vida útil (EOL), o Adobe Campaign não será mais compatível com essas versões, e elas serão removidas da matriz de compatibilidade. Verifique se você está usando as versões compatíveis dos sistemas listados na matriz de compatibilidade para evitar problemas.

>[!NOTE]
>
>Os consoles do servidor e do cliente do Adobe Campaign devem ter a mesma versão. [Saiba como verificar sua versão](upgrades.md#version).

## Console do cliente {#ClientConsoleoperatingsystems}

Os sistemas operacionais e navegadores a seguir são necessários para usar o console do cliente do Campaign. [Saiba mais](connect.md).

### Sistemas operacionais {#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11, 10

>[!NOTE]
>A versão de 32 bits do console do cliente está obsoleta desde a versão 8.5. A partir da versão 8.6, o console do cliente só estará disponível em 64 bits. Para mais informações sobre como atualizar o seu sistema operacional, consulte esta [nota técnica](../../technotes/upgrades/console.md).

### Navegador da Web {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, versão mais recente. Baixe do [Site do desenvolvedor da Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_br){target="_blank"}.

## Conectores CRM {#CRMconnectors}

Os sistemas de gerenciamento de relacionamento com o cliente (CRM) compatíveis com o Adobe Campaign estão listados abaixo. Saiba mais sobre conectores CRM [nesta página](../connect/crm.md).

* API do conector **Salesforce** versão 49
* Conector do **Microsoft Dynamics**, API da Web: Dynamics 365 local e online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Os bancos de dados externos compatíveis com o módulo Federated Data Access (FDA) do Adobe Campaign estão listados abaixo. Saiba mais sobre FDA [nesta página](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, a partir do Campaign v8.5
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## SDK móvel {#MobileSDK}

Para enviar [notificações por push](../send/push.md) com o Campaign, use o SDK móvel da Adobe Experience Platform configurando a extensão do Adobe Campaign Classic na interface da coleção de dados.

As versões compatíveis com iOS e Android estão detalhadas na [documentação do Adobe Developer](https://developer.adobe.com/client-sdks/home/){target="_blank"}.

## Interface da Web {#web-ui}

Os seguintes navegadores são compatíveis com a interface do Campaign Web. Saiba mais sobre a interface do Campaign Web [nesta página](campaign-ui.md#ac-web-ui).

* **Microsoft Edge**, **Google Chrome**, **Safari** (versões mais recentes)

## Acesso à Web {#web-access}

Os seguintes navegadores são compatíveis com Campaign para o acesso a partir da Web. Saiba mais sobre o acesso ao Campaign Web [nesta página](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versões mais recentes)

## Recursos adicionais {#support}

* [Atualizações da versão do Campaign](upgrades.md)
* [Confira a sua versão do Campaign](upgrades.md#version)
* [Instalar o console do cliente do Campaign](connect.md)
* [Versões do painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=pt-BR){target="_blank"}.

Para manter-se em dia sobre novas versões de soluções da Experience Cloud, inscreva-se na [Atualização prioritária de produtos da Adobe](https://www.adobe.com/br/subscription/priority-product-update.html){target="_blank"}.