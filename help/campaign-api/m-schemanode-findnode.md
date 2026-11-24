---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%
---
# findNode

Retorna uma instância de [SchemaNode](c-schemanode.md) ou nulo se o nó não existir e o parâmetro mustExist estiver definido como falso.

```text
findNode (name [, strict ] [, mustExist ])
```

## Parâmetros

XPath **name** representa o nome do nó a ser pesquisado

**strict** Booleano que indica se (estrito a falso) ou não, quando o nome do último item no caminho não existe como está, ele deve ser pesquisado como um atributo ou um elemento. Por padrão, verdadeiro.

**mustExist** Booleano que indica se uma exceção deve ser gerada se o nó não existir. true por padrão.

## Valor de retorno

Retorna uma instância [SchemaNode](c-schemanode.md) se o nó puder ser encontrado, ou nulo se o parâmetro mustExist estiver definido como falso.

## Observações

Exemplo:

```javascript
var schema = application.getSchema("nms:recipient");

logInfo("netSales: " + schema.root.findNode("@netSales"));
logInfo("merchandise/@lastPurchaseDate: " + schema.root.findNode("merchandise/@lastPurchaseDate", true, false));
```

Resultado:

```javascript
netSales: [object NodeDef]
merchandise/@lastPurchaseDate: [object NodeDef]
```

## Recursos

**Método de classe:** [SchemaNode](c-schemanode.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
