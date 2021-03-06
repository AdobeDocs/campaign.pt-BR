---
title: Workflows técnicos e replicação de dados
description: Workflows técnicos e replicação de dados
feature: Workflows
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 3%

---

# Workflows técnicos e replicação de dados

## Workflows técnicos{#tech-wf}

No contexto de um [Implantação empresarial (FDA)](enterprise-deployment.md), o Adobe Campaign vem com um conjunto de fluxos de trabalho técnicos incorporados. Os workflows técnicos executam processos ou tarefas agendados regularmente no servidor.

Esses workflows executam operações de manutenção no banco de dados, aproveitam as informações de rastreamento nos logs do delivery, criam campanhas recorrentes e muito mais.

![](../assets/do-not-localize/glass.png) A lista completa de workflows técnicos é detalhada em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html).

Além desses workflows técnicos, o Campaign v8 depende de workflows técnicos específicos para gerenciar [replicação de dados](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Esse workflow executa a replicação automática de tabelas incorporadas que precisam estar presentes no banco de dados local do Campaign (Postgres) e no banco de dados do Cloud ([!DNL Snowflake]). Ele é agendado para ser executado a cada hora, diariamente. If **lastModified** existe, a replicação acontece de forma incremental, caso contrário, toda a tabela é replicada. A ordem das tabelas na matriz abaixo é a ordem usada pelo workflow de replicação.
* **[!UICONTROL Replicate Staging data]**
Esse workflow replica dados de preparo para chamadas unitárias. Ele é agendado para ser executado a cada hora, diariamente.
* **[!UICONTROL Deploy FFDA immediately]**\
   Esse workflow executa uma implantação imediata no banco de dados do Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Esse workflow replica os dados XS para uma determinada conta externa.

Esses workflows técnicos estão disponíveis na **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** nó do explorador do Campaign. **Eles não devem ser modificados.**

Se necessário, é possível iniciar a sincronização de dados manualmente. Para fazer isso, clique com o botão direito do mouse no botão **Scheduler** e selecione **Execute pending task(s) now**.

## Replicação de dados{#data-replication}

Algumas tabelas incorporadas são replicadas do banco de dados local do Campaign para [!DNL Snowflake] Banco de dados da nuvem por meio de workflows dedicados descritos acima.

Entenda quais bancos de dados o Adobe Campaign v8 usa, por que os dados estão sendo replicados, quais dados estão sendo replicados e como o processo de replicação funciona.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Políticas de replicação de dados{#data-replication-policies}

As políticas de replicação são baseadas no tamanho das tabelas. Algumas tabelas serão replicadas em tempo real, outras serão replicadas a cada hora. Algumas tabelas terão atualizações incrementais quando outras forem substituídas.

Além do **Replicar tabelas de referência** do workflow técnico, você pode forçar a replicação de dados em seus workflows.

Você pode:

* adicione um **Código JavaScript** atividade com o seguinte código:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* adicione um **nlmodule** atividade com o seguinte comando:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**Tópicos relacionados**

* [Saiba como começar a usar workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)

* [Períodos de retenção de dados](../dev/datamodel-best-practices.md#data-retention)
