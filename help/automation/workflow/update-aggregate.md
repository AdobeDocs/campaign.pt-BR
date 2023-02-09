---
product: campaign
title: Atualizar agregado
description: Saiba mais sobre a atividade de fluxo de trabalho Atualizar agregado
feature: Workflows
role: Data Engineer
level: Beginner
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 11%

---

# Atualizar agregado{#update-aggregate}

Agregados definidos em [cubos](../../v8/reporting/gs-cubes.md) para fins de relatório podem ser atualizadas com uma atividade específica. A **[!UICONTROL Workflow]** estiver disponível ao configurar a agregação.

Saiba mais sobre cubos e agregados em [esta seção](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Para atualizar uma agregação, edite a variável **[!UICONTROL Update aggregate]** e selecione o cubo e a agregação para atualizar.

Você pode configurar um **Atualização completa** ou **Atualização parcial**.

![](assets/update-aggregate-details.png)

Por padrão, uma atualização completa é executada durante cada cálculo. Para habilitar uma atualização parcial, selecione a opção e defina as condições de atualização.

![](assets/update-aggregate-partial.png)

Uma boa prática é adicionar uma **[!UICONTROL Scheduler]** para configurar a frequência das atualizações de cálculo.
