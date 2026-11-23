---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 44%
---
# GenCreateOrUpdateSchemaSequenceDDL

Gera o script SQL usado para criar ou atualizar a sequência do esquema autoPk

```text
String sqlDDL = GenCreateOrUpdateSchemaSequenceDDL ( String schemaId, String newSequence, String oldSequence )
```

## Parâmetros

**schemaId** Identificador de esquema

**newSequence** Nova sequência

**oldSequence** Sequência antiga

## Retornar valor(es)

Script SQL **sqlDDL**

## Recursos

**Esquema:** [xtk:builder](s-xtk-builder.md)

**Estático:**

Sim
