---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 82622a4517356eaba1f7eba23d4b3050d8ca37c9
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 25%

---

# Versões mais recentes {#latest-release}

Esta página lista novos recursos, melhorias e correções que vêm com o Campaign v8 (console) **versões mais recentes**. Saiba mais sobre lançamentos, versões e atualizações do Campaign em [esta página](upgrades.md). Outras versões estão listadas na seção Versões anteriores desta documentação.

>[!BEGINSHADEBOX]

**Nesta página**

* Campaign v8.6 - [Versão 8.6.4](#release-8-6-4)
* Campaign v8.7 - [Versão 8.7.3](#release-8-7-3)

>[!ENDSHADEBOX]


## Versão 8.7.3 {#release-8-7-3}

_5 de fevereiro de 2025_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa transição na [documentação da interface da web do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Novos recursos {#features-8-7-3}

* **Dynamic Reporting para mensagens transacionais** - Agora é possível monitorar as mensagens transacionais na interface do usuário do Dynamic Reporting. Esses relatórios oferecem ao profissional de marketing a capacidade de visualizar em tempo real todas as métricas e dimensões de relatórios das mensagens transacionais e o detalhamento das entregas enviadas por meio de um modelo. [Saiba mais](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **REST APIs de mensagens transacionais** - As APIs transacionais baseadas em eventos agora estão disponíveis para emails. [Saiba mais](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### Correções {#fixes-8-7-3}

Os seguintes problemas foram corrigidos nesta versão:

NEO79373, NEO81908, NEO83081.


## Versão 8.6.4 {#release-8-6-4}

_15 de janeiro de 2025_

### Melhorias gerais {#improvements-8-6-4}

* A estabilidade do aplicativo do Campaign foi aprimorada durante a análise de entrega no contexto de uma [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Essa versão vem com mecanismos de arquitetura FFDA aprimorados e fortalecidos, incluindo gerenciamento de chaves, armazenamento temporário e replicação de dados.
* Novos fluxos de trabalho técnicos foram introduzidos para a [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md). Esses workflows replicam o delivery e dados relacionados centralizando solicitações de replicação paralela em tabelas correspondentes. Estes fluxos de trabalho começam com `Replicate nms`. [Leia mais](../architecture/replication.md)
* Uma nova opção **Habilitar supervisor de watchdog para manter o fluxo de trabalho em execução permanentemente** agora está disponível nas propriedades do fluxo de trabalho. Quando essa opção está habilitada, os workflows são reiniciados automaticamente após um erro. A reinicialização ocorre a cada 30 segundos por padrão se o workflow ainda estiver com erro. Para ajustar esse intervalo, você pode criar uma nova opção `XtkWorkflow_WatchdogTimerTimeout` e definir um tipo de dados Integer para especificar o novo atraso. Essa opção só deve ser habilitada em workflows técnicos. [Leia mais](../../automation/workflow/workflow-properties.md#execution)

### Melhorias de segurança {#security-8-6-4}

A conexão com soluções e aplicativos da Adobe por meio da conta externa **[!UICONTROL Adobe Experience Cloud]** foi atualizada para reforçar a segurança.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Atualizações de compatibilidade {#comp-8-6-4}

Os databricks agora são compatíveis como um banco de dados externo com o Federated Data Access (FDA) do Adobe Campaign. Saiba mais [nesta página](compatibility-matrix.md#FederatedDataAccessFDA).

### Correções {#fixes-8-6-4}

Os seguintes problemas foram corrigidos nesta versão:

NEO48232, NEO67814, NEO71388, NEO74855, NEO75643, NEO75962, NEO76132, NEO76958, NEO76986, NEO77162, NEO77452, NEO78946, NEO79373, NEO80243, NEO80314, NEO81127, NEO81209, NEO81223, NEO81287, NEO81290, NEO8133 NEO81512, NEO81520, NEO81566, NEO81704, NEO81908, NEO82195, NEO82591, NEO82592, NEO82640, NEO82665, NEO8277 NEO82920, NEO83081, NEO83096, NEO83137, NEO83143.

