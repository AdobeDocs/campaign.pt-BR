---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 33%
---
# GetTrackingInfo

Permite que um servidor de redirecionamento remoto baixe informações sobre uma ação de entrega.

```text
XML document = GetTrackingInfo ( String instance, String dbId, String deliveryId )
```

## Parâmetros

Nome da instância de **instância**

**dbId** Identificador do banco de dados do cliente que está executando uma entrega

**deliveryId** ID de Entrega.

## Retornar valor(es)

**documento** Documento contendo as informações de rastreamento para esta entrega

## Recursos

**Esquema:** [nms:remoteTracking](s-nms-remotetracking.md)

**Estático:**

Sim
