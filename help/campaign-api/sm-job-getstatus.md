---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 4%
---
# GetStatus

Obter informações sobre o progresso do processamento do trabalho. Aviso: essa API não garante o retorno de uma lista de entradas de log exclusivas (o chamador precisa desduplicá-las usando a ID ).

```text
[ Number status, XML returnLogs, XML properties ] = GetStatus ( String id, Number lastLogId, Number maxLogCount )
```

## Parâmetros

**id** Identificador do trabalho

**lastLogId** Identificador da última entrada do log retornado na chamada anterior

**maxLogCount** Número máximo de entradas de log a serem enviadas

## Retornar valor(es)

**status** Status do trabalho

**returnLogs** Registrar mensagens

Propriedades de **propriedades** (progresso...)

## Recursos

**Esquema:** [xtk:job](s-xtk-job.md)

**Estático:**

Sim
