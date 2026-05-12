---
title: Compartilhar públicos-alvo com soluções da Adobe Experience Cloud
description: Saiba como compartilhar públicos-alvo com soluções da Adobe Experience Cloud
feature: Audiences
role: User
level: Beginner
hide: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
TQID: https://experienceleague.adobe.com/Q7eY7lPXlHWEcaj-Hx4Bbqj-hwzMvrlxGGYeN5AxzRE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 76%

---

# Compartilhar públicos-alvo com soluções da Adobe Experience Cloud{#shared-audiences}


Opção 1: origens e destinos da AEP

Opção 2: Adobe People/AAM

É possível integrar o **Adobe Campaign** ao **Serviço principal de pessoas** ou ao Adobe Audience Manager. Depois será possível:

* Importar públicos-alvos/segmentos compartilhados de diferentes soluções da Adobe Experience Cloud para o Adobe Campaign. Os públicos-alvos podem ser importados por meio de listas no Adobe Campaign.

* Exportar listas no formato de públicos-alvo compartilhados da Adobe Experience Cloud. Esses públicos-alvos podem ser usados nas diferentes soluções da Adobe Experience Cloud que você usa. Os públicos-alvo podem ser exportados após o direcionamento num fluxo de trabalho, usando uma atividade **[!UICONTROL Update shared audience]** dedicada.

A integração oferece suporte a dois tipos de Adobe Experience Cloud IDs:

* **ID do visitante**: esse tipo de identificador reconcilia os visitantes da Adobe Experience Cloud com os destinatários do Adobe Campaign.
* **ID declarado**: esse tipo de identificador reconcilia todos os tipos de dados com elementos do banco de dados do Adobe Campaign. Ele é representado no Adobe Campaign como uma chave de reconciliação predefinida.

  >[!NOTE]
  >
  > A fonte de dados de ID declarada agora também pode ser usada com a integração do serviço principal Pessoas.
  >
  >Se você estiver usando a integração do serviço principal Pessoas e quiser adicionar a integração do Audience Manager, será necessária a ajuda de um consultor da Adobe Audience Manager para evitar a perda de todas as sincronizações de ID coletadas durante a transição para o uso dessa fonte de dados de ID declarada em um contexto do Adobe Audience Manager.

Consulte:

[Documentação do Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=pt-BR){target="_blank"}

[Guia de componentes da interface central do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=pt-BR){target="_blank"}
