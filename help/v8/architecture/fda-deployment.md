---
title: Introdução à implantação do FDA do Campaign
description: Introdução à implantação do FDA do Campaign
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 561e4b6d2c99e98e068132c80c2bebb756b60a44
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# [!DNL Campaign] Implantação do FDA{#gs-fda}

Na implantação do FDA do Campaign (padrão), [!DNL Adobe Campaign] O v8 pode ser conectado ao [!DNL Snowflake] para acessar os dados por meio de [Federated Data Access](../connect/fda.md) recurso: você pode acessar e processar dados e informações externos armazenados em seu [!DNL Snowflake] banco de dados sem alterar a estrutura dos dados do Adobe Campaign.

>[!NOTE]
>
>Neste modelo de implantação, a variável [!DNL Snowflake] o banco de dados secundário está disponível somente mediante solicitação. Para atualizar sua implantação com [!DNL Snowflake], entre em contato com o Gerente de transição de Adobe.
>

## Benefícios{#fda-benefits}

Esse modelo de implantação vem com os seguintes benefícios:

* **Armazenamento e desempenho**
Você pode mover seus dados históricos para [!DNL Snowflake] e, em seguida, reduzir as dependências ao limite de Adobe Campaign IDs. Essa arquitetura também reduz sua dependência do armazenamento PostgreSQL e limites de desempenho. À medida que menos dados são armazenados no banco de dados do Campaign, o desempenho é melhor e as tarefas de manutenção são executadas mais rapidamente.

* **Extensão do modelo de dados e gerenciamento de dados**
É possível criar tabelas em [!DNL Snowflake] e os vincule ao Adobe Campaign, por exemplo, para usar dados arquivados durante períodos de retenção ou executar processos de segmentação com desempenhos excepcionais.

  Essa arquitetura também permite usar os recursos de fluxo de trabalho de gerenciamento de dados no [!DNL Snowflake]. Somente agregações e tabelas temporárias são movidas para o Campaign para fins de personalização e delivery.


## Arquitetura{#fda-archi}

Com esse modelo de implantação, os usuários do Adobe Campaign podem estender seus dados para [!DNL Snowflake] e aproveite os benefícios de uma plataforma de dados única e integrada para obter insights avançados de dados de campanhas de marketing em tempo real. Ele oferece aos usuários a capacidade de desbloquear grandes valores de seus dados, oferecendo uma plataforma única, unificada e fácil de usar para análise de dados. A plataforma de dados em nuvem não requer gerenciamento, pois é dimensionada infinitamente para suportar qualquer volume de dados de marketing do Adobe Campaign.

A comunicação geral entre servidores e processos é realizada de acordo com o seguinte esquema:

![](assets/fda-architecture.png)

O PostgreSQL é o banco de dados principal e o Snowflake pode ser usado como o banco de dados secundário. Você pode estender seu modelo de dados e armazenar seus dados no Snowflake. Posteriormente, é possível executar ETL, segmentação e relatórios em um grande conjunto de dados com desempenhos excelentes.
