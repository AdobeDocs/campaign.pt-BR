---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 20%
---
# fromXMLString

Cria um novo documento a partir de uma cadeia de caracteres XML.

```text
fromXMLString (string)
```

## Parâmetros

**cadeia** Cadeia de caracteres XML.

## Valor de retorno

Nenhum.

## Observações

Uma exceção será gerada se o argumento não for um documento XML válido. Essa função se aplica à classe DOMDocument. Exemplo:

```javascript
var doc = DOMDocument.fromXMLString(
    '<?xml version="1.0" encoding="ISO-8859-1"?>' +
    '<form name="address" namespace="nms" colcount="2"/>')
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
