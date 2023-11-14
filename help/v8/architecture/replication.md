---
title: Workflows técnicos e replicação de dados
description: Workflows técnicos e replicação de dados
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: f807963a7640773ac18d49999b561f2f3b894d7f
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 5%

---

# Workflows técnicos e replicação de dados {#wf-data-replication}

## Workflows técnicos {#tech-wf}

No contexto de um [Implantação corporativa (FFDA)](enterprise-deployment.md), o Adobe Campaign vem com um conjunto de fluxos de trabalho técnicos incorporados. Os workflows técnicos executam processos ou trabalhos, agendados regularmente no servidor.

Esses workflows executam operações de manutenção no banco de dados, aproveitam as informações de rastreamento nos logs do delivery, criam campanhas recorrentes e muito mais.

![](../assets/do-not-localize/glass.png) A lista completa de workflows técnicos é detalhada em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html).

Além desses workflows técnicos, o Campaign v8 depende de workflows técnicos específicos para gerenciar [replicação de dados](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Esse workflow executa a replicação automática de tabelas integradas que precisam estar presentes no banco de dados local do Campaign (Postgres) e no banco de dados da nuvem ([!DNL Snowflake]). Ele é programado para ser executado a cada hora, diariamente. Se **lastModified** existir, a replicação ocorrerá de forma incremental, caso contrário, a tabela inteira será replicada. A ordem das tabelas no array abaixo é a ordem usada pelo workflow de replicação.
* **[!UICONTROL Replicate Staging data]**
Esse fluxo de trabalho replica dados de preparo para chamadas unitárias. Ele é programado para ser executado a cada hora, diariamente.
* **[!UICONTROL Deploy FFDA immediately]**\
  Este fluxo de trabalho executa uma implantação imediata no banco de dados em nuvem.
* **[!UICONTROL Replicate FFDA data immediately]**
Esse workflow replica os dados XS para uma determinada conta externa.

Esses workflows técnicos estão disponíveis no **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** nó do Campaign Explorer. **Eles não devem ser modificados.**

Se necessário, é possível iniciar a sincronização de dados manualmente. Para fazer isso, clique com o botão direito do mouse na **Scheduler** atividade e selecione **Executar tarefas pendentes agora**.

## Replicação de dados {#data-replication}

Algumas tabelas integradas são replicadas do banco de dados local do Campaign para [!DNL Snowflake] banco de dados em nuvem por meio de fluxos de trabalho dedicados descritos acima.

Entenda quais bancos de dados o Adobe Campaign v8 usa, por que os dados estão sendo replicados, quais dados estão sendo replicados e como o processo de replicação funciona.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Políticas de replicação de dados {#data-replication-policies}

As políticas de replicação são baseadas no tamanho das tabelas. Algumas tabelas são replicadas em tempo real, outras são replicadas de hora em hora. Algumas tabelas terão atualizações incrementais quando outras serão substituídas.

Além do incorporado **Replicar tabelas de referência** fluxo de trabalho técnico, é possível forçar a replicação de dados em seus fluxos de trabalho.

Você pode:

* adicionar um **Código Javascript** atividade com o seguinte código:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* adicionar um **nlmodule** atividade com o seguinte comando:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**Tópicos relacionados**

* [Saiba como começar a usar workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=pt-BR)

* [Períodos de retenção de dados](../dev/datamodel-best-practices.md#data-retention)
