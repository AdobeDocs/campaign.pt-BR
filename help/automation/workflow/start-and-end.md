---
product: campaign
title: Início e término
description: Saiba mais sobre atividades de fluxo de trabalho de início e término
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 1de622bc-967b-403b-86e0-2ad32cb432e3
TQID: https://experienceleague.adobe.com/Y6nuELN3qjtuXhruC9MgmyqxzptNTJgfZ0XLGleQ3A4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 135
ht-degree: 100%

---

# Início e término{#start-and-end}



As atividades **[!UICONTROL Start]** e **[!UICONTROL End]** permitem marcar graficamente o início e o fim de um fluxo de trabalho. Essas atividades não têm impacto funcional e, portanto, são opcionais.

* **[!UICONTROL Start]**

  A execução de um fluxo de trabalho começa com atividades sem uma transição de entrada e atividades tipo início.

  ![](assets/s_user_segmentation_start_stop.png)

* **[!UICONTROL End]**

  É possível configurar a atividade **[!UICONTROL End]** para interromper todas as tarefas em andamento. Para fazer isso, clique duas vezes na atividade para exibir suas propriedades e marque a opção apropriada.

  ![](assets/s_user_segmentation_end.png)

  Os dados na tabela de trabalho são excluídos automaticamente quando a atividade final é habilitada. Se isso não for necessário e para evitar cargas desnecessárias, é possível desabilitar a transição na última saída de atividade. Por exemplo, em uma saída de remessa, se nenhum processo estiver agendado, desmarque a opção relevante conforme mostrado abaixo:

  ![](assets/s_advuser_delivery_option_no_output.png)
