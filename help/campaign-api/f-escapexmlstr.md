---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 27%
---
# escapeXmlStr

Converte uma cadeia de caracteres em formato XML.

```text
escapeXmlStr (value)
```

## Parâmetros

Cadeia de caracteres **value** a ser convertida.

## Valor de retorno

A sequência de caracteres após a conversão.

## Observações

A função transforma os caracteres &amp;, &lt;, > e \\&quot; nas sequências de escape correspondentes:

* &amp; amp;
* &lt; &lt;
* > >
* &quot; &amp;quot;

## Recursos

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
