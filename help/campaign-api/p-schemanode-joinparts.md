---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 14%
---
# joinParts

Retorna uma tabela de instâncias de SchemaNode para as quais cada elemento representa uma condição da junção.

```text
joinParts
```

## Observações

Cada elemento na tabela tem duas propriedades:

* source - O elemento que representa o campo da tabela de origem.
* target - O elemento que representa o campo da tabela de destino.

Exemplo:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

var link = root.children.country
for each(var join in link.joinParts)
{
  logInfo("src = " + join.source.name)
  logInfo("dst = " + join.destination.name)
}
```

## Recursos

**Propriedade da classe:** [SchemaNode](c-schemanode.md)

**Somente leitura:**

Sim

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
