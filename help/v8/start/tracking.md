---
title: Introdução aos recursos de rastreamento e monitoramento
description: Introdução aos recursos de rastreamento e monitoramento
feature: Monitoring
role: User
level: Beginner, Intermediate
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: a78019d11a0a2acbd8c0d9ba7c2082c09f90356c
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 32%

---

# Rastrear e monitorar mensagens{#gs-ac-reports}

## Recursos de rastreamento no Campaign

Os recursos de rastreamento de campanha rastreiam as mensagens enviadas e ajudam a analisar o comportamento dos recipients: abrir, clicar em links, assinar/cancelar assinatura e muito mais. Você pode acessar logs dedicados, relatórios e métricas, consultar o banco de dados para revisar dados coletados e muito mais.

Para obter mais informações, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html#tracking-tab){target="_blank"}.

O painel de delivery é uma ferramenta essencial para monitorar seus deliveries e possíveis problemas durante o envio de mensagens.

Para obter mais informações, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"}.

Os principais recursos de rastreamento disponíveis no Campaign estão listados abaixo.

### Rastreamento de mensagens {#message-tracking}

<img src="assets/do-not-localize/icon-message-tracking.svg" width="60px">

**Links rastreados**

Você pode rastrear a recepção de mensagens e a ativação dos links inseridos no conteúdo da mensagem para entender melhor o comportamento dos recipients.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html#sending-messages){target="_blank"}

**Rastreamento de URL**

As opções de rastreamento podem ser configuradas por meio da ativação ou desativação de URLs rastreados.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/personalizing-url-tracking.html#sending-messages){target="_blank"}


**Personalização do link rastreado**

Os recursos de rastreamento de campanha permitem adicionar links em emails que podem ser personalizados e que oferecem suporte ao rastreamento.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/tracking-personalized-links/tracking-personalized-links.html#sending-messages){target="_blank"}

**Logs de rastreamento**

O fluxo de trabalho técnico **Rastreamento** recupera os dados de rastreamento depois que a entrega é enviada e o rastreamento é ativado. Esses dados podem ser encontrados na guia Rastreamento do seu delivery.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/accessing-the-tracking-logs.html#sending-messages){target="_blank"}

**Testar o rastreamento**

Antes de enviar as mensagens com o rastreamento, você pode testar o rastreamento na mirror page, em logs de email e em links.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/testing-tracking.html#sending-messages){target="_blank"}

### Rastreamento de aplicativo web {#web-application-tracking}

<img src="assets/do-not-localize/icon-web-app.svg" width="60px">

**Rastreamento de uma aplicação web**

Também é possível rastrear e medir visitas em páginas de aplicação web com tags de rastreamento. Essa funcionalidade pode ser usada para todos os tipos de aplicação web, como formulários e pesquisas online.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/tracking-a-web-application.html#designing-content){target="_blank"}

**Recusar rastreamento da aplicação web**

A opção de recusar o rastreamento de aplicações web permite que você interrompa o rastreamento dos comportamentos da Web de usuários finais que recusam o rastreamento comportamental. Você pode incluir a capacidade de exibir um banner em aplicações web ou páginas de aterrissagem para permitir que os usuários recusem.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out.html#designing-content){target="_blank"}

### Rastreamento de relatórios {#tracking-reports}

<img src="assets/do-not-localize/icon_monitor.svg" width="60px">

**Estatísticas de rastreamento**

Este relatório fornece estatísticas sobre aberturas, cliques e transações e permite rastrear o impacto de marketing do delivery.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/about-message-tracking.html#tracking-reports){target="_blank"}

**Fluxos de clique e URLs**

Este relatório mostra a lista de páginas visitadas após uma entrega.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html#urls-and-click-streams){target="_blank"}

**Pessoa/pessoas e destinatários**

Entenda melhor a diferença de rastreamento entre uma pessoa/pessoas e um recipient no Adobe Campaign com este exemplo.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html#reporting){target="_blank"}

**Indicadores de rastreamento**

Este relatório combina os principais indicadores para rastrear o comportamento dos recipients ao receber o delivery, como abertura, taxas de click-through e fluxos de cliques.

[Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html#reporting){target="_blank"}

**Cálculo do indicador**

As diferentes tabelas fornecem a lista de indicadores usados nos diferentes relatórios e suas fórmulas de cálculo, dependendo do tipo de delivery.

[Saiba mais](../reporting/metrics-calculation.md)

## Diretrizes de monitoramento

O Adobe Campaign oferece um conjunto de recursos para monitorar seus processos e seu ambiente.

### Monitore seus deliveries

O monitoramento de entregas após o envio é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes.

Saiba mais sobre as informações que você pode monitorar após enviar uma entrega, entenda como as falhas de entrega e as quarentenas são gerenciadas na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=pt-BR#sending-messages){target="_blank"}

### Monitorar workflows

Saiba como monitorar a execução do fluxo de trabalho em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html)

### Monitorar sua instância

As diretrizes de monitoramento de instâncias estão disponíveis na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html#monitoring-campaign-classic){target="_blank"}

Use a interface de autoatendimento da trilha de auditoria para monitorar alterações feitas na instância. A trilha de auditoria captura em tempo real uma lista abrangente de ações e eventos que ocorrem na sua instância do Adobe Campaign. Você pode acessar um histórico de dados para ajudar a responder perguntas como: o que aconteceu com seus workflows e quem os atualizou pela última vez ou o que seus usuários fizeram na instância.

Saiba mais sobre a Trilha de auditoria nesta [página](../reporting/audit-trail.md){target="_blank"}
