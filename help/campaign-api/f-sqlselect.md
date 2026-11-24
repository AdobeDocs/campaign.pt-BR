---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 13%
---
# sqlSelect

Executa uma consulta SQL e retorna o resultado como um documento XML.

```text
sqlSelect (format, query [, dataSource ])
```

## Parâmetros

**format** Uma cadeia de caracteres separada com vírgulas descrevendo o formato dos dados esperados como um nome:type\[:length\] digite list docName, \[fieldXPath:type,\]\*

**consulta** A consulta SQL.

**dataSource** A fonte de dados.

## Valor de retorno

Um objeto XML que contém uma lista de elementos para cada linha do resultado da consulta.

## Observações

Exemplo:

```javascript
var res = sqlSelect("publicUrl,@sstringValue:string",
        "select sstringValue from XtkOption where sname='XtkFileRes_PublicUrl'")
logInfo(res.publicUrl.@sstringValue.toString())
```

```javascript
var xmlRes = sqlSelect("name:string,file:string:64","select relname, relfilenode from  pg_class WHERE relkind='r' AND pg_get_userbyid(relowner)<>'postgres';");
```

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
