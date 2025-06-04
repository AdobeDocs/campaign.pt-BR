---
product: campaign
title: SMS de entrada
description: Saiba mais sobre a atividade de workflow de SMS de entrada
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 2c12c45b-4429-4e60-bc96-ff70a95d4c9e
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 90%

---

# SMS de entrada{#inbound-sms}



A atividade de **SMS de Entrada** permite baixar e processar mensagens de texto de uma conta externa.

## Propriedades {#properties}

![](assets/sms_rec_edit.png)

A primeira guia da atividade de **SMS de Entrada** permite inserir os parâmetros de roteamento para mensagens SMS e inserir o script a ser executado no recebimento de cada mensagem. A segunda guia permite atribuir um cronograma à atividade e a terceira guia define as condições de expiração da atividade.

1. **[!UICONTROL SMS routing]**: selecione a conta externa que será usada para recuperação do SMS. Contas externas são configuradas por meio do nó **[!UICONTROL Administration > Platform > External accounts]** da árvore. [Saiba mais](../../v8/config/external-accounts.md)
1. **[!UICONTROL Script]**
1. **[!UICONTROL Schedule]**

   ![](assets/sms_rec_edit_2.png)

1. **[!UICONTROL Expiration]**

As guias **[!UICONTROL Script]**, **[!UICONTROL Schedule]** e **[!UICONTROL Expiry]** são detalhadas em [Emails de entrada](inbound-emails.md).
