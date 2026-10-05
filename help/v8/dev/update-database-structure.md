---
title: Atualizar a estrutura do banco de dados
description: Atualizar a estrutura do banco de dados
feature: Configuration
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
TQID: 'https://experienceleague.adobe.com/1UBvvvkN-05BqOe4aOMpYFtKEMp0Yf-q9ECtbtmHzb0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 0%
---
# Atualizar a estrutura do banco de dados {#updating-the-database-structure}

Para aplicar as modificações feitas nos esquemas, inicie o assistente de atualização do banco de dados. Este assistente pode ser acessado via **[!UICONTROL Tools > Advanced > Update database structure]**. Ele verifica se a estrutura física do banco de dados corresponde à sua descrição lógica e executa os scripts de atualização SQL.

![](assets/schema_update.png)

Os módulos no banco de dados são automaticamente preenchidos e ativados.

![](assets/schema_update_select2.png)

Siga as etapas e exiba o script SQL de atualização do banco de dados:

![](assets/schema_update2.png)

>[!NOTE]
>
>Está em um campo de edição e pode ser modificado para excluir ou adicionar o código SQL.

Em seguida, inicie a atualização do banco de dados:

![](assets/schema_update3.png)
