---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 23%
---
# ArmazenarMirrorPageInfo

Adiciona informações para gerar mirror pages para um conjunto de partes de entrega.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfo ( Number deliveryId, Number partsCount, Number firstPartId, Number lastPartId )
```

## Parâmetros

**deliveryId** Identificador de entrega

**partsCount** Número de partes

**firstPartId** Identificador da primeira parte

**lastPartId** Identificador da última parte

## Retornar valor(es)

**fatalError** Retorna um código de erro que impede o chamador de executar desativações. Caso contrário, o erro pode ser temporário.

**fatalErrorMsg** Mensagem de erro associada ao código de erro &#39;fatalError&#39;.

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
