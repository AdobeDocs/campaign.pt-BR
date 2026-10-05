---
product: campaign
title: Entrega recorrente
description: Saiba mais sobre a atividade de fluxo de trabalho de entrega recorrente
feature: Workflows
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
TQID: 'https://experienceleague.adobe.com/EuZFMSHKtsfYexPt3-HS0RJHnmxCQX-Pf8qUy-DlBu0'
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
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 85%
---
# Entrega recorrente{#recurring-delivery}



Uma atividade **[!UICONTROL Recurring delivery]** permite configurar uma ocorrência de modelo de entrega específico para uma campanha.

![](assets/do-not-localize/how-to-video.png) [Conheça este recurso no vídeo](#recurring-delivery-video)

Essa atividade só está disponível na guia **[!UICONTROL Targeting and workflows]** localizada em uma campanha.

Para fazer isso:

1. Selecione o modelo de entrega no qual a atividade será baseada.

   ![](assets/recurring_delivery_001.png)

1. Configure o modelo de entrega.

O processo de configuração dessa atividade é semelhante ao da criação de um modelo de entrega em termos das opções disponíveis.

Para obter um exemplo de uso dessa atividade, consulte esta [seção](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## Como configurar uma entrega recorrente

Uma **entrega recorrente** criará uma nova instância de entrega toda vez que for executada. Por exemplo, se o fluxo de trabalho estiver programado para ser executado uma vez por semana, o resultado será 52 entregas em um ano. Também significa que o log abrangente e os logs de rastreamento serão separados por cada instância da entrega.

![Entrega recorrente](assets/delivery_recurring.jpg)

Se desejar impedir a execução de uma entrega recorrente, cancele completamente a campanha ou interrompa a execução do fluxo de trabalho. Parar o delivery no painel do Campaign só interrompe a ocorrência do delivery: as próximas instâncias do delivery recorrente continuarão sendo criadas em cada execução de fluxo de trabalho.

>[!NOTE]
>
>Não é possível enviar uma prova de uma atividade do tipo **[!UICONTROL Recurring delivery]**.
> 
>Para criar uma entrega diretamente por meio de um fluxo de trabalho da campanha, use as atividades específicas predefinidas do canal (por exemplo **[!UICONTROL Email delivery]**).

## Vídeo tutorial (#recurring-delivery-video)

Este vídeo explica como configurar uma entrega recorrente e uma atividade de scheduler.

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

Vídeos explicativos extras sobre o Campaign estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
