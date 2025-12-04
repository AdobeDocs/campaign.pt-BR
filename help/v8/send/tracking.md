---
title: Introdução ao rastreamento de mensagens
description: Saiba mais sobre os recursos de rastreamento no Adobe Campaign
feature: Monitoring, Email
role: User
level: Beginner
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: 57e177dc6c30502f2ed3bb08b18586fa5399e89c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 32%

---

# Introdução ao rastreamento de mensagens {#get-started-tracking}

Graças às suas funcionalidades de rastreamento, o Adobe Campaign permite que você rastreie as mensagens enviadas e verifique o comportamento dos recipients: abrir, clicar em links, cancelar assinatura e muito mais.

Essas informações são recuperadas na guia **[!UICONTROL Tracking]** do perfil de cada destinatário da entrega. Esta guia apresenta todos os links de URL rastreados e clicados pelo destinatário selecionado na lista. Esse é o acúmulo de todos os URLs rastreados nas entregas que ainda estão na tela de envio. A lista pode ser configurada e normalmente contém: o URL clicado, a data e a hora do clique e o documento no qual o URL foi localizado.

O **painel de entrega** também é uma ferramenta importante para monitorar suas entregas e possíveis problemas durante o envio de mensagens.

O diagrama a seguir mostra os estágios da caixa de diálogo entre o usuário e os vários servidores.

<img src="assets/tracking-diagram.png" width="70%">

>[!NOTE]
>
>A configuração de rastreamento é executada pela Adobe para implantações do Managed Cloud Services.

## Rastreamento de mensagens {#message-tracking}

**Links rastreados**

Você pode rastrear a recepção de mensagens e a ativação dos links inseridos no conteúdo da mensagem para entender melhor o comportamento dos recipients.

[Saiba mais sobre links rastreados](tracked-links.md)

**Rastreamento de URL**

As opções de rastreamento podem ser configuradas por meio da ativação ou desativação de URLs rastreados.

[Saiba mais sobre as opções de rastreamento de URL](url-tracking.md)

**Personalização do link rastreado**

Os recursos de rastreamento de campanha permitem adicionar links em emails que podem ser personalizados e que oferecem suporte ao rastreamento.

[Saiba mais sobre o rastreamento de links personalizados](personalized-links.md)

**Logs de rastreamento**

O fluxo de trabalho técnico **Rastreamento** recupera os dados de rastreamento depois que a entrega é enviada e o rastreamento é ativado. Esses dados podem ser encontrados na guia Rastreamento do seu delivery.

[Saiba mais sobre logs de rastreamento](tracking-logs.md)

**Testar o rastreamento**

Antes de enviar as mensagens com o rastreamento, você pode testar o rastreamento na mirror page, em logs de email e em links.

[Saiba mais sobre o rastreamento de testes](testing-tracking.md)

## Rastreamento de relatórios {#tracking-reports}

**Estatísticas de rastreamento**

Este relatório fornece estatísticas sobre aberturas, cliques e transações e permite rastrear o impacto de marketing do delivery.

[Saiba mais sobre relatórios de rastreamento](../reporting/delivery-reports.md#tracking-indicators)

**Fluxos de clique e URLs**

Este relatório mostra a lista de páginas visitadas após uma entrega.

[Saiba mais sobre URLs e fluxos de clique](../reporting/delivery-reports.md#urls-and-click-streams)

**Pessoa/pessoas e destinatários**

Entenda melhor a diferença de rastreamento entre uma pessoa/pessoas e um recipient no Adobe Campaign com este exemplo.

[Saiba mais sobre pessoas e recipients direcionados](../reporting/metrics-calculation.md#targeted-persons---recipients)

**Indicadores de rastreamento**

Este relatório combina os principais indicadores para rastrear o comportamento dos recipients ao receber o delivery, como abertura, taxas de click-through e fluxos de cliques.

[Saiba mais sobre indicadores de rastreamento](../reporting/delivery-reports.md#tracking-indicators)

**Cálculo do indicador**

As diferentes tabelas fornecem a lista de indicadores usados nos diferentes relatórios e suas fórmulas de cálculo, dependendo do tipo de delivery.

[Saiba mais sobre o cálculo de indicador](../reporting/metrics-calculation.md)


