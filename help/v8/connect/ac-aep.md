---
title: Trabalhar com o Campaign e o Adobe Experience Platform
description: Saiba como trabalhar com o Campaign e o Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Trabalhar com o Campaign e o Adobe Experience Platform

O destino do Cloud Service gerenciado da Adobe Campaign e os conectores de origem permitem uma integração perfeita entre o Adobe Campaign e o Adobe Experience Platform:

* Use **Conector de Fontes de nuvem gerenciadas da Adobe Campaign** para enviar segmentos do Experience Platform para o Adobe Campaign para ativação,

   ![](assets/aep-destination.png)

* Use **Conector de destino da nuvem gerenciada do Adobe Campaign** para enviar o delivery do Adobe Campaign e os logs de rastreamento para o Adobe Experience Platform.

   ![](assets/aep-logs.png)

As etapas para configurar essa integração no Adobe Experience Platform são as seguintes:

1. Configure uma nova conexão de destino do Adobe Campaign Managed Cloud Services para ativar um segmento/público-alvo e enviar esses dados para o Adobe Campaign.

   Forneça detalhes sobre a instância do Campaign a ser usada, selecione segmentos a serem ativados para o destino e configure os atributos que deseja exportar para o Campaign.

   [Saiba como criar uma conexão de destino do Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Configure uma nova conexão de origem do Adobe Campaign Managed Cloud Services para assimilar eventos do Campaign na Adobe Experience Platform.

   Forneça detalhes sobre a instância do Campaign e o schema a ser usado, selecione um conjunto de dados em que os dados devem ser assimilados e configure os campos a serem recuperados.

   [Saiba como criar uma conexão de origem do Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)
