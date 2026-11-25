---
product: campaign
title: SMS de entrada
description: Saiba mais sobre a atividade de fluxo de trabalho de SMS de entrada
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 2c12c45b-4429-4e60-bc96-ff70a95d4c9e
TQID: 'https://experienceleague.adobe.com/ZZcWkqyokq5qWLAHGLW7TNJimNc5a9MUEQkSr0fgKgc'
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
  - id: bce277d1-7efa-48d8-9a1b-b588bb45ba1c
    internal-label: Channels Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 73%
---
# SMS de entrada{#inbound-sms}



A atividade de **SMS de Entrada** permite baixar e processar mensagens de texto de uma conta externa.

## Propriedades {#properties}

![Atividade de SMS de entrada com o campo Conta externa, as mensagens de Filtros para processar links e uma área de Script.](assets/sms_rec_edit.png)

A primeira guia da atividade de **SMS de Entrada** permite inserir os parâmetros de roteamento para mensagens SMS e inserir o script a ser executado no recebimento de cada mensagem. A segunda guia permite atribuir um cronograma à atividade e a terceira guia define as condições de expiração da atividade.

1. **[!UICONTROL SMS routing]**: selecione a conta externa que será usada para recuperação do SMS. As contas externas são configuradas no nó **[!UICONTROL Administration > Platform > External accounts]** da árvore. [Saiba mais](../../v8/config/external-accounts.md)
1. **[!UICONTROL Script]**
1. **[!UICONTROL Schedule]**

   ![Guia Agendamento de SMS de Entrada com Execução de plano marcada e Interromper agendamento assim que um SMS for recebido marcado.](assets/sms_rec_edit_2.png)

1. **[!UICONTROL Expiration]**

As guias **[!UICONTROL Script]**, **[!UICONTROL Schedule]** e **[!UICONTROL Expiry]** são detalhadas em [Emails de entrada](inbound-emails.md).
