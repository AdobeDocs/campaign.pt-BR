---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%
---
# SetResolved

Declara uma entidade como não tendo mais conflitos.

```text
SetResolved ( String conflictId )
```

## Parâmetros

**conflictId** Identificador de conflito.

## Retornar valor(es)

Nenhum.

## Observações

Quando todos os conflitos são resolvidos, esse método permite que você coloque a entidade de volta em seu lugar normal. Todos os atributos e elementos conflitantes devem ser resolvidos antes de chamar esse método.

## Recursos

**Esquema:** [xtk:conflict](s-xtk-conflict.md)

**Estático:**

Sim
