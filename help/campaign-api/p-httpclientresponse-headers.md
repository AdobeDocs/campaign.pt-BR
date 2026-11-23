---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# cabeçalhos

A lista de cabeçalhos da resposta HTTP agrupados por nome.

```text
headers
```

## Observações

Cada propriedade header carregava o nome do cabeçalho e o valor da tabela que corresponde a cada cabeçalho com esse nome. Esta função é diferente do [cabeçalho](p-httpclientresponse-header.md) porque retorna uma tabela de valores em vez de um valor exclusivo para um determinado nome. Isso é útil para cabeçalhos que podem aparecer várias vezes, como Accept-Language ou Set-Cookie. A função retornará uma tabela vazia se a resposta HTTP não tiver um cabeçalho com esse nome. Exemplo:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = response
var cookies = response.headers["set-cookie"]
for each(var c in cookies)
{
  logInfo("Set-Cookie: " + c)
}
```

as propriedades dos cabeçalhos não são itemizáveis. Os nomes de propriedades não diferenciam maiúsculas de minúsculas.

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
