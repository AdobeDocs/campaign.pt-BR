---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 51%
---
# GetServerFileName

Retorna o nome do arquivo no servidor para a pasta de upload após copiá-lo, se necessário.

```text
String serverFileName = fileRes.GetServerFileName ()
```

## Parâmetros

Nenhum.

## Retornar valor(es)

**serverFileName** Nome completo do arquivo no servidor (vazio se o arquivo não for encontrado).

## Exemplo

```javascript
var query = xtk.queryDef.create(
  {queryDef: {schema: "xtk:fileRes", operation: "get", 
    select: {
      node: [
      {expr: "@label"}, 
      {expr: "@originalName"}, 
      {expr: "@storageType"}, 
      {expr: "@fileName"}, 
      {expr: "@md5"}]
    }, 
    where: {
      condition: {expr: "@id = 4216"}
    }
  }})

var fileRes = xtk.fileRes.create(query.ExecuteQuery())
var sFileName = fileRes.GetServerFileName();
        
```

## Recursos

**Esquema:** [xtk:fileRes](s-xtk-fileres.md)

**Estático:**

Não

**Const:**

Não

**Somente chave:**

Não
