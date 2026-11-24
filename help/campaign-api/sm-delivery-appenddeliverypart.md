---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 13%
---
# AppendDeliveryPart

Adicione uma parte a uma entrega que está sendo preparada.

```text
[ Number deliveryPartId, Number fatalError, String fatalErrorMsg ] = AppendDeliveryPart ( XML deliveryPart, Boolean retry )
```

## Parâmetros

**deliveryPart** Documento que representa a parte da entrega (ou uma coleção de partes da entrega).

**tentativa** Especifica se esta é uma nova tentativa de enviar esta parte da entrega.

## Retornar valor(es)

**deliveryPartId** Identificador da parte de entrega no banco de dados (quando não é uma coleção).

**fatalError** Retorna um código de erro que impede o chamador de executar desativações. Caso contrário, o erro pode ser temporário.

**fatalErrorMsg** Mensagem de erro associada ao código de erro &#39;fatalError&#39;.

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
