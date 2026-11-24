---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 12%
---
# isEqualNode

Compara dois nós.

```text
isEqualNode (arg)
```

## Parâmetros

**arg** O segundo nó.

## Valor de retorno

true se os dois nós forem iguais; caso contrário, false.

## Observações

Dois nós são iguais se as seguintes condições forem verificadas:

* Os dois nós são do tipo.
* As propriedades nodeName, localName, namespaceURI, prefix e nodeValue devem ser idênticas.
* Os dois nós são do tipo.
* Os atributos devem ser iguais.
* Os nós devem ser iguais.

Como a normalização pode afetar a igualdade, recomendamos que você normalize antes de comparar.

## Recursos

**Método da classe:** [DOMNode](c-domnode.md)

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
