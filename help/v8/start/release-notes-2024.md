---
title: Notas de versão do Campaign v8 (console) 2023
description: Lista de recursos e melhorias disponíveis com as versões do Campaign v8 de 2023
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: 69ef7e81d5fc0f5cf0dc74fa16d970ef89607331
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 77%

---

# Notas de versão de 2024 {#2024-rn}

Esta página lista novos recursos, melhorias e correções que vêm com as **Versões do Campaign v8 de 2024**.


## Versão 8.6.2 {#release-8-6-2}

_23 de fevereiro de 2024_

### Correções {#fixes-8-6-2}

Esta versão corrige o seguinte problema:

* Correção de um problema de desempenho que poderia ocorrer na instância mid-sourcing (NEO-72595).

## Versão 8.6.1 {#release-8-6-1}

_14 de fevereiro de 2024_

### Novos recursos {#new-8-6-1}

* A partir desta versão, você terá acesso à nova **Interface do Campaign Web**, disponível por meio do ambiente central do Adobe Experience Cloud. A Experience Cloud é a família integrada de aplicativos, produtos e serviços de marketing digital da Adobe. Com sua interface intuitiva, você pode acessar rapidamente os aplicativos em nuvem, recursos do produto e serviços. Saiba como se conectar à Adobe Experience Cloud e acessar a interface do Adobe Campaign Web [nesta página](campaign-ui.md#ac-web-ui).


* O Adobe Campaign v8 agora se integra ao **Adobe Experience Manager as a Cloud Service**, com criação disponível exclusivamente por meio da interface do Adobe Campaign Web. [Saiba mais](../connect/ac-aem.md)

* Agora é possível usar a **Biblioteca do Adobe Experience Manager Assets** junto com o Experience Cloud Assets, mesmo se o pacote de Integração com o Adobe Experience Cloud estiver instalado em sua instância do Adobe Campaign. [Saiba mais](../connect/ac-aem.md#assets-library)

### Melhorias gerais {#improvements-8-6-1}

* O Campaign v8.6 oferece taxa de transferência aprimorada para **indicadores de rastreamento de entregas de email**. Com nossos processos otimizados, o rastreamento da ingestão e do tempo de computação é reduzido, e você pode verificar os indicadores-chave da entrega muito mais rápido.


### Atualizações sobre capacidade de entrega {#deliverability-8-6-1}

* Até fevereiro de 2024, qualquer empresa que envie mais de 5.000 mensagens de email através do Google ou do Yahoo! terá que começar a usar uma tecnologia de autenticação conhecida como DMARC (Domain-based Message Authentication Reporting and Conformance). Certifique-se de que o registro DMARC esteja configurado para todos os subdomínios usados com o Adobe Campaign. [Saiba mais](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=pt-BR){target="_blank"}

* A partir de 1º de junho de 2024, o Google e o Yahoo! exigirão que os remetentes cumpram o Cancelamento de inscrição na lista com um clique. O Adobe Campaign agora é compatível com essa opção. [Saiba mais](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=pt-BR#one-click-list-unsubscribe){target="_blank"}


### Correções {#fixes-8-6-1}

Os seguintes problemas foram corrigidos nesta versão:

NEO67892, NEO67235, NEO66797, NEO66462, NEO65091, NEO65036, NEO64984, NEO64680, NEO63973, NEO63879, NEO638795, NEO63657, NEO63539, NEO63387, NEO63294, NEO63174, NEO62964, NEO62750, NEO62686, NEO62455, NEO62406, NEO611 580, NEO61199, NEO60786, NEO59544, NEO59198, NEO59059, NEO58637, NEO55197, NEO52542, NEO50488, NEO47789
