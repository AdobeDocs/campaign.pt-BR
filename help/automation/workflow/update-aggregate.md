---
product: campaign
title: Atualizar agregado
description: Saiba mais sobre a atividade de fluxo de trabalho Atualizar agregado
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 108
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
