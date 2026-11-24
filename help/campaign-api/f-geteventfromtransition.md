---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 6%
---
# getEventFromTransition

Retorna o último evento a passar por uma determinada transição.

```text
getEventFromTransition (transitionName)
```

## Parâmetros

**transitionName** O nome interno da transição.

## Valor de retorno

O último evento a ter passado por determinada transição ou nulo. O objeto corresponde a uma entidade no esquema &quot;xtk:workflowEvent&quot;.

## Recursos

**Disponível em:**

* Fluxo de trabalho
