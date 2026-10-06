---
product: campaign
title: Restrição de tempo
description: Saiba mais sobre a atividade de fluxo de trabalho de restrição de tempo
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 0a922827-456d-425c-be04-d9efbb152c92
TQID: 'https://experienceleague.adobe.com/H5or5WZXA8Nl2OBYo6EkFGAwEguMYDCKs1CqLbzODkk'
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 62%
---
# Restrição de tempo{#time-constraint}

A atividade de **Restrição de tempo** permite adiar a execução de uma tarefa ou abandoná-la.

Insira o rótulo para a atividade e especifique o período durante o qual a tarefa do workflow pode ser executada. O workflow será executado somente durante essa janela de execução definida e permanecerá pausado fora dela.

Quando a opção **[!UICONTROL Try again later if outside of execution period]** estiver selecionada, ela permitirá reiniciar a tarefa fora do período de execução. se desejar que a ação do fluxo de trabalho seja abandonada para sempre após sua suspensão, desmarque essa opção.

![](assets/s_user_scheduled_wait.png)
