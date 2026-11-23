---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# GetMidBroadLogs

Recupere os logs de entrega modificados por último no modo de mid-sourcing.

```text
[ XML result, Date nextDate ] = GetMidBroadLogs ( Date startDate, Number logCount, Date emitterDate )
```

## Parâmetros

**startDate** Recupere logs modificados desde esta data (no servidor mid-sourcing).

**logCount** Número máximo de logs a serem recuperados, desde que não tenham sido atualizados no mesmo segundo.

**emitterDate** Data de referência do servidor emissor. Usado para ajustar as datas do log de delivery.

## Retornar valor(es)

**resultado** Documento de saída, lista de logs de entrega.

**nextDate** Data do primeiro log recuperado (maior que startDate).

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
