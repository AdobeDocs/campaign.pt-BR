---
product: campaign
title: Alterar imagens de atividade
description: Saiba como alterar a imagem da atividade
feature: Workflows
role: Admin
version: Campaign v8, Campaign Classic v7
exl-id: f5580401-3305-4915-88a2-3400a32aa7aa
TQID: 'https://experienceleague.adobe.com/9i-2gtfWr0ghkIif2S-ORoXk-hTlSMHgkeRAmMW0msg'
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
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 74%
---
# Alterar imagens de atividade{#change-activity-images}



As imagens usadas nos diagramas dos vários fluxos de trabalho podem ser alteradas. No entanto, elas devem estar em conformidade com determinadas restrições. Estes são os estágios de implementação:

* Para alterar a imagem de fundo, selecione o fluxo de trabalho de segmentação desejado e clique na guia **[!UICONTROL Properties]**.

  ![Propriedades do fluxo de trabalho, guia Avançado: campo de imagem de plano de fundo com o ícone Selecionar link realçado.](assets/s_user_segmentation_properties_tab.png)

  Para selecionar a imagem a ser usada, clique no ícone **[!UICONTROL Select link]** à direita do campo **[!UICONTROL Background image]**.

  >[!NOTE]
  >
  >A largura em pixels da imagem do plano de fundo deve ser em múltiplo de 4.

  ![Janela de seleção de imagens listando imagens de fundo como backgrounds/grid.png, com Ok para confirmar.](assets/s_user_segmentation_background_select.png)

  O ícone **[!UICONTROL Edit link]** permite visualizar a imagem selecionada.

* Para alterar a imagem associada a uma atividade, clique duas vezes no objeto e, em seguida, clique na guia **[!UICONTROL Advanced]**.

  Para selecionar a imagem a ser usada, clique no ícone **[!UICONTROL Select link]** à direita do campo **[!UICONTROL Image]**.

  ![Guia Avançado de uma atividade com o campo Imagem realçado, definido como activities/dedup.png.](assets/s_user_segmentation_activity_image.png)

  O ícone **[!UICONTROL Edit link]** permite visualizar a imagem selecionada.

  ![Visualização dos nms de imagem selecionados:activities/dedup.png, exibidos com o ícone Editar link.](assets/s_user_segmentation_activity_image_select.png)

>[!NOTE]
>
>As imagens salvas no nó **[!UICONTROL Administration > Configuration > Images]** da árvore estão disponíveis para seleção.
>  
>As imagens devem estar no formato PNG, com 48x48 pixels, 16 milhões de cores e um plano de fundo transparente.
