---
title: Compartilhar e sincronizar públicos-alvo e atributos de perfil com a Adobe Experience Platform
description: Saiba como sincronizar públicos-alvo e atributos de perfil do Adobe Experience Platform com o Campaign
feature: Experience Platform Integration
role: Developer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
TQID: 'https://experienceleague.adobe.com/sQgS-ig3-OfCLseGyqsbismNI-qqy1E2io6P17HZsUU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: eb007b6d-6e57-46ab-9485-3f24d6102304
    internal-label: Experience Platform integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%
---
# Compartilhar e sincronizar públicos-alvo com a Adobe Experience Platform {#gs-ac-aep}

Os conectores Adobe Campaign Managed Cloud Service Destination e Source permitem uma integração perfeita entre o Adobe Campaign e o Adobe Experience Platform. Com essa integração, você pode:

* Envie públicos-alvo da Adobe Experience Platform para a Adobe Campaign e envie de volta os logs de entrega e rastreamento para a Adobe Experience Platform para fins de análise,
* Traga atributos de perfil do Adobe Experience Platform para o Adobe Campaign e tenha um processo de sincronização em vigor para que eles possam ser atualizados regularmente.

## Enviar públicos da Adobe Experience Platform para o Campaign {#audiences}

As principais etapas para enviar públicos-alvo da Adobe Experience Platform para o Adobe Campaign e enviar de volta logs de delivery e rastreamento são as seguintes:

* Use uma **Conexão de destino** do Adobe Campaign Managed Cloud Services para enviar segmentos do Experience Platform para o Adobe Campaign:

  1. Acesse o catálogo de Destinos do Adobe Experience Platform e crie uma nova conexão **[!UICONTROL Adobe Campaign Managed Cloud Services]**.
  1. Forneça detalhes sobre a instância do Campaign a ser usada e escolha **[!UICONTROL Audience sync]** como o tipo de sincronização.

     ![](assets/aep-audience-sync.png){width="800" align="center"}

  1. Selecione os segmentos a serem enviados para o Adobe Campaign.
  1. Configure os atributos que deseja exportar para o público-alvo.
  1. Após a configuração do fluxo, os públicos-alvo selecionados estarão disponíveis para ativação no Adobe Campaign.

     ![](assets/aep-destination.png){width="800" align="center"}

  Informações detalhadas sobre como configurar o destino estão disponíveis na [documentação de conexão do Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en){target="_blank"}

* Use uma **conexão Source** do Adobe Campaign Managed Cloud Services para enviar a entrega do Adobe Campaign e os logs de rastreamento para o Adobe Experience Platform:

  Para fazer isso, configure uma nova **conexão com o Source** para assimilar eventos do Campaign na Adobe Experience Platform. Forneça detalhes sobre a instância do Campaign e o esquema a ser usado, selecione um conjunto de dados onde os dados devem ser assimilados e configure os campos a serem recuperados. [Saiba como criar uma conexão de origem do Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}

## Sincronizar atributos de perfil entre o Adobe Experience Platform e o Adobe Campaign {#profile}

Ao conectar o Adobe Campaign com o Adobe Experience Platform, você pode trazer atributos de perfil adicionais, que estão vinculados a um perfil no Adobe Experience Platform e têm um processo de sincronização em vigor para que sejam atualizados no banco de dados do Adobe Campaign.

Por exemplo, digamos que você esteja capturando valores de aceitação e recusa no Adobe Experience Platform. Com essa conexão, você pode trazer esses valores para o Adobe Campaign e ter um processo de sincronização em vigor para que eles sejam atualizados regularmente.

>[!NOTE]
>
>A sincronização de atributos de perfil está disponível para perfis que já estão presentes no banco de dados do Adobe Campaign.

As principais etapas para sincronizar atributos de perfil do Adobe Experience Platform com o Adobe Campaign são as seguintes:

1. Acesse o catálogo de Destinos do Adobe Experience Platform e crie uma nova conexão **[!UICONTROL Adobe Campaign Managed Cloud Services]**.
1. Forneça detalhes sobre a instância do Campaign a ser usada e escolha **[!UICONTROL Profile sync (Update only)]** como o tipo de sincronização.

   ![](assets/aep-profile-sync.png){width="800" align="center"}

1. Selecione os segmentos direcionados aos perfis que serão atualizados no banco de dados do Adobe Campaign.
1. Configure os atributos de perfil que deseja atualizar para o Adobe Campaign.
1. Depois que o fluxo for configurado, os atributos de perfil selecionados serão sincronizados com o Adobe Campaign e atualizados para todos os perfis direcionados pelos segmentos configurados no destino.

Informações detalhadas sobre como configurar o destino estão disponíveis na [documentação de conexão do Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en){target="_blank"}