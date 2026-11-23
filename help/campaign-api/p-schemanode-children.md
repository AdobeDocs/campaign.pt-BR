---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# filhos

Retorna um objeto para o qual cada propriedade é um nó filho indexado por seu nome.

```text
children
```

## Observações

Exemplo:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

logInfo(root.children["@firstName"].label)
logInfo(root.children.country.label)

// root.children is a map which :
//   each key is the name of the child
//   each value the corresponding SchemaNode instance
for each(var node in root.children)
{
  logInfo(node.label + " (" + node.type + ")")
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
