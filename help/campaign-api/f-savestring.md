---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 22%
---
# saveString

Este comando está obsoleto, use [saveFile()](f-savefile.md). Salva uma cadeia de caracteres em um arquivo.

```text
saveString (text, filename [, codePage ])
```

## Parâmetros

**texto** A sequência de texto a ser salva.

**filename** O nome completo do arquivo a ser salvo.

**codePage** Este parâmetro opcional permite que você especifique a codificação de caracteres. Exemplo:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valor de retorno

Nenhum.

## Observações

Se a codificação de caracteres não for especificada, o padrão do servidor será usado.

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
