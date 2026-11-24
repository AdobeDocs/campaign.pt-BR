---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 16%
---
# ExportPreview

Calcular a visualização da coluna do arquivo de saída nas primeiras linhas da consulta

```text
[ XML resultColumns, XML resultXML, String resultSQLRequest ] = ExportPreview ( XML dataTransferStep, Number lineCount, Boolean countMode, String calcFieldName )
```

## Parâmetros

**dataTransferStep** Etapa de transferência em que o campo calculado é definido.

**lineCount** Número de linhas a serem retornadas

**countMode** Modo de contagem de linhas

**calcFieldName** Nome do campo calculado observado. Se estiver vazio, é uma pré-visualização global do arquivo de saída.

## Retornar valor(es)

**resultColumns** retorna os valores das colunas do arquivo de exportação (line/col/val, line/col/errors).

**resultXML** Retorna o documento XML de saída da consulta.

**resultSQLRequest** Retorna a consulta SQL executada.

## Recursos

**Esquema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Estático:**

Sim
