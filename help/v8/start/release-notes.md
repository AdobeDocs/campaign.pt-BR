---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d4b172bc6b874d542dc9f2725e3bc35679fc7635
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 29%

---

# Versões mais recentes {#latest-release}

Esta página lista novos recursos, melhorias e correções que acompanham as versões mais recentes do Campaign v8 (console). Saiba mais sobre lançamentos, versões e atualizações do Campaign [nesta página](upgrades.md).

## Versão 8.6.4 {#release-8-6-4}

_15 de janeiro de 2025_


### Melhorias gerais {#improvements-8-6-4}

* A estabilidade do aplicativo do Campaign foi aprimorada durante a análise de entrega no contexto de uma [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Essa versão vem com mecanismos de arquitetura FFDA aprimorados e fortalecidos, incluindo gerenciamento de chaves, armazenamento temporário e replicação de dados.
* Novos fluxos de trabalho técnicos foram introduzidos para a [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md). Esses workflows replicam o delivery e dados relacionados centralizando solicitações de replicação paralela em tabelas correspondentes. Estes fluxos de trabalho começam com `Replicate nms`.
* Uma nova opção **Habilitar supervisor de watchdog para manter o fluxo de trabalho em execução permanentemente** agora está disponível nas propriedades do fluxo de trabalho. Quando essa opção está habilitada, os workflows são reiniciados automaticamente após um erro. A reinicialização ocorre a cada 30 segundos por padrão. Para ajustar esse intervalo, você pode criar uma nova opção `XtkWorkflow_WatchdogTimerTimeout` e definir um tipo de dados Integer para especificar o novo atraso. Essa opção só deve ser habilitada em workflows técnicos.

### Melhorias de segurança {#security-8-6-4}

A conexão com soluções e aplicativos Adobe por meio da conta externa **[!UICONTROL Adobe Experience Cloud]** foi atualizada para reforçar a segurança.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Atualizações de compatibilidade {#comp-8-6-4}

Os databricks agora são compatíveis como um banco de dados externo com o Federated Data Access (FDA) do Adobe Campaign. Saiba mais [nesta página](compatibility-matrix.md#FederatedDataAccessFDA).

### Correções {#fixes-8-6-4}

Os seguintes problemas foram corrigidos nesta versão:

NEO77452, NEO81127, NEO81209, NEO80243, NEO80314, NEO81223, NEO81287, NEO81290, NEO81312, NEO81512, NEO81520, NEO81566, NEO81704, NEO83096, NEO83081.