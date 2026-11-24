---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 13%
---
# Exportar

Gerar e exportar um relatório

```text
Export ( String reportName, XML context, String exportFormat, String fileName, Boolean isAdHoc )
```

## Parâmetros

**reportName** Nome interno do relatório

**context** Contexto de execução.

**exportFormat** Os valores possíveis são: XLS, OOXML\_SS, ODF\_SS, PDF

XLS gera um documento do Excel 94-2003\
 OOXML\_SS gera um documento do Excel 2007\
 ODF\_SS gera um documento Aberto

**fileName** Nome do arquivo de saída

**isAdHoc** Especifica se a exportação diz respeito a um relatório ad hoc

## Retornar valor(es)

Nenhum.

## Recursos

**Esquema:** [xtk:report](s-xtk-report.md)

**Estático:**

Sim
