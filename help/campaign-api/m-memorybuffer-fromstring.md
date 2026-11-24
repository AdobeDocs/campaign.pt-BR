---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 31%
---
# fromString

Carrega o conteúdo de uma cadeia de caracteres no buffer.

```text
fromString (string [, codepage ])
```

## Parâmetros

**cadeia** A cadeia de caracteres.

**página de código** Página de código usada para serializar a cadeia de caracteres no buffer. Esse parâmetro opcional permite especificar a codificação de caracteres. Por exemplo:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valor de retorno

Nenhum.

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
