---
solution: Campaign
product: Adobe Campaign
title: Matriz de compatibilidade do Campaign v8
description: Conheça os sistemas e as versões compatíveis com o Campaign v8
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
translation-type: tm+mt
source-git-commit: e94080bc5e56e642494de48ff4b739b806c6e2e7
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 34%

---

# Matriz de compatibilidade do Campaign v8

Este documento lista todos os sistemas e componentes compatíveis com a última build do **Adobe Campaign v8**. Os produtos e as versões que não estão nessa lista não são compatíveis com o Adobe Campaign.

>[!CAUTION]
>
>* Salvo indicação em contrário, todas as versões secundárias são compatíveis.
>* À medida que versões específicas desses sistemas e ferramentas de terceiros atingem o fim da vida útil (EOL), a Adobe Campaign não será mais compatível com essas versões e elas serão removidas dessa matriz de compatibilidade. Verifique se você está usando as versões compatíveis dos sistemas listadas na matriz de compatibilidade para evitar problemas.


## Sistemas compatíveis

### Conectores CRM{#CRMconnectors}

* **** API do Salesforceconnector versão 49
* **Microsoft** Dynamics connector, Web API: Dynamics 365 No local e Online

### Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Análise do Microsoft Azure Synapse**
* **Amazon Redshift**
* **[!DNL Snowflake]**
* **Oracle** 19c, 18c, 12c, 11G
* **PostgreSQL** 12.x, 11.x, 10.x, 9.6.x, 9.5.x, 9.4.x
* **Microsoft SQL Server** 2019, 2017, 2016, 2014, 2012 SP1 e SP2
* **MySQL** 5.7
* **Teradata** 16.20, 16, 15.10, 15.0
* **Netezza** 7.2
* **sybase IQ** 16, ASE 15.7
* **SAP** HANA versão 1 SPS 12
* **Hadoop via HiveSQL**
   * HortonWorks HDP 2.4.X, 2.5.x, 2.6.x
   * HDInsight 3.4 (HDP 2.4), 3.5 (HDP 2.5), 3.6 (HDP 2.6
   * Cloudera CDH6.x

### Sistemas operacionais do console do cliente{#ClientConsoleoperatingsystems}

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (recomendado para instâncias japonesas)

## Console do cliente {#ClientConsoleoperatingsystems}

:warning: Os seguintes sistemas operacionais e navegadores são necessários para usar o Console do Cliente do Campaign.

### Sistemas operacionais

<table>
<tbody>
<tr>
<td>Microsoft Windows Server</td>
<td>
<p>2016</p>
<p>2012</p>
</td>
</tr>
<tr>
<td>Microsoft Windows</td>
<td>
<p>8</p>
<p>10 (recomendado para instâncias em japonês)</p>
</td>
</tr>
</tbody>
</table>

### Navegador

<table>
<tbody>
<tr>
<td>
<p>Microsoft Internet Explorer</p>
</td>
<td>
<p>11</p>
</td>
</tr>
</tbody>
</table>

### Mobile SDK{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 com o SDK móvel build 1.0.27.
* **Apple iOS** 9 - 14 com SDK móvel build 1.0.26, compatível com as versões de 32 e 64 bits.

## Navegadores compatíveis {#Browsers}

Os seguintes navegadores são compatíveis com o Campaign for Web Access.

* **Microsoft Edge**,  **Mozilla Firefox**,  **Google Chrome**,  **Safari**  (versões mais recentes)

* **Internet Explorer** 11

## Como verificar a versão do Campaign

O menu **Help > About..** permite que você acesse as seguintes informações:

* o número da versão para o Console do cliente do Campaign e o servidor de aplicativos
* o número de compilação do Console do Cliente do Campaign e do servidor de aplicativos
* um link para entrar em contato com o Atendimento ao cliente da Adobe
* links para Política de privacidade da Adobe, Termos de uso e Política de cookies
