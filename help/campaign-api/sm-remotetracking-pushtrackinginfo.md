---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# PushTrackingInfo

Permite fazer o upload de todas as informações relativas a uma entrega para o servidor de rastreamento remoto.

```text
PushTrackingInfo ( String instance, String dbId, String jobId, XML document )
```

## Parâmetros

Nome da instância de **instância**

**dbId** Identificador do banco de dados do cliente que está executando uma entrega

ID de Entrega do **jobId**.

**documento** Documento contendo as informações de rastreamento para esta entrega

## Retornar valor(es)

Nenhum.

## Recursos

**Esquema:** [nms:remoteTracking](s-nms-remotetracking.md)

**Estático:**

Sim
