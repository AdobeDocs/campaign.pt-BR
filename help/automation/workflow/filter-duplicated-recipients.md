---
product: campaign
title: Filtrar recipients duplicados
description: Saiba como filtrar recipients duplicados
feature: Workflows
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 100%

---

# Filtrar recipients duplicados {#filtering-duplicated-recipients}



Neste exemplo, queremos filtrar os recipients que aparecem duas vezes ou mais em uma delivery para recuperar perfis duplicados.

Para criar este exemplo, aplique as seguintes etapas:

1. Arraste e solte uma atividade **[!UICONTROL Query]** em um workflow e abra a atividade.
1. Clique em **[!UICONTROL Edit query]** e defina as dimensões do filtro e do direcionamento para **[!UICONTROL Recipients]**.

   ![](assets/query_recipients_1.png)

1. Defina a seguinte condição de filtro para o recipient do target que existe no log de delivery. Escolha **Recipient delivery log (broadlog)** na coluna **Expression**, escolha **exist such as** na coluna **Operator**.

   ![](assets/query_recipients_2.png)

1. Defina a condição de filtro a seguir para direcionar sua delivery. Escolha **[!UICONTROL Internal name]** na coluna Expression e **[!UICONTROL equal to]** na coluna Operator.
1. Na coluna Valor, adicione o nome interno da delivery desejada.

   ![](assets/query_recipients_3.png)

1. Com um operador **[!UICONTROL AND]**, repita as mesmas operações para selecionar outros deliveries.

   ![](assets/query_recipients_4.png)

A transição de saída contém os recipients duplicados alcançados nas deliveries.
