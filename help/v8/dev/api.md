---
title: 'Introdução às APIs do Campaign '
description: 'Introdução às APIs do Campaign '
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 391eac2f5e4d4c8c5d4dadd3394798361640e1d8
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 12%

---

# Introdução às APIs [!DNL Campaign]{#gs-ac-api}

[!DNL Adobe Campaign] O vem com um conjunto de funções Javascript que você pode usar:

* em Scripts - em [!DNL Adobe Campaign] workflows
* por APIs - de sistemas externos

Você pode usar APIs do JavaScript para gravar no banco de dados da nuvem do Campaign ou ler a partir do banco de dados:

* APIs específicas de negócios que permitem agir em cada objeto: deliveries, workflows, subscrições e assim por diante. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html).
* APIs genéricas de acesso aos dados para consultar os dados do modelo de dados. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html).

O Campaign v8 funciona com dois bancos de dados: um banco de dados local para a interface do usuário, mensagens em tempo real e consultas unitárias e gravação por meio de APIs, e um banco de dados da nuvem para execução de campanha, relatórios, assimilação de dados, consultas em lote e execução de workflows.

>[!CAUTION]
>
>[!DNL Adobe Campaign] O v8 vem com um limite na taxa de transferência (TPS) da nossa camada de API. Quebrar o limite leva a um erro HTTP padrão (429). Como usuário do Managed Cloud Services, você pode entrar em contato com o Adobe para adaptar o controle de cada API.

## Pré-requisitos

Antes de usar [!DNL Adobe Campaign] APIs, é necessário conhecer os seguintes tópicos:

* JavaScript
* Protocolo SOAP
* [!DNL Adobe Campaign] datamodel

Para usar APIs e interagir com [!DNL Adobe Campaign], você também deve estar familiarizado com o modelo de dados.

>[!NOTE]
>Você pode gerar uma descrição completa do seu modelo de dados. Saiba mais [nesta página](datamodel.md).

## [!DNL Campaign] Mecanismo de preparo da API

Com o [!DNL Campaign] banco de dados da nuvem, as chamadas unitárias de explosão não são recomendadas devido ao desempenho (latência e simultaneidade). A operação em lote é sempre preferida. Para garantir desempenho ideal das APIs, o Campaign continua lidando com chamadas de API no nível do banco de dados local.

![](../assets/do-not-localize/glass.png) [O mecanismo de preparo da API é detalhado nesta página](staging.md)

## Novas APIs

Novas APIs estão disponíveis para gerenciar a sincronização de dados entre o banco de dados local [!DNL Campaign] e o banco de dados da nuvem. Um novo mecanismo também foi introduzido para lidar com chamadas de API no nível do banco de dados local, a fim de evitar latência e aumentar o desempenho geral.

![](../assets/do-not-localize/glass.png) [As novas APIs são detalhadas nesta página](new-apis.md)

**Tópicos relacionados**

* [Práticas recomendadas do modelo de dados](datamodel-best-practices.md)
