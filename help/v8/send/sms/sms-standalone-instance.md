---
title: SMS em uma instância independente
description: Saiba como configurar um delivery de SMS em uma instância independente
feature: SMS
role: User
hide: true
level: Beginner, Intermediate
exl-id: 7cebcde0-c5a8-4b9b-baba-27a62bebde91
TQID: https://experienceleague.adobe.com/dCe9loow9GAK5YIKzwwcZVS94JtDiEhg0p5QUCBd-So
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 8%

---

# SMS em uma instância independente {#sms-standalone}

>[!IMPORTANT]
>
>Esta documentação é para o Adobe Campaign v8.7.2 e posteriores.
>
>Para versões mais antigas, leia a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/pt-br/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

Em uma instância independente, o envio de um delivery de SMS requer:

1. Uma **conta externa** especificando um conector e o tipo de mensagem, [saiba mais aqui](#external-account)

1. Um **modelo de entrega** no qual esta conta externa é referenciada, [saiba mais aqui](#sms-delivery-template)

## Criar uma conta externa {#external-account}

>[!IMPORTANT]
>
>Usar a mesma conta e senha para várias contas externas de SMS pode resultar em conflitos e sobreposição entre as contas. Saiba mais na [página de solução de problemas de SMS](smpp-connection.md#sms-troubleshooting).

Estas são as etapas para criar sua conta externa SMPP:

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**, clique no ícone **[!UICONTROL New]**

   ![](assets/sms_extaccount.png){zoomable="yes"}

1. Configure o **[!UICONTROL Label]** e o **[!UICONTROL Internal name]** da sua conta externa. Defina o tipo de conta como **[!UICONTROL Routing]**, marque a caixa **[!UICONTROL Enabled]**, selecione **[!UICONTROL Mobile (SMS)]** para o canal e **[!UICONTROL Bulk delivery]** para o modo de entrega.

   ![](assets/sms_extaccount_new.png){zoomable="yes"}

1. Na guia **[!UICONTROL Mobile]**, mantenha **[!UICONTROL Extended generic SMPP]** na lista suspensa **[!UICONTROL Connector]**.
A caixa **[!UICONTROL Send messages through a dedicated process]** está marcada por padrão.

   ![](assets/sms_extaccount_connector.png){zoomable="yes"}

   Para configurar a conexão, você precisa preencher as guias deste formulário. Para obter detalhes, [saiba mais sobre a conta externa SMPP](smpp-external-account.md#smpp-connection-settings).


## Configurar o template do delivery {#sms-delivery-template}

Para facilitar a criação do delivery de SMS, crie um template do delivery de SMS no qual sua conta externa SMPP é referenciada.

Em **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, clique com o botão direito do mouse no modelo de entrega do Mobile existente e escolha **[!UICONTROL Duplicate]**.

![](assets/sms_template_duplicate.png){zoomable="yes"}

Altere o **[!UICONTROL Label]** e o **[!UICONTROL Internal name]** do seu modelo para reconhecê-lo facilmente, e clique no botão **[!UICONTROL Properties]**.

![](assets/sms_template_name.png){zoomable="yes"}

Na guia **[!UICONTROL General]**, em **[!UICONTROL Routing]**, selecione a conta externa SMPP.

![](assets/sms_template_routing.png){zoomable="yes"}

Na guia **[!UICONTROL SMS]**, é possível adicionar parâmetros opcionais ao modelo.

![](assets/sms_template_properties.png){zoomable="yes"}

[Saiba mais sobre esta configuração da guia SMS](sms-delivery-settings.md).
