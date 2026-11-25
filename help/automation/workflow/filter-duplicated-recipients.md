---
product: campaign
title: Filtrar destinatários duplicados
description: Saiba como filtrar destinatários duplicados
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
TQID: 'https://experienceleague.adobe.com/jwnm0saAGOFD4FjCniKHBm6xDd8H2QggSy3UvrMAb-E'
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
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 71%
---
# Filtrar destinatários duplicados {#filtering-duplicated-recipients}



Neste exemplo, queremos filtrar os destinatários que aparecem duas vezes ou mais em uma entrega para recuperar perfis duplicados.

Para criar este exemplo, aplique as seguintes etapas:

1. Arraste e solte uma atividade **[!UICONTROL Query]** em um fluxo de trabalho e abra a atividade.
1. Clique em **[!UICONTROL Edit query]** e defina as dimensões do filtro e do direcionamento para **[!UICONTROL Recipients]**.

   ![Etapa de dimensão de filtragem e direcionamento da atividade Query com Destinatários selecionados. Condições de filtragem destacadas.](assets/query_recipients_1.png)

1. Defina a seguinte condição de filtro para o destinatário do target que existe no log de entrega. Escolha **Recipient delivery log (broadlog)** na coluna **Expression**, escolha **exist such as** na coluna **Operator**.

   ![Etapa de filtro com a condição Logs de entrega do destinatário (broadLog) e o operador existe, como.](assets/query_recipients_2.png)

1. Defina a condição de filtro a seguir para direcionar sua entrega. Escolha **[!UICONTROL Internal name]** na coluna Expression e **[!UICONTROL equal to]** na coluna Operator.
1. Na coluna Valor, adicione o nome interno da entrega desejada.

   ![Condição de filtro no nome interno da entrega, igual ao valor summer_delivery_sales, em existe, como.](assets/query_recipients_3.png)

1. Com um operador **[!UICONTROL AND]**, repita as mesmas operações para selecionar outras entregas.

   ![Existem duas condições unidas por And, direcionadas para summer_delivery_sales e summer_delivery_new_collection.](assets/query_recipients_4.png)

A transição de saída contém os destinatários duplicados alcançados nas entregas.
