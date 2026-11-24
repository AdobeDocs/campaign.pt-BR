---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 16%
---
# getNumberValue

Retorna o valor do nó digital referenciado pelo XPath fornecido.

```text
getNumberValue (xpath)
```

## Parâmetros

Caminho **xpath**.

## Valor de retorno

O valor digital corresponde ao nó referenciado.

## Observações

A sintaxe do XPath aceita apenas um subconjunto de idioma XPath. Uma exceção será gerada se o caminho estiver mal formado ou se o valor não for um número válido.

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
