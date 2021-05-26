---
solution: Campaign v8
product: Adobe Campaign
title: Trabalhar com o Campaign e o Adobe Analytics
description: Saiba como trabalhar com o Campaign e o Adobe Analytics
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 44%

---

# Trabalhar com o Campaign e o Adobe Analytics


## Conector Adobe Analytics

Você pode configurar os Conectores do Adobe Analytics para integrar o Campaign e o Analytics.

O Adobe Analytics Connector permite que o Adobe Campaign e o Adobe Analytics interajam por meio do complemento **Web Analytics connectors**. Essa integração compartilha dados do Analytics para o Campaign como segmentos relacionados ao comportamento do usuário após um email. Por outro lado, ele envia indicadores e atributos de campanhas de email entregues pelo Adobe Campaign para o Adobe Analytics – Data Connector.

Usando o Adobe Analytics Connector, o Adobe Campaign tem uma maneira de medir o público-alvo da Internet (Web Analytics). Graças a essas integrações, o Adobe Campaign pode recuperar dados do comportamento do visitante para um ou mais sites, após uma campanha de marketing, e (após a análise) executar campanhas de re-marketing com uma visualização para convertê-los em compradores. Por outro lado, as ferramentas do Web Analytics permitem que o Adobe Campaign encaminhe indicadores e atributos de campanha para suas plataformas.

Os campos de ação para cada ferramenta são os seguintes:

* **Adobe Analytics**

   * marca as campanhas de e-mail iniciadas com o Adobe Campaign
   * salva o comportamento do recipient, no site navegado depois de clicar no e-mail da campanha, no formato de segmentos. Os segmentos estão relacionados a produtos abandonados (visualizados, mas não adicionados ao carrinho ou comprados), compras ou abandonos de carrinho.

* **Adobe Campaign**

   * envia os indicadores e os atributos da campanha para o conector, que, por sua vez, os encaminha para a ferramenta Web Analytics
   * recupera e analisa segmentos
   * e dispara uma campanha de re-marketing

Saiba mais sobre o Adobe Campaign e Adobe Analytics em [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html)

[!DNL :speech_balloon:]  Como um usuário do Managed Cloud Services,  [entre em contato com a ](../start/campaign-faq.md#support) Adobe para integrar o Adobe Analytics Data Connector ao Campaign.


## Acionadores da Experience Cloud

Você pode usar Experience Cloud Triggers para conectar dados entre o Adobe Campaign e o Adobe Analytics usando o pipeline. O pipeline recupera as ações ou acionadores do usuário do seu site. O abandono do carrinho é um exemplo de acionador. Os acionadores são processados no Adobe Campaign para enviar emails em tempo quase real.

Saiba mais sobre Adobe Campaign e Experience Cloud Triggers em [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en).

[!DNL :speech_balloon:]  Como usuário do Managed Cloud Services,  [entre em contato com a ](../start/campaign-faq.md#support) Adobe para implementar acionadores de Experience Cloud com o Campaign.
