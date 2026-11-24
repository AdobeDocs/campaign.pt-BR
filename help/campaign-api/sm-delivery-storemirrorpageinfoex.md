---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 22%
---
# ArmazenarMirrorPageInfoEx

Adiciona informações para gerar mirror pages para um conjunto de partes de entrega.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfoEx ( Number deliveryId, Boolean notification, Number partsCount, Number firstPartId, Number notificationId )
```

## Parâmetros

**deliveryId** Identificador de entrega

**notificação** É uma notificação?

**partsCount** Número de partes

**firstPartId** Identificador da primeira parte

Identificador de notificação **notificationId**

## Retornar valor(es)

**fatalError** Retorna um código de erro que impede o chamador de executar desativações. Caso contrário, o erro pode ser temporário.

**fatalErrorMsg** Mensagem de erro associada ao código de erro &#39;fatalError&#39;.

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
