---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 31%
---
# UpdateBroadLogs

Atualize o status dos logs de entrega, execute o tratamento de erros e atualize os contadores de entrega.

```text
UpdateBroadLogs ( Number deliveryId, XML logs, Boolean deliveryMustExist )
```

## Parâmetros

**deliveryId** Identificador de entrega

**logs** Coleção contendo os registros nms:broadLog a serem atualizados (@id, @status, @eventDate e @lastModified devem ser especificados)

**deliveryMustExist** Especifica se um erro deve ser gerado para um identificador de entrega inválido.

## Retornar valor(es)

Nenhum.

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
