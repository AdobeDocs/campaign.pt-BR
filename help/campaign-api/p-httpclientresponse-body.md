---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 12%
---
# corpo

O corpo da resposta HTTP na forma de um objeto MemoryBuffer.

```text
body
```

## Observações

A codificação do corpo da resposta é acessível por meio da propriedade [codePage](p-httpclientresponse-codepage.md). O corpo da resposta HTTP é fornecido na forma de um objeto [MemoryBuffer](c-memorybuffer.md). Todos os métodos aplicáveis a um [MemoryBuffer](c-memorybuffer.md) são, portanto, aplicáveis ao corpo da resposta HTTP. Exemplo:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
if( response.code != 200 )
  throw "HTTP request failed with " + response.message
var content = response.body.toString(response.codePage)
```

## Recursos

**Propriedade da classe:** [HttpClientResponse](c-httpclientresponse.md)

**Somente leitura:**

Sim

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
