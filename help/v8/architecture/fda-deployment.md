---
title: Introdução à implantação do FDA-Snowflake do Campaign
description: Introdução à implantação do FDA-Snowflake do Campaign
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] implantação{#gs-fda-snowflake}

Em um [!DNL Snowflake] Implantação FDA (padrão), [!DNL Adobe Campaign] v8 está conectado a [!DNL Snowflake] para acessar dados por meio de [Federated Data Access](../connect/fda.md) capacidade: você pode acessar e processar dados externos e informações armazenadas em [!DNL Snowflake] banco de dados sem alterar a estrutura dos dados do Adobe Campaign.

## Benefícios{#fda-benefits}

Este modelo de implantação vem com os seguintes benefícios:

* **Armazenamento e desempenho**
Você pode mover seus dados históricos para [!DNL Snowflake] e, em seguida, reduzir as dependências do limite das Adobe Campaign IDs. Essa arquitetura também reduz sua dependência para os limites de armazenamento e desempenho do PostgreSQL. À medida que menos dados são armazenados no banco de dados do Campaign, o desempenho é melhor e as tarefas de manutenção são executadas mais rapidamente.

* **Extensão do modelo de dados e gerenciamento de dados**
Você pode criar tabelas em [!DNL Snowflake] e vincule-os à Adobe Campaign, por exemplo, para usar dados arquivados durante os períodos de retenção, ou para executar processos de segmentação com desempenho excepcional.

   Essa arquitetura também permite usar os recursos do fluxo de trabalho de gerenciamento de dados no [!DNL Snowflake]. Somente agregações e tabelas temporárias são movidas para o Campaign para fins de personalização e delivery.


## Arquitetura{#fda-archi}

Com esse modelo de implantação, os usuários do Adobe Campaign podem estender seus dados para [!DNL Snowflake] e aproveite os benefícios de uma plataforma de dados única e integrada para obter insights avançados de dados de campanha de marketing em tempo real. Ele fornece aos usuários a capacidade de liberar um valor profundo de seus dados, oferecendo uma plataforma única, unificada e de fácil uso para análise de dados. A plataforma de dados em nuvem não requer gerenciamento, pois é dimensionada infinitamente para suportar qualquer volume de dados de marketing do Adobe Campaign.

A comunicação geral entre servidores e processos é realizada de acordo com o seguinte schema:

![](assets/fda-architecture.png)

O PostgreSQL é o banco de dados principal e o Snowflake é o banco de dados secundário. Você pode estender seu modelo de dados e armazenar seus dados no Snowflake. Posteriormente, é possível executar ETL, segmentação e relatórios em um grande conjunto de dados com desempenho excepcional.
