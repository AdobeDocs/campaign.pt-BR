---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 13%
---
# HttpSoapConnection

Cria uma conexão HTTP com um servidor do SOAP.

```text
HttpSoapConnection (url [, codepage ] [, protocol ] [, async ])
```

## Parâmetros

URL **url** do servidor, incluindo o caminho.

**página de código** A codificação para a serialização da chamada SOAP. Esse parâmetro opcional permite especificar a codificação de caracteres. A codificação padrão é UTF-8. Exemplo:

* iso-8859-1
* utf-8
* utf-16

**protocolo** O tipo de protocolo SOAP usado. Esse parâmetro opcional permite especificar o protocolo SOAP usado, que é SOAP\_11 por padrão. Valores possíveis:

* SOAP\_11: protocolo SOAP 1.1.
* SOAP\_12: protocolo SOAP 1.2.
* 0: protocolo SOAP interno ao Adobe Campaign.

**async** Booleano definido como true se a conexão for destinada a executar uma consulta assíncrona. Definido como falso por padrão.

## Valor de retorno

Nenhum.

## Observações

Exemplos:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp")
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-16", HttpSoapConnection.SOAP_11)
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-8", 0)
```

## Recursos

**Método de classe:** [HttpSoapConnection](c-httpsoapconnection.md)

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
