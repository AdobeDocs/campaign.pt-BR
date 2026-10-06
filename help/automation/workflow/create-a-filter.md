---
product: campaign
title: Criar um filtro
description: Saiba como criar um filtro ao executar consultas
feature: Query Editor, Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8e6fd9b4-77c4-4af8-921b-c3fe104fa5bc
TQID: 'https://experienceleague.adobe.com/3EkEMTJs1-sdM9wSTYorHWO-emO3Nz5nugrWDU4h5pM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
    internal-label: Query Editor
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 77%
---
# Criar um filtro {#creating-a-filter}

Os filtros disponíveis no Adobe Campaign são definidos por meio das condições de filtragem criadas usando o mesmo modo operacional usado ao criar consultas no [Editor de consultas](../../v8/start/query-editor.md).

O nó **[!UICONTROL Administration > Configuration > Predefined filters]** contém todos os filtros padrão. Alguns deles são usados em listas e visões gerais. Saiba mais sobre [filtros predefinidos internos](../../v8/audiences/create-filters.md).

Por exemplo, a lista de operadores pode ser filtrada por **[!UICONTROL Active accounts]**:

![](assets/query_editor_filter_sample_1.png)

O filtro correspondente contém a consulta no valor **[!UICONTROL Account disabled]** do esquema **[!UICONTROL Operators]**:

![](assets/query_editor_filter_sample_2.png)

Para a mesma lista, o filtro **[!UICONTROL By login or label]** permite filtrar os dados na lista com base no valor inserido no campo de filtro:

![](assets/query_editor_filter_sample_3.png)

Ele é construído da seguinte maneira:

![](assets/query_editor_filter_sample_4.png)

Para corresponder às condições do filtro, a conta do operador deve verificar uma das seguintes condições:

* Seu rótulo contém os caracteres inseridos no campo de entrada,
* O nome do operador contém os caracteres inseridos no campo de entrada,
* O conteúdo da área de descrição contém os caracteres inseridos no campo de entrada.

>[!NOTE]
>
>A função **[!UICONTROL Upper]** permite desativar a função com diferenciação de maiúsculas e minúsculas.

A coluna **[!UICONTROL Taken into account if]** permite definir os critérios do aplicativo para essas condições de filtro. Aqui, os caracteres **$(/tmp/@text)** representam o conteúdo do campo de entrada vinculado ao filtro:

![](assets/query_editor_filter_sample_5.png)

Aqui, **$(/tmp/@text)=&#39;agency&#39;**

A expressão **$(/tmp/@text)!=&#39;&#39;** aplica cada condição quando o campo de entrada não está vazio.
