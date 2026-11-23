---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 19%
---
# addHeader

Adiciona um cabeçalho HTTP

```text
addHeader (headerName, headerValue)
```

## Parâmetros

**headerName** Cadeia de caracteres que é o nome do cabeçalho HTTP.

**headerValue** Cadeia de caracteres que é o conteúdo do cabeçalho HTTP.

## Valor de retorno

Nenhum.

## Observações

Os cabeçalhos especificados dessa maneira prevalecem sobre os cabeçalhos padrão durante as chamadas de SOAP. Exemplo:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.addHeader("Authorization","Basic " + memBuf.toBase64());
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
