---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '35'
ht-degree: 28%
---
# chaves

Retorna uma tabela com definições das chaves [SchemaKey](c-schemakey.md) do nó atual.

```text
keys
```

## Observações

Exemplo:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
  logInfo("Key: " + key.name + "\t is-internal: " + key.isInternal)
    
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
