---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 41%
---
# BuildUpdateSchemaDiff

Gera um documento que descreve as diferenças entre a estrutura real do banco de dados e sua descrição lógica.

```text
XML sqlSchemaDiff = BuildUpdateSchemaDiff ( XML parameters, Boolean useNamingConventions )
```

## Parâmetros

**parâmetros** Atualizar parâmetros

**useNamingConvention** Use convenções de nomenclatura SQL para calcular caminhos de novos campos.

## Retornar valor(es)

**sqlSchemaDiff** Esquema gerado

## Recursos

**Esquema:** [xtk:builder](s-xtk-builder.md)

**Estático:**

Sim
