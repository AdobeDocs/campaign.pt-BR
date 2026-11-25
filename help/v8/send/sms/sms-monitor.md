---
title: Monitorar e rastrear um SMS
description: Sobre o monitoramento e o rastreamento de um delivery de SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 42be45db-3a90-4ad0-896d-f082afff1f8e
TQID: 'https://experienceleague.adobe.com/wETwv6lIEctnfT54WQjulzGxeCPo6lZDF-rxlwBtF4I'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# Monitorar e rastrear um SMS

É importante monitorar o delivery de SMS para garantir que suas campanhas de marketing sejam eficientes.

Estas são as possibilidades que você tem para saber o que acontece após o envio do seu delivery

## Entender o painel de entrega do SMS

O painel do delivery fornece muitas informações sobre o SMS.

Para acessar o painel, clique duas vezes no delivery na lista de delivery.

Na guia **[!UICONTROL Summary]**, você tem os dados principais, como o número de mensagens processadas e o número de sucessos.

![Guia Resumo do painel de entrega de SMS com mensagens a enviar, taxas de sucesso e processadas e status de entrega](assets/sms_summary.png){zoomable="yes"}

Após o envio do SMS, a guia **[!UICONTROL SMS]**, que é sobre o conteúdo da entrega, não estará mais acessível para alteração.

Na guia **[!UICONTROL Delivery]**, você tem as informações sobre os logs de entrega. Para cada endereço contatado, você pode ver se o SMS foi enviado ou não

![Lista de logs da guia Entrega mostrando, para cada endereço contatado, se o SMS foi enviado, com status e motivo](assets/sms_deliverylogs.png){zoomable="yes"}

Você pode ver na guia **[!UICONTROL Exclusions]** os detalhes sobre por que alguns endereços são excluídos do público-alvo.

![Guia de entrega - Lista de guias de exclusões de endereços ignorados com o motivo; por exemplo, endereço ou Duplo](assets/sms_exclusions.png){zoomable="yes"}

A guia **[!UICONTROL Tracking]** é sobre o rastreamento. Abaixo o exemplo de um URL rastreado no conteúdo do SMS.

![Lista de URLs da guia de rastreamento mostrando uma URL rastreada do conteúdo de SMS com seu rótulo, tipo e URL de origem](assets/sms_trackinglogs.png){zoomable="yes"}

E por último, a guia **[!UICONTROL Audit]** com todos os detalhes durante a inicialização da entrega:

![Guia Auditoria Log listando as mensagens registradas durante a inicialização da entrega, com colunas de data e mensagem](assets/sms_audit.png){zoomable="yes"}

## Entender as falhas de SMS

Os tipos de falha e os motivos para falha no SMS são os mesmos dos emails.

Saiba mais sobre [falhas de entrega](../delivery-failures.md) e, especificamente, sobre [quarentenas de SMS](../delivery-failures.md#sms-quarantines).
