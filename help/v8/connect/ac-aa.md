---
solution: Campaign
product: Adobe Campaign
title: Trabalhar com o Campaign e o Adobe Analytics
description: Saiba como trabalhar com o Campaign e o Adobe Analytics
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 48%

---

# Trabalhar com o Campaign e o Adobe Analytics

## Acionadores da Experience Cloud

Você pode usar Experience Cloud Triggers para conectar dados entre o Adobe Campaign e o Adobe Analytics usando o pipeline. O pipeline recupera as ações ou acionadores dos usuários do seu site. O abandono do carrinho é um exemplo de acionador. Os acionadores são processados no Adobe Campaign para enviar emails em tempo quase real.

:voice_balloon: Como um usuário do Managed Cloud Services, [entre em contato com o Adobe](../start/support.md#support) para implementar acionadores de Experience Cloud com o Campaign.

## Conector de dados do Adobe Analytics

PARA ATUALIZAR COM A NOVA INTEGRAÇÃO

Você também pode configurar os Data Connectors do Adobe Analytics para integrar o Campaign e o Analytics.

O conector de dados (anteriormente conhecido como Adobe Genesis) permite que o Adobe Campaign e o Adobe Analytics interajam por meio do pacote **Web Analytics connectors**. Essa integração compartilha dados do Analytics para o Campaign como segmentos relacionados ao comportamento do usuário após um email. Por outro lado, ele envia indicadores e atributos de campanhas de email entregues pelo Adobe Campaign para o Adobe Analytics – Data Connector.

Graças a essas integrações, o Adobe Campaign pode recuperar dados do comportamento do visitante para um ou mais sites, após uma campanha de marketing, e (após a análise) executar campanhas de re-marketing com uma visualização para convertê-los em compradores. Por outro lado, as ferramentas do Web Analytics permitem que o Adobe Campaign encaminhe indicadores e atributos de campanha para suas plataformas.

Os campos de ação para cada ferramenta são os seguintes:

* Adobe Analytics:

   * marca as campanhas de e-mail iniciadas com o Adobe Campaign
   * salva o comportamento do recipient, no site navegado depois de clicar no e-mail da campanha, no formato de segmentos. Os segmentos estão relacionados a produtos abandonados (visualizados, mas não adicionados ao carrinho ou comprados), compras ou abandonos de carrinho.

* Adobe Campaign:

   * envia os indicadores e os atributos da campanha para o conector, que, por sua vez, os encaminha para a ferramenta Web Analytics
   * recupera e analisa segmentos
   * e dispara uma campanha de re-marketing

CONSULTE https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html?lang=en#technical-workflows-of-web-analytics-processes

:voice_balloon: Como um usuário do Managed Cloud Services, [entre em contato com o Adobe](../start/support.md#support) para integrar o Adobe Analytics Data Connector ao Campaign.

