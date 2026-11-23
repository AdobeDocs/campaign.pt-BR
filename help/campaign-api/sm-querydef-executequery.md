---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 36%
---
# ExecuteQuery

Recuperar dados de uma consulta

```text
XML output = queryDef.ExecuteQuery () const
```

## Parâmetros

Nenhum.

## Retornar valor(es)

**saída** Documento XML de saída

## Observações

A consulta aceita quatro tipos de operações:

* selecionar
* obter
* getIfExists
* count

## Exemplo

```javascript
var query = NLWS.xtkQueryDef.create(
  {queryDef: {schema: "xtk:workflow", operation: "select", 
    select: {
        node: [{expr: "@id"},
               {expr: "@label"},
               {expr: "@internalName"}] 
    }, 
    where: {
      condition: [{expr: "[folder/@name]='nmsTechnicalWorkflow'"},
                  {expr: "@production = 1"}]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }})

var res = query.ExecuteQuery()

var workflows = res.getElementsByTagName("workflow")
for each (var w in workflows)
  logInfo(w.getAttribute("internalName"))
        
```

## Recursos

**Esquema:** [xtk:queryDef](s-xtk-querydef.md)

**Estático:**

Não

**Const:**

Sim

**Somente chave:**

Não
