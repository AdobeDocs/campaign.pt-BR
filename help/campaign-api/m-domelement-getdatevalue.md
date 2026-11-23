---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 14%
---
# getDateValue

Retorna o valor do tipo date+hour da referência do nó pelo XPath fornecido.

```text
getDateValue (xpath)
```

## Parâmetros

Caminho **xpath**.

## Valor de retorno

Um objeto do tipo Date que corresponde ao valor do nó referenciado.

## Observações

A sintaxe do XPath aceita apenas um subconjunto de idioma XPath. Uma exceção será gerada se o caminho estiver mal formado ou se o valor não for uma data válida.

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
