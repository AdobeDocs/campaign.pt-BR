---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%
---
# getElements

Retorna a lista de elementos filho com o nome especificado, pertencente a este elemento.

```text
getElements ( [tagName ])
```

## Parâmetros

**tagName** Nome de elementos pesquisados. Se esse parâmetro for omitido, a função retornará todos os elementos secundários.

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
