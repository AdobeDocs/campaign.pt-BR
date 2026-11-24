---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# getElementsByTagNameNS

Retorna a lista de todos os elementos secundários com o nome especificado.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Parâmetros

**namespaceURI** O URI do namespace de elementos pesquisados.

**localName** Nome de elementos pesquisados.

## Valor de retorno

Tabela contendo a lista de elementos.

## Observações

Este método cria uma nova tabela para cada chamada. Portanto, é melhor manter a tabela em uma variável local do que fazer várias chamadas.

## Recursos

**Método de classe:** [DOMElement](c-domelement.md)

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
