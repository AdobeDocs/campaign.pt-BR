---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 12%
---
# getBooleanValue

Retorna o valor do nó booleano referenciado pelo XPath fornecido.

```text
getBooleanValue (xpath)
```

## Parâmetros

Caminho **xpath**.

## Valor de retorno

true se o valor de texto do nó referenciado for &#39;true&#39; ou &#39;1&#39;, false será o valor &#39;false&#39; ou &#39;0&#39;.

## Observações

A sintaxe do XPath aceita apenas um subconjunto de idioma XPath. O teste de valor não diferencia maiúsculas de minúsculas. Uma exceção será gerada se o caminho estiver mal formado ou se o valor não for um booleano válido.

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
