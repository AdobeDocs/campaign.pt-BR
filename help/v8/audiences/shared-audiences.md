---
title: Compartilhar públicos-alvo com soluções da Adobe Experience Cloud
description: Saiba como compartilhar públicos-alvo com soluções da Adobe Experience Cloud
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 75%
---
# Compartilhar públicos-alvo com soluções da Adobe Experience Cloud{#shared-audiences}

Opção 1: origens e destinos da AEP

Opção 2: Adobe People/AAM

É possível integrar o **Adobe Campaign** ao **Serviço principal de pessoas** ou ao Adobe Audience Manager. Depois será possível:

* Importar públicos-alvos/segmentos compartilhados de diferentes soluções da Adobe Experience Cloud para o Adobe Campaign. Os públicos-alvos podem ser importados por meio de listas no Adobe Campaign.

* Exportar listas no formato de públicos-alvo compartilhados da Adobe Experience Cloud. Esses públicos-alvos podem ser usados nas diferentes soluções da Adobe Experience Cloud que você usa. Os públicos-alvo podem ser exportados após o direcionamento num fluxo de trabalho, usando uma atividade **[!UICONTROL Update shared audience]** dedicada.

A integração oferece suporte a dois tipos de Adobe Experience Cloud IDs:

* **ID de visitante**: esse identificador reconcilia os visitantes da Adobe Experience Cloud com os destinatários do Adobe Campaign.
* **ID declarada**: esse identificador reconcilia todos os tipos de dados com elementos do banco de dados do Adobe Campaign. É a chave de reconciliação predefinida no Adobe Campaign.

  >[!NOTE]
  >
  > A fonte de dados da ID declarada agora também pode ser usada com a integração do serviço principal Pessoas.
  >
  >Se você estiver usando a integração do serviço principal Pessoas e quiser adicionar a integração do Audience Manager, será necessária a ajuda de um consultor da Adobe Audience Manager para evitar a perda de todas as sincronizações de ID coletadas durante a transição para o uso dessa fonte de dados de ID declarada em um contexto do Adobe Audience Manager.

Consulte:

[Base de Conhecimentos Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=pt-BR){target="_blank"}.

[Guia de componentes da interface central da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=pt-BR){target="_blank"}.
