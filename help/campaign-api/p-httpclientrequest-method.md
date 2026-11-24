---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 21%
---
# método

O método HTTP, no formato de uma cadeia de caracteres

```text
method
```

## Observações

O valor dessa propriedade é alterado sistematicamente para maiúsculas. Exemplo:

```javascript
var http = new HttpClientRequest(url)
http.method = "SEARCH"
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
