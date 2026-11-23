---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 48%
---
# BuildUpdateOneSchemaDiff

Gera um documento que descreve as diferenças entre uma tabela no banco de dados físico e a descrição lógica dessa tabela.

```text
XML sqlSchemaDiff = BuildUpdateOneSchemaDiff ( String schemaId, Boolean useNamingConventions )
```

## Parâmetros

**schemaId** Identificador de esquema

**useNamingConvention** Use convenções de nomenclatura SQL para calcular caminhos de novos campos.

## Retornar valor(es)

**sqlSchemaDiff** Esquema gerado

## Recursos

**Esquema:** [xtk:builder](s-xtk-builder.md)

**Estático:**

Sim
