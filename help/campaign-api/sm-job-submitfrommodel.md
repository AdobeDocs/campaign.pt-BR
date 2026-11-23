---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 17%
---
# SubmitFromModel

Envia um processo a partir de um modelo

```text
Number jobId = SubmitFromModel ( String schema, String where, String methodName, XML diff, Boolean async )
```

## Parâmetros

**esquema** Esquema de modelo de trabalho

**onde** Expressão de seleção de modelo

**methodName** Nome do método a ser chamado

**diff** conteúdo XML para adicionar ao modelo

**assíncrono** Execute um envio de trabalho assíncrono

## Retornar valor(es)

**jobId** Identificador do trabalho recém-criado

## Recursos

**Esquema:** [xtk:job](s-xtk-job.md)

**Estático:**

Sim
