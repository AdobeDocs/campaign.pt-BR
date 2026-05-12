---
title: Atualizar a estrutura do banco de dados
description: Atualizar a estrutura do banco de dados
feature: Configuration
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
TQID: https://experienceleague.adobe.com/1UBvvvkN-05BqOe4aOMpYFtKEMp0Yf-q9ECtbtmHzb0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 92
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
