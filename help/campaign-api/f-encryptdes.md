---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# encryptDES

> Aviso:
>
> Esta função é obsoleta, use [cryptString()](f-cryptstring.md).

Criptografa uma string com o algoritmo DES.

```text
encryptDES (key, value [, cipher mode ] [, initialization vector ] [, padding ])
```

## Parâmetros

**chave** A chave representada em hexadecimal. A chave deve ter 64 bits de comprimento, ou seja, 16 caracteres hexadecimais.

**value** A cadeia de caracteres a ser criptografada

**modo de codificação** O método para codificar blocos. Uma sequência de caracteres. ou seja, &quot;CBC&quot;, &quot;ECB&quot; ou &quot;EDE&quot;. Por padrão, &quot;CBC&quot;.

**vetor de inicialização** O vetor de inicialização na forma de uma cadeia de caracteres hexadecimal. Exatamente 8 octetos, ou seja, 16 caracteres. Uma string vazia por padrão.

**preenchimento** O tipo de preenchimento. Uma sequência de caracteres, ou seja, &quot;PKCS5PADDING&quot; ou &quot;PKCS7PADDING&quot;. Por padrão, uma cadeia de caracteres vazia, o que significa que &#39;\\0&#39; é adicionado ao final da cadeia de caracteres para criptografar.

## Valor de retorno

A cadeia de caracteres criptografada representada na base 64.

## Observações

* Uma chave DES tem 56 bits úteis e 8 bits usados para paridade; esses bits são ignorados.
* O valor efetivamente criptografado pelo algoritmo DES será a representação Windows-1252 de 8 bits da string, terminando com um caractere ASCII 0 e preenchido com múltiplo de 64 bits com zeros binários.
* O valor criptografado será um múltiplo de palavras de 64 bits.

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
