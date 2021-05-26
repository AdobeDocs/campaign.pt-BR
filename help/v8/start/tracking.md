---
solution: Campaign v8
product: Adobe Campaign
title: Introdução aos recursos de rastreamento e monitoramento
description: Introdução aos recursos de rastreamento e monitoramento
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 95ed0369-7215-496b-8e11-fe264c436488,e7931de5-83ce-431d-ae81-83793d257550
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 37%

---

# Rastrear e monitorar mensagens{#gs-ac-reports}

## Recursos de rastreamento no Campaign

Os recursos de rastreamento de campanha rastreiam as mensagens enviadas e ajudam a analisar o comportamento dos recipients: abrir, clicar em links, assinaturas/unsubscription e muito mais. Você pode acessar logs, relatórios e métricas dedicados, consultar o banco de dados para analisar os dados coletados e muito mais.

[!DNL :arrow_upper_right:]  Para obter mais informações, consulte a documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#tracking-tab).

O painel de delivery é uma ferramenta essencial para monitorar seus deliveries e possíveis problemas durante o envio de mensagens.

[!DNL :arrow_upper_right:] Para obter mais informações, consulte a documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=en#sending-messages).

Os principais recursos de rastreamento disponíveis no Campaign estão listados abaixo.

### Rastreamento de mensagens {#message-tracking}

<img src="assets/do-not-localize/icon-message-tracking.svg" width="60px">

**Links rastreados**

Você pode rastrear a recepção de mensagens e a ativação dos links inseridos no conteúdo da mensagem para entender melhor o comportamento dos recipients.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=en#sending-messages)

**Rastreamento de URL**

As opções de rastreamento podem ser configuradas por meio da ativação ou desativação de URLs rastreados.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/personalizing-url-tracking.html?lang=en#sending-messages)


**Personalização do link rastreado**

Os recursos de rastreamento de Campaign permitem que você adicione links em emails que podem ser personalizados e que oferecem suporte ao rastreamento.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/tracking-personalized-links/tracking-personalized-links.html?lang=en#sending-messages)

**Logs de rastreamento**

O workflow técnico **Tracking** recupera os dados de rastreamento depois que o delivery é enviado e o rastreamento é ativado. Esses dados podem ser encontrados na guia Rastreamento do seu delivery.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/accessing-the-tracking-logs.html?lang=en#sending-messages)

**Testar o rastreamento**

Antes de enviar as mensagens com o rastreamento, você pode testar o rastreamento na mirror page, em logs de email e em links.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/testing-tracking.html?lang=en#sending-messages)

### Rastreamento de aplicação web {#web-application-tracking}

<img src="assets/do-not-localize/icon-web-app.svg" width="60px">

**Rastreamento de uma aplicação web**

Também é possível rastrear e medir visitas em páginas de aplicação web com tags de rastreamento. Essa funcionalidade pode ser usada para todos os tipos de aplicação web, como formulários e pesquisas online.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/tracking-a-web-application.html?lang=en#designing-content)

**Recusar rastreamento da aplicação web**

A opção de recusar o rastreamento de aplicações web permite que você interrompa o rastreamento dos comportamentos da Web de usuários finais que recusam o rastreamento comportamental. Você pode incluir a capacidade de exibir um banner em aplicações web ou páginas de aterrissagem para permitir que os usuários recusem.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out.html?lang=en#designing-content)

### Rastreamento de relatórios {#tracking-reports}

<img src="assets/do-not-localize/icon_monitor.svg" width="60px">

**Estatísticas de rastreamento**

Este relatório fornece estatísticas sobre aberturas, cliques e transações e permite rastrear o impacto de marketing do delivery.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/about-message-tracking.html?lang=en#tracking-reports)

**Fluxos de clique e URLs**

Este relatório mostra a lista de páginas visitadas após um delivery.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#urls-and-click-streams)

**Pessoa/pessoas e recipients**

Entenda melhor a diferença de rastreamento entre uma pessoa/pessoas e um recipient no Adobe Campaign com este exemplo.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html?lang=en#reporting)

**Indicadores de rastreamento**

Este relatório combina os principais indicadores para rastrear o comportamento dos recipients ao receber o delivery, como abertura, taxas de click-through e fluxos de cliques.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#reporting)

**Cálculo do indicador**

As diferentes tabelas fornecem a lista de indicadores usados nos diferentes relatórios e suas fórmulas de cálculo, dependendo do tipo de delivery.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/indicator-calculation.html?lang=en#reporting)

## Orientações de monitoramento

A Adobe Campaign oferece um conjunto de recursos para monitorar seus processos e seu ambiente.

### Monitore seus deliveries

O monitoramento de deliveries após serem enviados é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes.

[!DNL :arrow_upper_right:] Saiba mais sobre as informações que você pode monitorar após enviar um delivery, entenda como as falhas de delivery e as quarentenas são gerenciadas na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)

### Monitorar workflows

[!DNL :arrow_upper_right:] Saiba como monitorar a execução do workflow na documentação do   [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=en#automating-with-workflows)

### Monitore sua instância

[!DNL :arrow_upper_right:] As diretrizes de monitoramento de instância estão disponíveis na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html?lang=en#monitoring-campaign-classic)

Use a interface de autoatendimento da trilha de auditoria para monitorar as alterações feitas em sua instância. A trilha de auditoria captura, em tempo real, uma lista abrangente de ações e eventos que ocorrem em sua instância do Adobe Campaign. Você pode acessar um histórico de dados para ajudar a responder perguntas como: o que aconteceu com seus fluxos de trabalho e quem os atualizou pela última vez ou o que seus usuários fizeram na instância .

[!DNL :arrow_upper_right:] Saiba mais sobre a Trilha de auditoria na documentação do   [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/audit-trail.html?lang=en#accessing-audit-trail)
