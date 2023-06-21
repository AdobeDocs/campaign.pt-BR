---
title: Trabalhar com o Campaign e o Adobe Experience Platform
description: Saiba como trabalhar com o Campaign e o Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: f8c4e05ba2fc97d981fb31f9b11c5de1dcc1ff6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Trabalhar com o Campaign e o Adobe Experience Platform

Os conectores de Destino e Origem do Cloud Service gerenciado da Adobe Campaign permitem uma integração perfeita entre o Adobe Campaign e o Adobe Experience Platform.

* Usar uma Adobe Campaign Managed Cloud Services **Conexão de destino** para enviar segmentos de Experience Platform para o Adobe Campaign para ativação:

  Para fazer isso, configure um novo Adobe Campaign Managed Cloud Services **Conexão de destino** para ativar um segmento/público-alvo e enviar esses dados para o Adobe Campaign. Forneça detalhes sobre a instância do Campaign a ser usada, selecione segmentos para ativar para o destino e configure os atributos que deseja exportar para o Campaign. [Saiba como criar uma conexão de destino do Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

  ![](assets/aep-destination.png){width="800" align="center"}

* Usar uma Adobe Campaign Managed Cloud Services **Conexão de origem** para enviar o delivery e os logs de rastreamento do Adobe Campaign para o Adobe Experience Platform:

  Para fazer isso, configure um novo Adobe Campaign Managed Cloud Services **Conexão de origem** para assimilar eventos do Campaign na Adobe Experience Platform. Forneça detalhes sobre a instância do Campaign e o esquema a ser usado, selecione um conjunto de dados onde os dados devem ser assimilados e configure os campos a serem recuperados. [Saiba como criar uma conexão de origem do Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}
