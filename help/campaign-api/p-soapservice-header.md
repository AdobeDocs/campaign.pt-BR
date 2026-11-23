---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 28%
---
# cabeçalho

Uma cadeia de caracteres textualmente copiada no cabeçalho do SOAP.

```text
header
```

## Observações

Les chaînes de caractères sont recopiées in-extenso dans l&#39;en-tête SOAP sans vérification Exemplo:

```javascript
      var cnx = new HttpSoapConnection(result.serverURL, "utf-8", HttpSoapConnection.SOAP_11)
var service = new SoapService(cnx, "urn:partner.soap.sforce.com")
service.header = "<ns1:SessionHeader xmlns:ns1='urn:partner.soap.sforce.com'><ns1:sessionId>123456</ns1:sessionId></ns1:SessionHeader>"
```

## Recursos

**Propriedade da classe:** [SoapService](c-soapservice.md)

**Somente leitura:**

Não

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
