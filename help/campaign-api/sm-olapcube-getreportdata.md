---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%
---
# GetReportData

```text
XML result = GetReportData ( Number cubeId, String queryDef, Boolean selectAll, Boolean useAggregates, XML cube )
```

## Parâmetros

Identificador de cubo **cubeId**. Pode ser definido como 0 se o cubo for passado como um parâmetro.

**queryDef** QueryDef definido no relatório

**selecionarTudo** Selecionar tudo

**useAggregates** Habilitar uso agregado

XML **cubo** descrevendo o cubo.

## Retornar valor(es)

Resultado **resultado**

## Recursos

**Esquema:** [xtk:olapCube](s-xtk-olapcube.md)

**Estático:**

Sim
