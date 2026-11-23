---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 26%
---
# ComandoExec

Executa um comando em uma entrega.

```text
Number newState = ExecCommand ( String deliveryId, String command )
```

## Parâmetros

**deliveryId** Identificador de entrega

**comando** Nome do comando (&#39;play&#39;, &#39;pause&#39; ou &#39;stop&#39;)

## Retornar valor(es)

**newState** Status da entrega após a execução do comando

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
