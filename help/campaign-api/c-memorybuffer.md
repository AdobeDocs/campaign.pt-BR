---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 6%
---
# MemoryBuffer (Classe)

Representa um conteúdo binário armazenado na memória.

Um é um objeto intermediário para manipular dados de e para um arquivo.

## Métodos

| Método | Descrição |
| --- | --- |
| [descartar](m-memorybuffer-dispose.md) | Libera os recursos usados pelo objeto. |
| [carregar](m-memorybuffer-load.md) | Carrega o conteúdo de um arquivo no buffer. |
| [salvar](m-memorybuffer-save.md) | Salva o conteúdo do buffer em um arquivo. |
| [paraXML](m-memorybuffer-toxml.md) | Retorna um objeto XML JavaScript obtido do conteúdo do [MemoryBuffer](c-memorybuffer.md). Esta função é obsoleta, use [toDocument()](m-memorybuffer-todocument.md) |
| [paraDocumento](m-memorybuffer-todocument.md) | Retorna um documento XML do conteúdo de texto deste buffer. |
| [toString](m-memorybuffer-tostring.md) | Retorna o conteúdo de [MemoryBuffer](c-memorybuffer.md) na forma de uma cadeia de caracteres. |
| [fromString](m-memorybuffer-fromstring.md) | Carrega o conteúdo de uma cadeia de caracteres no buffer. |
| [toBase64](m-memorybuffer-tobase64.md) | Converte o buffer ou parte da cadeia de caracteres codificada na base 64. |
| [appendBase64](m-memorybuffer-appendbase64.md) | Acrescenta dados de uma cadeia de caracteres codificada na base 64 ao final do buffer. |
| [removerTudo](m-memorybuffer-removeall.md) | Libera o buffer. |
| [sha1](m-memorybuffer-sha1.md) | Calcula a assinatura SHA-1 do conteúdo do MemoryBuffer. |
| [sha224](m-memorybuffer-sha224.md) | Calcula a assinatura SHA-2 de 224 bits do conteúdo do MemoryBuffer. |
| [sha256](m-memorybuffer-sha256.md) | Calcula a assinatura SHA-2 de 256 bits do conteúdo do MemoryBuffer. |
| [sha384](m-memorybuffer-sha384.md) | Calcula a assinatura SHA-2 de 384 bits do conteúdo do MemoryBuffer. |
| [sha512](m-memorybuffer-sha512.md) | Calcula a assinatura SHA-2 de 512 bits do conteúdo do MemoryBuffer. |
| [fromHexString](m-memorybuffer-fromhexstring.md) | Carrega o conteúdo de uma string hexadecimal no buffer. |
| [toHexString](m-memorybuffer-tohexstring.md) | Converte o buffer em uma string de caracteres hexadecimais. |
| [hmac](m-memorybuffer-hmac.md) | Calcula o hash MD5, SHA-1 ou SHA-256 do buffer. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [tamanho](p-memorybuffer-size.md) | Retorna o tamanho do buffer em bytes. |
| [isEmpty](p-memorybuffer-isempty.md) | Retorna verdadeiro se o buffer estiver vazio. |

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
