---
product: campaign
title: Atualizar agregado
description: Saiba mais sobre a atividade de fluxo de trabalho Atualizar agregado
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: 'https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 11%
---
# Atualizar agregado{#update-aggregate}

As agregações definidas em [cubos](../../v8/reporting/gs-cubes.md) para fins de relatório podem ser atualizadas com uma atividade específica. Uma guia **[!UICONTROL Workflow]** está disponível ao configurar a agregação.

Saiba mais sobre cubos e agregações em [esta seção](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Para atualizar uma agregação, edite a atividade **[!UICONTROL Update aggregate]** e selecione o cubo e a agregação a serem atualizados.

Você pode configurar uma **atualização completa** ou uma **atualização parcial**.

![](assets/update-aggregate-details.png)

Por padrão, uma atualização completa é executada durante cada cálculo. Para habilitar uma atualização parcial, selecione a opção e defina as condições de atualização.

![](assets/update-aggregate-partial.png)

Uma prática recomendada é adicionar uma atividade **[!UICONTROL Scheduler]** para configurar a frequência das atualizações de cálculo.
