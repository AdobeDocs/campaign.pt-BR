---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 14%
---
# getElementsByTagNameNS

Retorna a lista de todos os elementos do documento com o nome e o namespace especificados.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Parâmetros

**URI do namespace** URI do namespace.

**localName** Nome de elementos pesquisados.

## Valor de retorno

Tabela contendo a lista de elementos.

## Observações

Este método cria uma nova tabela para cada chamada. Portanto, é melhor manter a tabela em uma variável local do que fazer várias chamadas.

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
