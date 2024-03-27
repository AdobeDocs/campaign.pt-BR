---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3a63539bc6bb20fa79bdac76dd60efe7b232458b
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 100%

---

# Versão mais recente{#latest-release}

O Adobe Campaign é atualizado regularmente. Essa frequência regular de atualizações tem como objetivo disponibilizar a você o que há de melhor e mais recente, mantendo seu ambiente seguro e melhorando sua experiência com nosso produto. A Adobe recomenda que todos os clientes atualizem para a versão mais recente. Saiba mais sobre as versões e recomendações do Campaign [nesta página](upgrades.md).

Como usuário do Managed Cloud Services, sua instância é atualizada pela Adobe a cada nova versão. A Adobe entrará em contato com você e atualizará seus ambientes. O console do cliente do Campaign **precisa ser atualizado para a mesma versão** dos servidores do Campaign. Saiba como atualizar seu console do cliente [nesta página](../start/connect.md#upgrade-ac-console).

Além disso, como cliente, verifique se você está usando a versão mais recente compatível dos sistemas listados na [Matriz de compatibilidade](compatibility-matrix.md).


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

Os seguintes problemas foram corrigidos nessa versão:
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789