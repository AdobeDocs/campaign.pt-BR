---
product: campaign
title: Alerta
description: Alerta
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8fb36117-b126-470a-9c94-eb5c0a4aca1a
TQID: 'https://experienceleague.adobe.com/rTcTh1kbiAHwo1t1wo2SBUEBTR768IkDIP2J4BbFfp8'
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 83%
---
# Alerta{#alert}



Uma atividade **Alert** envia uma mensagem a um grupo de operadores. Ela opera da mesma forma que uma atividade de aprovação, mas nenhuma resposta é esperada nesse caso.

![](assets/edit_alerte.png)

Um alerta não é persistente e, portanto, não é visível no Console do cliente. Os operadores do grupo atribuído devem ter um endereço de e-mail completo para receber a notificação. A configuração dessa atividade é semelhante àquela de um **Approval**. O modelo de entrega padrão usado para alertar os operadores é o &quot;alertAssignee&quot;.
