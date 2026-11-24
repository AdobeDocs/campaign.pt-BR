---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 33%
---
# GetDlStatusAndLogs

Recuperar os últimos logs do journal e do status de entrega.

```text
[ Number deliveryState, XML returnLogs ] = GetDlStatusAndLogs ( Number deliveryId, Number lastLogId )
```

## Parâmetros

**deliveryId** Identificador de entrega

**lastLogId** Identificador da última entrada do diário retornada na chamada anterior

## Retornar valor(es)

**deliveryState** Status da entrega

**returnLogs** Registrar mensagens

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
