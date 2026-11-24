---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 26%
---
# SoapService

Cria um serviço para chamar as funções de um serviço Web.

```text
SoapService (cnx, namespace)
```

## Parâmetros

**cnx** a conexão HTTP ([HttpSoapConnection](c-httpsoapconnection.md)).

**namespace** Namespace do serviço.

## Valor de retorno

Nenhum.

## Observações

Exemplo:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
```

## Recursos

**Método de classe:** [SoapService](c-soapservice.md)

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
