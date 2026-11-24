---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 14%
---
# cabeçalho

Um objeto JavaScript que contém os cabeçalhos HTTP do cabeçalho.

```text
header
```

## Observações

Todas as propriedades do objeto de cabeçalho podem ser acessadas no modo de leitura/gravação e são enumeráveis. Cada proprietário do objeto de cabeçalho é uma entrada no cabeçalho HTTP da query. Os nomes de propriedades não fazem distinção entre maiúsculas e minúsculas (como no caso de cabeçalhos HTTP). Exemplo:

```javascript
var http = new HttpClientRequest(url)

var buffer = new MemoryBuffer()
buffer.fromString(userName + ':' + password, "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"
http.header["Date"] = (new Date()).toGMTString()
//Note: http.header.Date == http.header.date

for( var i in http.header )
logInfo("header[" + i + "] => " + http.header[i])
```

## Recursos

**Propriedade da classe:** [HttpClientRequest](c-httpclientrequest.md)

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
