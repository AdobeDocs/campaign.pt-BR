---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# conectar

Abre a conexão HTTP e passa o objeto para o modo &quot;keep-alive&quot;

```text
connect ( [hasProxy ] [, async ])
```

## Parâmetros

**hasProxy** Booleano como verdadeiro se você precisar usar um HTTP de proxy. Por padrão, defina como falso.

**async** Booleano definido como true se a conexão for destinada a executar uma consulta assíncrona. Definido como falso por padrão.

## Valor de retorno

Nenhum.

## Observações

Se a conexão HTTP falhar, uma exceção será gerada. A propriedade response só se torna válida após uma chamada bem-sucedida para a função execute. Não se esqueça de chamar disconnect() após terminar de usar a conexão. Exemplo:

```javascript
// Mistake with the hostname gogle instead of google
var badHttp = new HttpClientRequest("www.gogle.fr");
try {
  badHttp.connect();
} catch (e) {
  // Here an exception has been raised
}

var goodHttp = new HttpClientRequest("www.google.fr");
try {
  goodHttp.connect();
} catch (e) {
  // No exeception raised
}
...
goodHttp.disconnect();
```

## Recursos

**Método de classe:** [HttpClientRequest](c-httpclientrequest.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
