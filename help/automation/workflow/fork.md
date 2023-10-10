---
product: campaign
title: Bifurcação
description: Saiba mais sobre a atividade de workflow de bifurcação
feature: Workflows
role: User
exl-id: 7b94776c-2478-4e12-82a6-c94be12e7e22
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 100%

---

# Bifurcação{#fork}



Você pode usar a atividade **[!UICONTROL Fork]** para criar várias transições de saída e executar várias atividades independentemente no mesmo fluxo de trabalho.

>[!IMPORTANT]
>
>As transições de saída adicionadas após uma atividade **[!UICONTROL Fork]** não são executadas simultaneamente. Esse comportamento pode afetar o desempenho do fluxo de trabalho. Use a atividade **[!UICONTROL Fork]** se precisar executar várias atividades independentemente. Como opção, você pode unir as atividades de saída antes da parte subsequente do fluxo de trabalho.

Para configurar uma atividade **[!UICONTROL Fork]** e suas atividades relacionadas, siga estas etapas:

1. Abra a atividade **[!UICONTROL Fork]** e defina o nome e o rótulo das transições de saída.

   ![](assets/s_user_segmentation_fork.png)

1. Abra cada transição de saída e configure-a.
1. Como opção, para unir transições de saída, adicione uma atividade AND-join. [Saiba mais](and-join.md).

   A parte subsequente do fluxo de trabalho é executada somente após a conclusão das transições de saída unidas.

## Exemplo: segmentação

Neste exemplo, diferentes emails são enviados para diferentes grupos de população. Uma atividade **[!UICONTROL Fork]** é usada após um query, para executar duas ações simultaneamente:

* Salve o resultado da query
* Segmente o resultado para enviar vários deliveries

  ![A atividade Fork segue a interseção de dois queries e precede uma atividade de atualização de lista e uma atividade de Split.](assets/wkf_fork_example.png)

O fluxo de trabalho inclui estas atividades:

1. Atividade de **[!UICONTROL Query]**

   Dois grupos de população são selecionados: mulheres e parisienses.

1. Atividade de **[!UICONTROL Intersection]**

   A interseção dos resultados da query, ou seja, mulheres parisienses, é selecionada.

1. Atividade de **[!UICONTROL Fork]**

   A população calculada é salva e, em paralelo, segmentada em dois grupos:

   1. Mulheres parisienses com idade entre 18 e 40 anos
   1. Mulheres parisienses acima de 40 anos

1. Atividade de **[!UICONTROL Delivery]**

   Um email diferente é enviado para cada grupo de população.

## Caso de uso: enviar um email de aniversário

Um email recorrente é enviado para uma lista de recipients em seus aniversários. Uma atividade **[!UICONTROL Fork]** é usada para incluir recipients que nasceram em 29 de fevereiro em um ano bissexto. [Saiba mais](send-a-birthday-email.md) sobre esse caso de uso.

![A atividade fork segue uma atividade de teste e precede duas atividades de query.](assets/birthday-workflow_usecase_1.png)

## Caso de uso: automatizar o conteúdo com um fluxo de trabalho


Em seguida, você pode configurar cada transição de saída e associá-la usando uma atividade [AND-join](and-join.md), se necessário. Dessa forma, o restante do fluxo de trabalho será executado somente depois que as transições de saída da atividade **[!UICONTROL Fork]** forem concluídas.

## Tópicos relacionados

* [Atividade AND-join](and-join.md)
* [Caso de uso: email de aniversário](send-a-birthday-email.md)
