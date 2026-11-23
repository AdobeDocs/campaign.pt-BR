---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%
---
# cryptString

> Aviso:
>
> Esta função está totalmente obsoleta. Para obter mais detalhes, consulte esta [página](https://experienceleague.adobe.com/pt-br/docs/campaign-classic/using/technotes/gcm-functions#deprecated-functions-headding-anchor-depracated-functions).

Criptografa uma cadeia de caracteres com a chave da instância ou qualquer outra chave.

```text
cryptString (str [, key ] [, useSalt ])
```

## Parâmetros

**str** A cadeia de caracteres a ser criptografada.

**chave** A chave de criptografia AES é codificada na base 64: 256 bits se o comprimento da chave for 32; 192 bits se o comprimento da chave for 24; 128 bits se o comprimento da chave for 16 ou se nenhuma chave for especificada.

**useSalt** Use um salt dos dados para criptografar. Verdadeiro por padrão.

## Valor de retorno

Retorna a cadeia de caracteres criptografada

## Observações

A criptografia ocorre de acordo com o seguinte método:

* A sequência de caracteres unicode é transformada em uma sequência UTF-8.
* Um caractere de verificação é adicionado ao final.
* Essa cadeia de caracteres é criptografada usando o algoritmo AES no modo CBC (Encadeamento de blocos de cifra) com um vetor de inicialização nulo. Se nenhuma chave for fornecida como parâmetro, a chave da instância será usada.
* O bloco criptografado é então convertido na base 64.

A descriptografia é realizada usando a função [decryptString](f-decryptstring.md).

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
