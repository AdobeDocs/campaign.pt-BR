---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# SubmitMidSourcing

Enviar uma entrega no modo mid-sourcing.

```text
[ Number remoteId, Number remoteMatchId ] = SubmitMidSourcing ( XML delivery, XML routingMatch, String folderName )
```

## Parâmetros

Documento **delivery** que representa a entrega.

**routingMatch** não é mais usado

**folderName** Nome completo da pasta (no banco de dados do remetente).

## Retornar valor(es)

**remoteId** Identificador da entrega no banco de dados do destinatário.

**remoteMatchId** não é mais usado

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
