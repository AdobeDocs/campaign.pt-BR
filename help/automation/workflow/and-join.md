---
product: campaign
title: AND-join
description: AND-join
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
TQID: 'https://experienceleague.adobe.com/1ChXl3Rlm93ftFFaD7Z-PcoO7CwUcxRHm2JdCFzIOZs'
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
source-wordcount: '193'
ht-degree: 96%
---
# AND-join{#and-join}



Um join aciona sua transição de saída somente quando todas as transições de entrada são ativadas, ou seja, quando todas as atividades anteriores são concluídas. Isso permite verificar se determinadas atividades foram concluídas antes de continuar a executar o fluxo de trabalho.

Por exemplo, você pode usar uma atividade AND-join no contexto de criação de conteúdo e automação de envio de entrega, para garantir que uma entrega seja iniciada somente depois que as etapas de consulta de públicos-alvos e atualizações de conteúdo forem concluídas. Um caso de uso específico está disponível no

![](assets/and-join-usage.png)

>[!NOTE]
>
>Observe que transições de entrada configuradas com dimensões de direcionamento diferentes não podem ser agrupadas usando uma atividade **[!UICONTROL AND-join]**.

A população enviada da saída da atividade é determinada escolhendo um conjunto principal entre as transições de entrada na atividade.

A transição de saída só pode conter uma das populações de transição de entrada. Se a atividade não estiver configurada, a transição de saída selecionará aleatoriamente uma das populações de entrada.

>[!CAUTION]
>
>No caso de atividades do tipo **AND-join**, as variáveis do evento são mescladas, mas se uma mesma variável for definida duas vezes, há um conflito e o valor permanece indeterminado. Para obter mais informações, consulte [esta seção](javascript-scripts-and-templates.md#event-variables).
