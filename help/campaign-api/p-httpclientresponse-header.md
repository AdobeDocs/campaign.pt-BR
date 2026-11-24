---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 19%
---
# cabeçalho

Um objeto que contém todos os cabeçalhos HTTP.

```text
header
```

## Observações

O nome das propriedades não diferencia maiúsculas de minúsculas. Exemplo:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
for(var i in response.header)
  logInfo("header[" + i + "] => " + response.header[i])
    
```

Para recuperar vários cabeçalhos com o mesmo nome, use a propriedade [headers](p-httpclientresponse-headers.md) em vez da propriedade de cabeçalho.

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
