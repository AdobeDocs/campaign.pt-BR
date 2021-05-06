---
solution: Campaign Classic
product: campaign
title: Introdução à automação de campanha
description: Introdução à automação de campanha
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
translation-type: tm+mt
source-git-commit: 1bdc1f03a824f8867ae6066196e8e3984fa73af7
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---

# Gerenciar e automatizar processos

Configure o Campaign para aproveitar os poderosos recursos de automação de campanha de marketing.

Você pode configurar:

* Workflows
* Campanhas recorrentes
* Ciclo de validação completo
* Alertas
* Envio automático de relatórios
* Eventos acionados

## Projete e use workflows{#gs-ac-wf}

Use os fluxos de trabalho do Adobe Campaign para melhorar a velocidade e a escala de cada aspecto de suas campanhas de marketing, desde a criação de segmentos e a preparação de mensagens até o delivery.

Saiba mais sobre workflows nestas seções:

* [Introdução a fluxos de trabalho](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Atividades de workflow
   * [Atividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html) de direcionamento: query, lista de leitura, enriquecimento, união e muito mais
   * [Atividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html) de controle de fluxo: scheduler, bifurcação, alerta, sinal externo e muito mais
   * [Atividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) de ação: deliveries entre canais, código Javascript, atividades CRM, agregação de atualização e muito mais
   * [Atividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) de evento: transferência de arquivos, download da Web e muito mais
* [Saiba mais por meio de casos de uso completos](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/about-workflow-use-cases.html)
* [Criar um público-alvo em um workflow de campanha de marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [Práticas recomendadas para fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [Workflows técnicos incorporados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [Monitorar a execução de workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)

## Configurar campanhas recorrentes

Crie uma instância de delivery recorrente e crie uma nova cada vez que ela for executada. Por exemplo, se o fluxo de trabalho for projetado para ser executado uma vez por semana, o resultado será 52 deliveries em um ano. Isso também significa que os logs serão separados por cada instância de delivery.

:seta_upper_right: Saiba como criar uma campanha recorrente na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).

## Configurar o ciclo de validação completo

Configure o processo de aprovação para cada etapa de seus deliveries e garanta o monitoramento e controle completos dos vários processos de suas campanhas de marketing: direcionamento, conteúdo, orçamento, extração e envio de uma prova.

As notificações são enviadas aos operadores do Adobe Campaign que são definidos como revisores para informá-los de uma solicitação de aprovação.

:seta_upper_right: Saiba como configurar e gerenciar o processo de aprovação na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html).


## Enviar alertas

Como operador do Campaign, você pode receber alertas quando ocorrer uma falha.

Você pode criar um workflow que permitirá monitorar o status de um conjunto de workflows e enviar mensagens recorrentes aos supervisores.

:seta_upper_right: Saiba como criar um workflow para monitorar o status de outros workflows na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=en#step-1--creating-the-monitoring-workflow).

Você também pode receber um alerta quando ocorrer uma falha

## Enviar relatórios automáticos

:seta_upper_right: Saiba como enviar um relatório automaticamente para uma lista de operadores [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=en#step-1--creating-the-recipient-list).


## Aproveitar eventos de acionador

Use as mensagens transacionais do Campaign para automatizar as mensagens geradas a partir de eventos acionados de sistemas de informações. Essas mensagens transacionais podem ser fatura, confirmação de pedido, confirmação de remessa, alteração de senha, notificação de indisponibilidade de produto, extrato de conta ou criação de conta de site, por exemplo. Essas mensagens podem ser enviadas individualmente ou em lote por email, SMS ou notificações por push)ons.

:seta_upper_right: Saiba mais sobre os recursos de mensagens transacionais na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging).


Conecte o Adobe Campaign e o Adobe Analytics para recuperar as ações do usuário e enviar mensagens personalizadas em tempo quase real.

:seta_upper_right: Saiba como integrar o Campaign com acionadores do Analytics na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud).

:bulb: Saiba como integrar o Campaign com outras soluções em [esta seção](../start/connect.md)
