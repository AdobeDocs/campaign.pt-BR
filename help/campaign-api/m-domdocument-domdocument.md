---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 33%
---
# Documento DOM

Cria um novo documento.

```text
DOMDocument (name [, namespaceURI ])
```

## Parâmetros

**nome** Nome do documento.

**namespaceURI** URI do namespace do documento.

## Valor de retorno

Nenhum.

## Observações

Exemplo:

```javascript
var doc = new DOMDocument("test")
var doc2 = new DOMDocument("html", "http://www.w3.org/1999/xhtml")
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
