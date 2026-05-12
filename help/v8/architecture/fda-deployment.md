---
title: Introdução à implantação do FDA do Campaign
description: Introdução à implantação do FDA do Campaign
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
TQID: https://experienceleague.adobe.com/PfXTlEYfwkN9YRDIx44TdtZLjNZJkHqN73sJGxA0c-E
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: ee3dfd63-9a21-4961-9f24-ea3385284a21
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 329
ht-degree: 0%

---

# Implantação do FDA do [!DNL Campaign]{#gs-fda}

Em sua implantação FDA (padrão) do Campaign, o [!DNL Adobe Campaign] v8 pode ser conectado ao [!DNL Snowflake] para acessar dados por meio do recurso [Federated Data Access](../connect/fda.md): você pode acessar e processar dados externos e informações armazenados no banco de dados do [!DNL Snowflake] sem alterar a estrutura dos dados do Adobe Campaign.

>[!NOTE]
>
>Neste modelo de implantação, o banco de dados secundário [!DNL Snowflake] está disponível somente mediante solicitação. Para atualizar sua implantação com o [!DNL Snowflake], contate o Adobe Transition Manager.
>

## Benefícios{#fda-benefits}

Esse modelo de implantação vem com os seguintes benefícios:

* **Armazenamento e desempenhos**
Você pode mover seus dados históricos para [!DNL Snowflake] e reduzir dependências para o limite de Adobe Campaign IDs. Essa arquitetura também reduz sua dependência do armazenamento PostgreSQL e limites de desempenho. À medida que menos dados são armazenados no banco de dados do Campaign, o desempenho é melhor e as tarefas de manutenção são executadas mais rapidamente.

* **Extensão do modelo de dados e gerenciamento de dados**
Você pode criar tabelas em [!DNL Snowflake] e vinculá-las ao Adobe Campaign, por exemplo, para usar dados arquivados por períodos de retenção ou executar processos de segmentação com desempenhos pendentes.

  Essa arquitetura também permite usar os recursos de fluxo de trabalho de gerenciamento de dados no [!DNL Snowflake]. Somente agregações e tabelas temporárias são movidas para o Campaign para fins de personalização e delivery.


## Arquitetura{#fda-archi}

Com esse modelo de implantação, os usuários do Adobe Campaign podem estender seus dados para o [!DNL Snowflake] e aproveitar os benefícios de uma plataforma de dados única e integrada para obter insights avançados de dados de campanhas de marketing em tempo real. Ele oferece aos usuários a capacidade de desbloquear grandes valores de seus dados, oferecendo uma plataforma única, unificada e fácil de usar para análise de dados. A plataforma de dados em nuvem não requer gerenciamento, pois é dimensionada infinitamente para suportar qualquer volume de dados de marketing do Adobe Campaign.

A comunicação geral entre servidores e processos é realizada de acordo com o seguinte esquema:

![](assets/fda-architecture.png)

O PostgreSQL é o banco de dados principal e o Snowflake pode ser usado como o banco de dados secundário. Você pode estender seu modelo de dados e armazenar seus dados no Snowflake. Posteriormente, é possível executar ETL, segmentação e relatórios em um grande conjunto de dados com desempenhos excelentes.
