---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 6%
---
# addMethod

Declara uma função no serviço.

```text
addMethod (name, action, arguments, responses, requestNodeName, responseNodeName)
```

## Parâmetros

**nome** Nome do método. Esse é o nome exposto no JavaScript e o nome do método SOAP.

**ação** parâmetro SOAP-Action.

**arguments** Declaração de argumentos no formato de uma tabela contendo uma lista de cadeias de caracteres agrupadas por pares. A primeira string é o nome do argumento e a segunda corresponde ao tipo: \[&quot;name1&quot;, &quot;type1&quot;, &quot;name2&quot;, &quot;type2&quot;, ...\]

**respostas** Declaração de valores de retorno na forma de uma tabela contendo uma lista de cadeias de caracteres agrupadas por pares: a primeira cadeia de caracteres é o nome do argumento e a segunda corresponde ao tipo: \[&quot;nome1&quot;, &quot;tipo1&quot;, &quot;nome2&quot;, &quot;tipo2&quot;, ...\]

**requestNodeName** Uma cadeia de caracteres que especifica o nome do nó XML da consulta SOAP em vez do nome do método.

**responseNodeName** Uma cadeia de caracteres que especifica o nome do nó XML da resposta SOAP em vez do nome do método seguido por Response.

## Valor de retorno

Nenhum.

## Observações

Os seguintes tipos são compatíveis:

* sequência de caracteres
* booleano
* longo
* curto
* byte
* flutuante
* duplo
* data
* tempo
* data e hora
* NLDocument
* NLElement
* NLRawXML
* NLCollection

Quando um método é declarado no serviço, ele se torna um método do serviço e pode ser chamado diretamente chamando o método pelo seu nome. O tipo NLRawXML usado em um parâmetro de entrada copia todo o nó XML para substituir o argumento. Usado como um tipo de retorno, ele contém todo o primeiro elemento filho da resposta do SOAP. Seu uso implica que a resposta do SOAP tem apenas um elemento filho. O tipo NLCollection usado em um parâmetro de entrada copia todos os elementos secundários para substituir o argumento. Isso é útil quando o argumento recebido é um parâmetro de variável. Usado como um tipo de retorno, ele contém a resposta SOAP inteira, pois essa é a raiz do valor de retorno. No caso de erros, uma exceção é gerada. Se esse for um erro de SOAP formado corretamente, a exceção gerada terá uma propriedade soapFault e conterá o nó XML do erro SOAP. Exemplo:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
session.addMethod("GetOption", "xtk:session#GetOption",
  ["token", "string", "name", "string"],
  ["value", "string", "type", "byte"])
try
{
var result  = session.GetOption("admin/", "NmsBroadcast_DefaultProvider")
var value   = result[0]
var type    = result[1]
logInfo("Value = " + value)
logInfo("Type = " + type)
}
catch( e )
{
  if( e.soapFault )
    logInfo("A SOAP Fault occured : " + e.soapFault.toXMLString());
  else
    logInfo("An error occured : " + e);
}
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
