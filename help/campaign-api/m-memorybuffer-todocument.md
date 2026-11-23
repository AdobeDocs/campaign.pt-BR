---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 23%
---
# toDocument

Retorna um documento XML do conteúdo de texto deste buffer.

```text
toDocument ( [codePage ])
```

## Parâmetros

**codePage** Um número inteiro que codifica a página de caracteres usada. Por padrão, MemoryBuffer.CODEPAGE\_UTF8.

## Valor de retorno

Um objeto de tipo [DOMDocument](c-domdocument.md).

## Recursos

**Método de classe:** [MemoryBuffer](c-memorybuffer.md)

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
