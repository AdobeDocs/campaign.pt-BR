---
solution: Campaign v8
product: Adobe Campaign
title: Matriz de compatibilidade do Campaign v8
description: Conheça os sistemas e as versões compatíveis com o Campaign v8
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: ffdfc9a2e1bec191b5a3cc7f7b40683b2456bf3e
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 31%

---

# Matriz de compatibilidade do Campaign v8

Este documento lista todos os sistemas e componentes compatíveis com a última build do **Adobe Campaign v8**. Os produtos e as versões que não estão nessa lista não são compatíveis com o Adobe Campaign.

>[!CAUTION]
>
>* Salvo indicação em contrário, todas as versões secundárias são compatíveis.
>* À medida que versões específicas desses sistemas e ferramentas de terceiros atingem o fim da vida útil (EOL), a Adobe Campaign não será mais compatível com essas versões e elas serão removidas dessa matriz de compatibilidade. Verifique se você está usando as versões compatíveis dos sistemas listadas na matriz de compatibilidade para evitar problemas.


## Sistemas compatíveis

### Console do cliente{#ClientConsoleoperatingsystems}

:aviso: os seguintes sistemas operacionais e navegadores são necessários para usar o Console do cliente do Campaign.

**Sistemas operacionais**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (recomendado para instâncias japonesas)

**Navegador**

**Microsoft Internet Explorer** 11

### Conectores CRM{#CRMconnectors}

* **** API do Salesforceconnector versão 49
* **Microsoft** Dynamics connector, Web API: Dynamics 365 No local e Online

### Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Snowflake]**

### SDK móvel{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 com o SDK móvel build 1.0.27.
* **Apple iOS** 9 - 14 com SDK móvel build 1.0.26, compatível com as versões de 32 e 64 bits.

### Navegadores compatíveis {#Browsers}

Os seguintes navegadores são compatíveis com o Campaign for Web Access.

* **Microsoft Edge**,  **Mozilla Firefox**,  **Google Chrome**,  **Safari**  (versões mais recentes)

* **Internet Explorer** 11

## Como verificar a versão do Campaign

Use o menu **Ajuda > Sobre...** para verificar sua versão.

![](assets/ac-version.png)

Você acessa as seguintes informações:

* O número **version** do console do cliente e do servidor de aplicativos. Na amostra acima, a versão é 8.1.5 para o console do cliente e para o servidor de aplicativos.
* O número SHA, entre parênteses.
* Um link para entrar em contato com o Atendimento ao cliente do Adobe.
* Links para Política de privacidade do Adobe, Termos de uso e Política de cookies.
