---
product: campaign
title: Delivery recorrente
description: Saiba mais sobre a atividade de workflow de delivery recorrente
feature: Workflows
role: User, Data Engineer
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: 28742db06b9ca78a4e952fcb0e066aa5ec344416
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 97%

---

# Entrega recorrente{#recurring-delivery}



Uma atividade **[!UICONTROL Recurring delivery]** permite configurar uma ocorrência de template de delivery específico para uma campanha.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#recurring-delivery-video)

Essa atividade só está disponível na guia **[!UICONTROL Targeting and workflows]** localizada em uma campanha.

Para fazer isso:

1. Selecione o template delivery no qual a atividade será baseada.

   ![](assets/recurring_delivery_001.png)

1. Configure o template de delivery.

O processo de configuração dessa atividade é semelhante ao da criação de um template de delivery em termos das opções disponíveis.

Para obter um exemplo de uso dessa atividade, consulte esta [seção](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## Como configurar um delivery recorrente

Um **delivery recorrente** criará uma nova instância de delivery toda vez que for executado. Por exemplo, se o workflow estiver programado para ser executado uma vez por semana, o resultado será 52 deliveries em um ano. Também significa que o log abrangente e os logs de rastreamento serão separados por cada instância do delivery.

![Delivery recorrente](assets/delivery_recurring.jpg)

Se desejar impedir a execução de um delivery recorrente, cancele completamente a campanha ou interrompa a execução do fluxo de trabalho. Parar o delivery no painel do Campaign só interromperá a ocorrência do delivery: as próximas instâncias do delivery recorrente continuarão sendo criadas em cada execução de fluxo de trabalho.

>[!NOTE]
>
>Não é possível enviar uma prova de uma atividade do tipo **[!UICONTROL Recurring delivery]**.
> 
>Para criar um delivery diretamente por meio de um workflow da campanha, use as atividades específicas predefinidas do canal (por exemplo **[!UICONTROL Email delivery]**).

## Vídeo tutorial (#recurring-delivery-video)

Este vídeo explica como configurar um delivery recorrente e uma atividade de scheduler.

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

Vídeos explicativos extras sobre o Campaign estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
