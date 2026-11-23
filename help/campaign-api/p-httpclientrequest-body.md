---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%
---
# corpo

O corpo da consulta HTTP.

```text
body
```

## Observações

O objeto atribuído ao corpo da query é processado da seguinte maneira:

* undefined, null, function: não são considerados elementos enviáveis, o corpo da consulta HTTP está vazio.
* number, boolean, string, XML, Object: alterado para uma string de caracteres com base no método toString e codificado com base no tipo de conteúdo do cabeçalho HTTP.
* [MemoryBuffer](c-memorybuffer.md): o conteúdo é copiado no corpo da consulta sem alteração.

Exemplo:

```javascript
var query = "Select \"urn:schemas:calendar:uid\" " // etc...
var apptRequest =
  "<g:searchrequest xmlns:g="DAV:">\n" +
  "  <g:sql>\n" +
        query +
  "  </g:sql>\n" +
  "</g:searchrequest>"
http.body = apptRequest
    
```

## Recursos

**Propriedade da classe:** [HttpClientRequest](c-httpclientrequest.md)

**Somente leitura:**

Não

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
