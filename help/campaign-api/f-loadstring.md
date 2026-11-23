---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 23%
---
# loadString

Este comando está obsoleto, use ⌐[loadFile()](f-loadfile.md). Retorna o conteúdo de um arquivo de texto

```text
loadString (filename [, codePage ])
```

## Parâmetros

**filename** O nome completo do arquivo a ser carregado.

**codePage** Este parâmetro opcional permite que você especifique a codificação de caracteres. Exemplo:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valor de retorno

Uma sequência de caracteres correspondente ao conteúdo do arquivo de texto.

## Observações

Se a codificação de caracteres não for especificada, o padrão do servidor será usado.

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
