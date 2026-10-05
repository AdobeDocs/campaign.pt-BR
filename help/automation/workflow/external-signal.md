---
product: campaign
title: Sinal externo
description: Saiba mais sobre a atividade de fluxo de trabalho de sinal externo
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 45cb95ec-77bf-4bab-895f-b94f6ce660fd
TQID: 'https://experienceleague.adobe.com/w1Sip-iisntO8WLiUhYCqr-9DeiGY1F2eiU2CUSDF7c'
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
source-wordcount: '168'
ht-degree: 100%
---
# Sinal externo{#external-signal}



A atividade **External signal** permite acionar a execução de um conjunto de tarefas em um fluxo de trabalho para uma agenda.

Quando uma tarefa &quot;External signal&quot; é ativada, ela é pausada indefinidamente ou até o final do período de tempo especificado. Sua transição é ativada pela chamada SOAP **PostEvent(sessionToken, workflowId, activity, transition, parameters, complete).** O parâmetro **[!UICONTROL complete]** permite que a tarefa seja concluída, de modo que ela não responda a chamadas subsequentes.

Consulte a documentação online sobre chamadas SOAP para obter mais informações sobre a função PostEvent.

É possível configurar essa atividade para definir eventos se nenhum sinal for recebido. Para fazer isso, crie a atividade e clique na guia **[!UICONTROL Expiration]**. Clique no botão **[!UICONTROL Insert]** para criar e configurar um evento.

![](assets/edit_signal.png)

A configuração das expirações é apresentada em [Expirações](define-approvals.md).

O campo **Delay** permite especificar um atraso de expiração nas unidades de sua escolha. Consulte [Wait](wait.md).

Cada linha representa um tipo de expiração e coincides com uma transição.

![](assets/external_sign_diag.png)
