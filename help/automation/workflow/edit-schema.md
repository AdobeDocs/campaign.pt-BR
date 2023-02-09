---
product: campaign
title: Editar esquema
description: Saiba mais sobre a atividade de workflow editar esquema
feature: Workflows, Targeting Activity
exl-id: 16fb1aa5-cf99-4461-a1a4-7a68d97e2a74
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 100%

---

# Editar esquema{#edit-schema}



Os dados podem ser transformados, normalizados e, se necessário, enriquecidos no workflow utilizando a atividade **[!UICONTROL Edit schema]**. Geralmente é usado para normalizar a estrutura de dados: é possível renomear as colunas de saída ou modificar o conteúdo, calculando os valores médios de um campo ou agregado.

Essa atividade não altera os dados na tabela de trabalho, altera apenas seu schema, ou seja, o modo de exibição lógico dos dados.

![](assets/wf_manipulation_box.png)

Também é possível criar associações com outras tabelas de trabalho, por meio da guia **[!UICONTROL Links]**.

![](assets/wf_manipulation_box_link_tab.png)

A seção inferior permite configurar a lista de condições de associação, isto é, os critérios utilizados para reconciliar os dados a partir das duas tabelas.
