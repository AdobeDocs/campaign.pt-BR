---
product: campaign
title: Controle de entregas
description: Saiba mais sobre a atividade de workflow de controle de entrega
feature: Workflows
role: User
exl-id: 09fe638d-5e1c-49d1-9196-6300c1e56703
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 100%

---

# Controle de entregas{#delivery-control}



Uma ação do tipo **Controle de entrega** permite iniciar, pausar ou parar uma entrega.

Isso pode ser a entrega especificada na transição, uma entrega selecionada explicitamente ou uma entrega calculada por um script. Para obter mais informações, consulte [Delivery](delivery.md).

![](assets/edit_diffusion_act.png)

Se você selecionar **[!UICONTROL Start]**, a atividade executará todas as etapas necessárias para iniciar a entrega (cálculo de direcionamento, preparação de conteúdo, entrega). Se algumas dessas etapas já foram executadas por uma atividade anterior do workflow, elas não serão executadas novamente. Por exemplo, se a estimativa de direcionamento já foi executada por uma atividade do tipo **[!UICONTROL Delivery]** (consulte [Entrega](delivery.md)), a atividade **[!UICONTROL Act on the delivery]** iniciará as etapas restantes (preparação de conteúdo e entrega).

As seguintes opções estão disponíveis:

* **[!UICONTROL Generate an outbound transition]**

  Cria uma transição de saída que será ativada no final da execução. Você pode escolher se quer recuperar ou não o target da entrega.

* **[!UICONTROL Processing errors]**

  Consulte [Processamento de erros](monitor-workflow-execution.md#processing-errors).

## Parâmetros de entrada {#input-parameters}

* deliveryId

Identificador de entrega, se a ação selecionada for **[!UICONTROL Specified in the transition]**.
