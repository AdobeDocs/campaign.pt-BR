---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%
---
# SoapService (Classe)

Permite executar chamadas SOAP em um serviço da Web.

## Bloqueando chamadas

Este é um exemplo típico de uso: Primeiro, você deve criar uma conexão e depois um serviço usando essa conexão e, em seguida, declarar os métodos do SOAP para esse serviço. O método SOAP é exposto no formato de um método JavaScript do objeto de serviço.

```text
var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0) var session = new SoapService(cnx, "xtk:session") session.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) var result = session.GetOption("admin/", "NmsBroadcast_DefaultProvider") var value = result[0] var type = result[1] logInfo("Value = " + value) logInfo("Type = " + type)
```

## Chamadas não bloqueadas

É possível executar chamadas não bloqueadas (assíncronas), ou seja, executar um query do SOAP em um servidor e continuar a executar o script sem esperar pelo resultado. As principais diferenças com o modo de bloqueio são:

* A conexão deve ser criada no modo assíncrono

* Use os

  [iniciar](m-soapservice-start.md)

  função.

* Definir um

  [concluído](p-soapservice-complete.md)

  no serviço, a ser chamado quando a resposta for recebida.

* O

  [SoapService.wait](m-soapservice-wait.md)

  é usada para aguardar o fim do processamento de um conjunto de consultas.

O script de exemplo a seguir faz uma série de chamadas &#39;GetOption&quot; do SOAP para um servidor Adobe Campaign, abrindo 3 conexões simultaneamente.

```text
var list = [ "XtkDatabaseId", "XtkKey", "WdbcTimeZone", "NmsServer_URL", "NmsBroadcast_DefaultProvider"] var requests = [] function complete(service, result, context, status) { if( status == "success" ) logInfo("option " + context + ": value = " + result[0]) else if( status == "fault" ) logInfo("option " + context + ": fault = " + result.message) else logInfo("option " + context + ": " + status) sendNext(service) } function createService() { // Create the connection var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0, true) // Create the service var service = new SoapService(cnx, "xtk:session") service.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) // Change the timeout to 5 seconds service.timeout = 5000 // Setup the callback function service.complete = complete return service } function sendNext(service) { if( list.length == 0) return // Pick an item from the list var name = list.shift() // Use the name as context var context = name // Send the request var req = service.start(context, "GetOption", "admin/", name) // Add the request to the wait queue requests.push(req) } // Open 3 connections and start a request on each one sendNext(createService()) sendNext(createService()) sendNext(createService()) SoapService.wait(requests) logInfo("Done.")
```

## Métodos

| Método | Descrição |
| --- | --- |
| [SoapService](m-soapservice-soapservice.md) | Cria um serviço para chamar as funções de um serviço Web. |
| [addMethod](m-soapservice-addmethod.md) | Declara uma função no serviço. |
| [descartar](m-soapservice-dispose.md) | Libera os recursos usados pelo objeto. |
| [início](m-soapservice-start.md) | Inicia uma consulta no modo assíncrono. |
| [espera](m-soapservice-wait.md) | Aguarda o fim de uma lista de consultas assíncronas do SOAP. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [concluído](p-soapservice-complete.md) | Função a ser chamada quando uma consulta assíncrona é concluída. |
| [cabeçalho](p-soapservice-header.md) | Uma cadeia de caracteres textualmente copiada no cabeçalho do SOAP. |
| [tempo limite](p-soapservice-timeout.md) | Tempo máximo de espera em milissegundos no caso de uma consulta assíncrona. Se esse parâmetro não estiver definido, o tempo de espera será de 5 minutos. |

## Recursos

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
