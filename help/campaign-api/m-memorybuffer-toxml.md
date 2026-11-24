---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 17%
---
# toXML

Retorna um objeto XML JavaScript obtido do conteúdo de [MemoryBuffer](c-memorybuffer.md). Esta função é obsoleta, use [toDocument()](m-memorybuffer-todocument.md)

```text
toXML ( [codePage ])
```

## Parâmetros

**codePage** Um número inteiro que codifica a página de caracteres usados. Por padrão, MemoryBuffer.CODEPAGE\_UTF8.

## Valor de retorno

O conteúdo de um carimbo na forma de um objeto XML.

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
