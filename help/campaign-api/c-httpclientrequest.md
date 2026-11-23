---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 4%
---
# HttpClientRequest (Classe)

Um objeto HttpClientRequest permite executar determinadas operações como um cliente HTTP.

Exemplo:

```text
var req = new HttpClientRequest("http://www.somewhere.com/login") var buffer = new MemoryBuffer() buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1") req.header["Authorization"] = "Basic " + buffer.toBase64() req.header["Content-Type"] = "text/xml; charset=utf-8" req.method = "SEARCH" req.body = "<xml>any content</xml>" req.execute()
```

## &quot;Keep Alive&quot;

O objeto pode ser usado em dois modos diferentes: padrão ou keep alive. O modo padrão permite enviar uma única consulta, o modo keep-alive permite enviar várias consultas enquanto mantém a conexão aberta. O status do objeto depende da sequência de uso do método. Se o método connect() for chamado, o objeto alternará para o modo &quot;keep alive&quot; (manter ativo). Exemplo

```text
var req = new HttpClientRequest("http://evc-cit.info/cgi-bin/cit042/timeofday.cgi") req.connect() // Now the object is in keep-alive mode, we can sand many requests using // the same connection // Request ten times the time of the cgi var i = 0 while ( i < 10 ) { req.execute() var response = req.reponse i++ } req.disconnect()
```

## Consultas assíncronas

As consultas são executadas no modo de bloqueio por padrão, o que significa que o

[executar](m-httpclientrequest-execute.md)

A função só retornará o controle depois que a consulta for enviada e a resposta recebida. Também é possível executar consultas no modo assíncrono. Neste caso, o

[executar](m-httpclientrequest-execute.md)

A função retorna o controle imediatamente e uma função será chamada assim que a resposta for recebida. Isso permite a execução simultânea de várias consultas. O programa a seguir é um exemplo completo que mostra como executar uma série de uploads HTTP, abrindo 3 conexões ao mesmo tempo, em que cada upload é iniciado após a conclusão do último.

```text
var list = [ "http://www.adobe.com/", "http://www.google.com/", "http://www.mozilla.org/", "http://www.linux.org/", "http://www.postgresql.org/"] var requests = [] var complete = function(req, context, status) { if( status == "success" ) logInfo("Receiving " + context + ": " + req.url + ": code = " + req.response.code) else logWarning("Error " + context + ": " + req.url + ": " + status) sendNext(context) } function sendNext(context) { // Repeat until the first execute() passes while( list.length != 0 ) { // Pick one URL from the list var url = list.shift() var req = new HttpClientRequest(url) req.complete = complete try { req.execute(false, true, context, 5000) logInfo("Sending " + url) requests.push(req) return } catch(e) { // Log a message and pick up next item from list logWarning("Failed to send " + url) } } } // Start 3 requests sendNext(1) sendNext(2) sendNext(3) // Wait until all requests are completed HttpClientRequest.wait(requests) logInfo("Finished.")
```

## Métodos

| Método | Descrição |
| --- | --- |
| [HttpClientRequest](m-httpclientrequest-httpclientrequest.md) | Cria um novo objeto para executar uma consulta de cliente HTTP. |
| [conectar](m-httpclientrequest-connect.md) | Abre a conexão HTTP e passa o objeto para o modo &quot;keep-alive&quot; |
| [desconectar](m-httpclientrequest-disconnect.md) | Fecha a conexão HTTP de um objeto no modo &quot;keep-alive&quot;. |
| [executar](m-httpclientrequest-execute.md) | Executa a consulta HTTP. |
| [espera](m-httpclientrequest-wait.md) | Aguarde até o fim de uma lista de consultas assíncronas. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [corpo](p-httpclientrequest-body.md) | O corpo da consulta HTTP. |
| [concluído](p-httpclientrequest-complete.md) | Função a ser chamada quando uma consulta assíncrona é concluída. |
| [cabeçalho](p-httpclientrequest-header.md) | Um objeto JavaScript que contém os cabeçalhos HTTP do cabeçalho. |
| [método](p-httpclientrequest-method.md) | O método HTTP, no formato de uma cadeia de caracteres |
| [resposta](p-httpclientrequest-response.md) | A resposta da consulta HTTP. Este é um objeto de tipo HttpClientResponse |
| [url](p-httpclientrequest-url.md) | O endereço do servidor remoto. |

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
