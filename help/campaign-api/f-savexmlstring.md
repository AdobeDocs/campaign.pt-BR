---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 16%
---
# saveXmlString

Este comando está obsoleto, use [saveXmlFile()](f-savexmlfile.md). Salva uma string de caracteres correspondente a um documento XML em um arquivo.

```text
saveXmlString (text, filename [, codePage ])
```

## Parâmetros

**texto** O documento XML na forma de uma cadeia de caracteres a ser salva.

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

Esta função insere um prólogo XML no arquivo, se necessário, e especifica a codificação do documento. Se a codificação de caracteres não for especificada, o padrão do servidor será usado.

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
