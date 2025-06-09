---
title: Compartilhar públicos-alvo com soluções da Adobe Experience Cloud
description: Saiba como compartilhar públicos-alvo com soluções da Adobe Experience Cloud
feature: Audiences
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 74%

---

# Compartilhar públicos-alvo com soluções da Adobe Experience Cloud{#shared-audiences}


Opção 1: origens e destinos da AEP

Opção 2: Adobe People/AAM

É possível integrar o **Adobe Campaign** ao **Serviço principal de pessoas** ou ao Adobe Audience Manager. Depois será possível:

* Importar públicos/segmentos compartilhados de diferentes soluções da Adobe Experience Cloud para o Adobe Campaign. Os públicos podem ser importados por meio de listas no Adobe Campaign.

* Exportar listas no formato de públicos-alvo compartilhados da Adobe Experience Cloud. Esses audiences podem ser usados nas diferentes soluções da Adobe Experience Cloud que você usa. Os públicos-alvo podem ser exportados após o direcionamento num fluxo de trabalho, usando uma atividade **[!UICONTROL Update shared audience]** dedicada.

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

[Guia de Componentes da Interface Central do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=pt-BR){target="_blank"}
