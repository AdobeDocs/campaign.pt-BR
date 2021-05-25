---
solution: Campaign v8
product: Adobe Campaign
title: Introdução às APIs do Campaign
description: Introdução às APIs do Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 5%

---

# Introdução às APIs [!DNL Campaign]{#gs-ac-api}

[!DNL Adobe Campaign] O vem com um conjunto de funções Javascript que você pode usar:

* em Scripts - em [!DNL Adobe Campaign] workflows
* por APIs - de sistemas externos

Você pode usar APIs do Javascript para gravar no banco de dados da nuvem do Campaign ou ler a partir do banco de dados:

* APIs específicas de negócios que permitem agir em cada objeto: deliveries, workflows, subscrições etc. Saiba mais em [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html).
* APIs genéricas de acesso aos dados para consultar os dados do modelo de dados. Saiba mais em [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html).

O Campaign v8 funciona com dois bancos de dados: um banco de dados local para a interface do usuário, mensagens em tempo real e consultas unitárias e gravação por meio de APIs, e um banco de dados da nuvem para execução de campanha, relatórios, assimilação de dados, consultas em lote e execução de workflows.

>[!CAUTION]
>
>[!DNL Adobe Campaign] O v8 vem com um limite na taxa de transferência (TPS) da nossa camada de API. Quebrar o limite leva a um erro HTTP padrão (429). Como usuário do Managed Cloud Services, você pode entrar em contato com o Adobe para adaptar o controle de cada API.


## Pré-requisitos

Antes de usar [!DNL Adobe Campaign] APIs, é necessário conhecer os seguintes tópicos:

* Javascript
* Protocolo SOAP
* [!DNL Adobe Campaign] datamodel

Para usar APIs e interagir com [!DNL Adobe Campaign], você também precisa estar familiarizado com seu modelo de dados.

>[!NOTE]
>Você pode gerar uma descrição completa do seu modelo de dados. Saiba mais [nesta página](datamodel.md).

## [!DNL Campaign] Mecanismo de preparo da API

Com o [!DNL Campaign] banco de dados da nuvem, as chamadas unitárias de explosão não são recomendadas devido ao desempenho (latência e simultaneidade). A operação em lote é sempre preferida. Para garantir desempenho ideal das APIs, o Campaign continua lidando com chamadas de API no nível do banco de dados local.

:bulb: [O mecanismo de preparo da API é detalhado nesta página](staging.md)

## Novas APIs

Novas APIs estão disponíveis para gerenciar a sincronização de dados entre o banco de dados local [!DNL Campaign] e o banco de dados da nuvem. Um novo mecanismo também foi introduzido para lidar com chamadas de API no nível do banco de dados local para evitar latência e aumentar o desempenho geral

:bulb: [Novas APIs são detalhadas nesta página](new-apis.md)

**Tópicos relacionados**

* [Práticas recomendadas do Modelo de dados](datamodel-best-practices.md)
