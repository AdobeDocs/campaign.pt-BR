---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 8%
---
# DESdecrypt

> Aviso:
>
> Esta função é obsoleta, use [decryptString()](f-decryptstring.md).

Decifra um dado com o algoritmo DES.

```text
DESdecrypt (value [, key ] [, cipher mode ] [, initialization vector ])
```

## Parâmetros

**value** Os dados a serem digitalizados, representados na base 64.

**chave** A chave representada em hexadecimal. A chave deve ter 64 bits ou 16 caracteres hexadecimais. Por padrão, o identificador do banco de dados é usado.

**modo de codificação** O método de codificação de blocos. Uma sequência de caracteres. ou seja, &quot;CBC&quot;, &quot;ECB&quot; ou &quot;EDE&quot;. Por padrão, &quot;CBC&quot;.

**vetor de inicialização** O vetor de inicialização na forma de uma cadeia de caracteres hexadecimal. Exatamente 8 octetos, ou seja, 16 caracteres. Uma string vazia por padrão.

## Valor de retorno

A cadeia de caracteres não criptografada.

## Observações

* Uma chave DES tem 56 bits úteis e 8 bits usados para paridade; esses bits são ignorados.
* Os dados serão descriptografados como uma sequência de 8 bits na página de código do Windows-1252.
* O comprimento dos dados criptografados deve ser um múltiplo de 64 bits.

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
