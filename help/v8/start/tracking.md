---
title: Introdução aos recursos de rastreamento e monitoramento
description: Introdução aos recursos de rastreamento e monitoramento
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 95ed0369-7215-496b-8e11-fe264c436488
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 50%

---

# Rastrear e monitorar mensagens{#gs-ac-reports}

## Recursos de rastreamento no Campaign

Os recursos de rastreamento de campanha rastreiam as mensagens enviadas e ajudam a analisar o comportamento dos recipients: abrir, clicar em links, assinaturas/unsubscription e muito mais. Você pode acessar logs, relatórios e métricas dedicados, consultar o banco de dados para analisar os dados coletados e muito mais.

↗️  Para obter mais informações, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#tracking-tab){target=&quot;_blank&quot;}.

O painel de delivery é uma ferramenta essencial para monitorar seus deliveries e possíveis problemas durante o envio de mensagens.

↗️ Para obter mais informações, consulte a documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

Os principais recursos de rastreamento disponíveis no Campaign estão listados abaixo.

### Rastreamento de mensagens {#message-tracking}

<img src="assets/do-not-localize/icon-message-tracking.svg" width="60px">

**Links rastreados**

Você pode rastrear a recepção de mensagens e a ativação dos links inseridos no conteúdo da mensagem para entender melhor o comportamento dos recipients.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=en#sending-messages){target=&quot;_blank&quot;}

**Rastreamento de URL**

As opções de rastreamento podem ser configuradas por meio da ativação ou desativação de URLs rastreados.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/personalizing-url-tracking.html?lang=en#sending-messages){target=&quot;_blank&quot;}


**Personalização do link rastreado**

Os recursos de rastreamento de Campaign permitem que você adicione links em emails que podem ser personalizados e que oferecem suporte ao rastreamento.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/tracking-personalized-links/tracking-personalized-links.html?lang=en#sending-messages){target=&quot;_blank&quot;}

**Logs de rastreamento**

O workflow técnico **Tracking** recupera os dados de rastreamento depois que o delivery é enviado e o rastreamento é ativado. Esses dados podem ser encontrados na guia Rastreamento do seu delivery.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/accessing-the-tracking-logs.html?lang=en#sending-messages){target=&quot;_blank&quot;}

**Testar o rastreamento**

Antes de enviar as mensagens com o rastreamento, você pode testar o rastreamento na mirror page, em logs de email e em links.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/testing-tracking.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### Rastreamento de aplicativo web {#web-application-tracking}

<img src="assets/do-not-localize/icon-web-app.svg" width="60px">

**Rastreamento de uma aplicação web**

Também é possível rastrear e medir visitas em páginas de aplicação web com tags de rastreamento. Essa funcionalidade pode ser usada para todos os tipos de aplicação web, como formulários e pesquisas online.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/tracking-a-web-application.html?lang=en#designing-content){target=&quot;_blank&quot;}

**Recusar rastreamento da aplicação web**

A opção de recusar o rastreamento de aplicações web permite que você interrompa o rastreamento dos comportamentos da Web de usuários finais que recusam o rastreamento comportamental. Você pode incluir a capacidade de exibir um banner em aplicações web ou páginas de aterrissagem para permitir que os usuários recusem.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out.html?lang=en#designing-content){target=&quot;_blank&quot;}

### Rastreamento de relatórios {#tracking-reports}

<img src="assets/do-not-localize/icon_monitor.svg" width="60px">

**Estatísticas de rastreamento**

Este relatório fornece estatísticas sobre aberturas, cliques e transações e permite rastrear o impacto de marketing do delivery.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/about-message-tracking.html?lang=en#tracking-reports){target=&quot;_blank&quot;}

**Fluxos de clique e URLs**

Este relatório mostra a lista de páginas visitadas após um delivery.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#urls-and-click-streams){target=&quot;_blank&quot;}

**Pessoa/pessoas e recipients**

Entenda melhor a diferença de rastreamento entre uma pessoa/pessoas e um recipient no Adobe Campaign com este exemplo.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html?lang=en#reporting){target=&quot;_blank&quot;}

**Indicadores de rastreamento**

Este relatório combina os principais indicadores para rastrear o comportamento dos recipients ao receber o delivery, como abertura, taxas de click-through e fluxos de cliques.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#reporting){target=&quot;_blank&quot;}

**Cálculo do indicador**

As diferentes tabelas fornecem a lista de indicadores usados nos diferentes relatórios e suas fórmulas de cálculo, dependendo do tipo de delivery.

↗️ [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/indicator-calculation.html?lang=en#reporting){target=&quot;_blank&quot;}

## Diretrizes de monitoramento

A Adobe Campaign oferece um conjunto de recursos para monitorar seus processos e seu ambiente.

### Monitore seus deliveries

O monitoramento de deliveries após serem enviados é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes.

↗️ Saiba mais sobre as informações que você pode monitorar após enviar um delivery, entenda como as falhas de delivery e quarentenas são gerenciadas em [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### Monitorar workflows

↗️ Saiba como monitorar a execução do workflow em [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

### Monitore sua instância

↗️ Diretrizes de monitoramento da instância estão disponíveis na documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html?lang=en#monitoring-campaign-classic){target=&quot;_blank&quot;}

Use a interface de autoatendimento da trilha de auditoria para monitorar as alterações feitas em sua instância. A trilha de auditoria captura, em tempo real, uma lista abrangente de ações e eventos que ocorrem em sua instância do Adobe Campaign. Você pode acessar um histórico de dados para ajudar a responder perguntas como: o que aconteceu com seus fluxos de trabalho e quem os atualizou pela última vez ou o que seus usuários fizeram na instância .

↗️ Saiba mais sobre a Trilha de auditoria na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/audit-trail.html?lang=en#accessing-audit-trail){target=&quot;_blank&quot;}
