---
title: Compartilhar públicos-alvo com soluções da Adobe Experience Cloud
description: Saiba como compartilhar públicos-alvo com soluções da Adobe Experience Cloud
feature: Subscriptions
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ec46a6f41d640b11306a88d6a966f81f8c2e43e0
workflow-type: ht
source-wordcount: '272'
ht-degree: 100%

---

# Compartilhar públicos-alvo com soluções da Adobe Experience Cloud{#shared-audiences}


Opção 1: origens e destinos da AEP

Opção 2: Adobe People/AAM

É possível integrar o **Adobe Campaign** ao **Serviço principal de pessoas** ou ao Adobe Audience Manager. Depois será possível:

* Importar públicos/segmentos compartilhados de diferentes soluções da Adobe Experience Cloud para o Adobe Campaign. Os públicos podem ser importados por meio de listas no Adobe Campaign.

* Exportar listas no formato de públicos  compartilhados da Adobe Experience Cloud. Esses audiences podem ser usados nas diferentes soluções da Adobe Experience Cloud que você usa. Os públicos podem ser exportados após o direcionamento num fluxo de trabalho, usando uma atividade **[!UICONTROL Update shared audience]** dedicada.

A integração oferece suporte a dois tipos de Adobe Experience Cloud IDs:

* **ID do visitante**: esse tipo de identificador reconcilia os visitantes da Adobe Experience Cloud com os recipients do Adobe Campaign.
* **ID declarado**: esse tipo de identificador reconcilia todos os tipos de dados com elementos do banco de dados do Adobe Campaign. Ele é representado no Adobe Campaign como uma chave de reconciliação predefinida.

   >[!NOTE]
   >
   > A fonte de dados de ID declarada agora também pode ser usada com a integração do serviço principal Pessoas.
   >
   >Se você estiver usando a integração do serviço principal Pessoas e quiser adicionar a integração do Audience Manager, será necessária a ajuda de um consultor do Adobe Audience Manager para evitar a perda de todas as sincronizações de ID coletadas durante a transição para o uso dessa fonte de dados de ID declarada em um contexto do Adobe Audience Manager.

Consulte:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=pt-BR](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=pt-BR)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=pt-BR](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=pt-BR)