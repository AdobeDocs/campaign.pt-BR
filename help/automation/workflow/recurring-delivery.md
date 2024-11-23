---
product: campaign
title: Entrega recorrente
description: Saiba mais sobre a atividade de workflow de entrega recorrente
feature: Workflows
role: User, Data Engineer
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: e0dbeb7402a46f76a26c28dd226bc069d52f2609
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 86%

---

# Entrega recorrente{#recurring-delivery}



Uma atividade **[!UICONTROL Recurring delivery]** permite configurar uma ocorrência de template de entrega específico para uma campanha.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#recurring-delivery-video)

Essa atividade só está disponível na guia **[!UICONTROL Targeting and workflows]** localizada em uma campanha.

Para fazer isso:

1. Selecione o template de entrega no qual a atividade será baseada.

   ![](assets/recurring_delivery_001.png)

1. Configure o template de entrega.

O processo de configuração dessa atividade é semelhante ao da criação de um template de delivery em termos das opções disponíveis.

Para obter um exemplo de uso dessa atividade, consulte esta [seção](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## Como configurar uma entrega recorrente

Uma **entrega recorrente** criará uma nova instância de entrega toda vez que for executada. Por exemplo, se o workflow estiver programado para ser executado uma vez por semana, o resultado será 52 entregas em um ano. Também significa que o log abrangente e os logs de rastreamento serão separados por cada instância da entrega.

![Entrega recorrente](assets/delivery_recurring.jpg)

Se desejar impedir a execução de uma entrega recorrente, cancele completamente a campanha ou interrompa a execução do fluxo de trabalho. Parar o delivery no painel do Campaign só interrompe a ocorrência do delivery: as próximas instâncias do delivery recorrente continuarão sendo criadas em cada execução de fluxo de trabalho.

>[!NOTE]
>
>Não é possível enviar uma prova de uma atividade do tipo **[!UICONTROL Recurring delivery]**.
> 
>Para criar uma entrega diretamente por meio de um workflow da campanha, use as atividades específicas predefinidas do canal (por exemplo **[!UICONTROL Email delivery]**).

## Vídeo tutorial (#recurring-delivery-video)

Este vídeo explica como configurar uma entrega recorrente e uma atividade de scheduler.

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

Vídeos extras explicativos do Campaign estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
