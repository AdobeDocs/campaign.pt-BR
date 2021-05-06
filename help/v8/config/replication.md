---
solution: Campaign Classic
product: campaign
title: Workflows técnicos e replicação de dados
description: Workflows técnicos e replicação de dados
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: a67c83eb531c795d621fdf36696ae4bde2151dba
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---

# Workflows técnicos e replicação de dados

## Workflows técnicos 

O Adobe Campaign vem com um conjunto de fluxos de trabalho técnicos incorporados. Os workflows técnicos executam processos ou tarefas agendados regularmente no servidor.

Esses workflows executam operações de manutenção no banco de dados, aproveitam as informações de rastreamento nos logs do delivery, criam campanhas recorrentes e muito mais.

:seta_upper_right: A lista completa de workflows técnicos é detalhada em [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Além desses workflows técnicos, o Campaign v8 depende de workflows técnicos específicos para gerenciar [replicação de dados](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Esse workflow executa a replicação automática de tabelas de referência que precisam estar presentes no banco de dados local do Campaign (Postgres) e no banco de dados do Cloud ([!DNL Snowflake]). Ele é agendado para ser executado a cada hora, diariamente. Se o campo **lastModified** existir, a replicação ocorrerá de forma incremental, caso contrário, toda a tabela será replicada. A ordem das tabelas na matriz abaixo é a ordem usada pelo workflow de replicação.
* **[!UICONTROL Replicate Staging data]**
Esse workflow replica dados de preparo para chamadas unitárias. Ele é agendado para ser executado a cada hora, diariamente.
* **[!UICONTROL Deploy FFDA immediately]**\
   Esse workflow executa uma implantação imediata no banco de dados do Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Esse workflow replica os dados XS para uma determinada conta externa.

Esses workflows técnicos estão disponíveis no nó **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** do explorador do Campaign.

## Replicação de dados{#data-replication}

As tabelas são replicadas do banco de dados do Campaign para [!DNL Snowflake] o banco de dados da nuvem por meio de workflows dedicados descritos acima.

As políticas de replicação são baseadas no tamanho da tabela. Algumas tabelas serão replicadas. Algumas tabelas serão replicadas em tempo real, e outras serão replicadas a cada hora. Algumas tabelas terão atualizações incrementais quando outras forem substituídas.

| Namespace | Tabela | replicação de workflow | Replicação em tempo real |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | --------------------- |
| XTK | xtk:enum<br>xtk:enumValue<br>xtk:enumAlias<br>xtk:folder<br>xtk:formRendering<br>xtk:operator<br>xtk:group<br>xtk:report<br>xtk:olapCube<br>xtk:olapDimension<br>xtk:olapMeasure<br>xtk:dictionaryString<br> | Sim (incremental) | Sim |
| XTK | xtk:opsecurity<br>xtk:rights<br>xtk:operatorGroup<br>xtk:reportHistory<br>xtk:reportRights | Sim (completo) | Sim |
| NMS | nms:budget<br>nms:program<br>nms:operation<br>nms:plan<br>nms:typologyRule<br>nms:typology<br>nms:extAccount<br>nms:deliveryMapping<br>nms:delivery (replicação imediata)<br>nms:nms Membro<br>nms:webApp<br>nms:trackingUrl (replicação imediata)<br>nms:service<br>nms:offerEnv<br>nms:offerCategory<br>nms:offerSpace<br>nms:offer a16/>nms:offerView<br>nms:recipient (incremental?)<br><br>nms:<br>groupnms:<br>dlvExclusionnms:stock | Sim (incremental) | Sim |
| NMS | nms:country<br>nms:localOrgUnit<br>nms:state<br>nms:suppressionAddress<br>nms:suppressionDomain<br>nms:category<br>nms:trackingUrlInfo<br>nms:webTrackingLog<br>nms:mobileApp a8/>nms:budgetCategory<br>nms:costType<br>nms:costCenter<br>nms:costStructure<br>nms:stockLine<br>nms:costLine<br>nms:costLine<br> | Sim (completo) | Sim |
| NMS | nms:address<br>nms:userAgent<br>nms:userAgentReject<br>nms:userAgentStats<br>nms:broadLogMsg<br>nms:broadLog<br>nms:trackingLog<br>nms:deliveryLogStats<br>nms ms:appSubscription<br>nms:proposition<br>nms:rcpGrpRel<br>nms:broadLogRcp<br>nms:excludeLogRcp<br>nms:trackingLogRcp<br>nms:proms positionRcp<br>nms:localValidationRcp<br>nms:visitor<br>nms:broadLogVisitor<br>nms:trackingLogVisitor<br>nms:propositionVisitor<br>nms:webApp LogRcp<br>nms:appSubscriptionRcp<br>nms:broadLogAppSubRcp<br>nms:excludeLogAppSubRcp<br>nms:trackingLogAppSubRcp<br>nms nms:eventHisto<br>nms:broadLogEventHisto<br>nms:trackingLogEventHisto<br>nms:subscription<br>nms:subHisto<br>nms:trackingStats (apenas uso de Snowflake)<br>nms:tmpBroadcast (uso somente de Snowflake)<br>nms:tmpBroadcastExclusion (uso somente de Snowflake)<br>nms:tmpBroadcastPaper (uso somente de Snowflake) | Não | Não |

**Tópicos relacionados**

:seta_upper_right: Saiba como começar a usar workflows na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

:bulb: Acesse os períodos de retenção de dados em [nesta seção](../dev/datamodel-best-practices.md#data-retention)
