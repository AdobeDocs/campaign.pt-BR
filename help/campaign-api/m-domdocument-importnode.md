---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 25%
---
# importNode

Cria uma cópia de nó de outro documento.

```text
importNode (importedNode, deep)
```

## Parâmetros

Nó Source **importedNode**.

**deep** true se o nó completo tiver que ser copiado, caso contrário, false.

## Valor de retorno

Cópia do nó.

## Observações

Exemplo:

```javascript
var result = doc.importNode(rcpResult, true);
doc.root.appendChild(result);
```

## Recursos

**Método de classe:** [DOMDocument](c-domdocument.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Mensagem de entrega
* Regra de tipologia
* Importação
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
