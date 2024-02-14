---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 2f8cee4522efb59782a568334fc1300fc39d559f
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 16%

---

# Versão mais recente{#latest-release}

O Adobe Campaign é atualizado regularmente. Essa frequência regular de atualizações tem como objetivo disponibilizar a você o que há de melhor e mais recente, mantendo seu ambiente seguro e melhorando sua experiência com nosso produto. A Adobe recomenda que todos os clientes atualizem para a versão mais recente. Saiba mais sobre versões e recomendações do Campaign [nesta página](upgrades.md).

Como usuário do Managed Cloud Service, sua instância é atualizada pelo Adobe a cada nova versão. O Adobe entrará em contato com você e atualizará seus ambientes. Console do cliente do Campaign **deve ser atualizado para a mesma versão** como servidores do Campaign. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

Além disso, como cliente, verifique se você está usando as versões mais recentes compatíveis dos sistemas listados na [Matriz de compatibilidade](compatibility-matrix.md).


## Versão 8.6.1 {#release-8-6-1}

_14 de fevereiro de 2024_


### Novos recursos {#new-8-6-1}

* A partir desta versão, você terá acesso ao novo **Interface do usuário da Web do Campaign**, disponível por meio do ambiente central do Adobe Experience Cloud. A Experience Cloud é a família integrada de aplicativos, produtos e serviços de marketing digital da Adobe. Com sua interface intuitiva, você pode acessar rapidamente os aplicativos em nuvem, recursos do produto e serviços. Saiba como se conectar ao Adobe Experience Cloud e acessar a interface da Web do Adobe Campaign [nesta página](campaign-ui.md#ac-web-ui).


* O Adobe Campaign v8 agora se integra ao **Adobe Experience Manager as a Cloud Service**, com criação disponível exclusivamente por meio da interface da Web do Adobe Campaign. [Saiba mais](../connect/ac-aem.md)

* Agora você pode usar o **Biblioteca do Adobe Experience Manager Assets** junto com o Experience Cloud Assets, mesmo se o pacote Integration with the Adobe Experience Cloud estiver instalado em sua instância do Adobe Campaign. [Saiba mais](../connect/ac-aem.md#assets-library)

### Melhorias gerais {#improvements-8-6-1}

* O Campaign v8.6 oferece taxa de transferência aprimorada para **indicadores de rastreamento de deliveries de email**. Com nossos processos otimizados, o rastreamento da assimilação e do tempo de computação é reduzido, e você pode verificar os indicadores-chave de entrega muito mais rapidamente.


### Atualizações da entregabilidade {#deliverability-8-6-1}

* Até fevereiro de 2024, qualquer empresa que envie mais de 5.000 mensagens de email por meio do Google ou do Yahoo! O terá que começar a usar uma tecnologia de autenticação conhecida como DMARC (Domain-based Message Authentication Reporting and Conformance). Verifique se o registro DMARC está configurado para todos os subdomínios que você está usando com o Adobe Campaign. [Saiba mais](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=pt-BR){target="_blank"}

* A partir de 1º de junho de 2024, o Google e o Yahoo! exigirá que os remetentes cumpram o One-Click List-Unsubscribe. O Adobe Campaign agora é compatível com essa opção. [Saiba mais](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Correções {#fixes-8-6-1}

Os seguintes problemas foram corrigidos nessa versão: NEO67892, NEO67235, NEO66797, NEO66462, NEO65091, NEO65036, NEO64984, NEO64680, NEO63973, NEO63879, O-63815, NEO63657, NEO63539, NEO63387, NEO63294, NEO63174, NEO62964, NEO62750, NEO62686, NEO62455, NEO62400 6, NEO61580, NEO61199, NEO60786, NEO59544, NEO59198, NEO59059, NEO58637, NEO55197, NEO52542, NEO50488, NEO47789