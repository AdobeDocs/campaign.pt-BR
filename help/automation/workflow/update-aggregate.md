---
product: campaign
title: Atualizar agregado
description: Saiba mais sobre a atividade de fluxo de trabalho Atualizar agregado
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
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
