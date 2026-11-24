---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 33%
---
# ArquivosExistem

Verifica se os arquivos já existem no servidor (como arquivos ou na tabela de recursos).

```text
XML exist = FilesExist ( XML files )
```

## Parâmetros

**arquivos** Lista de arquivos (@name) e suas chaves MD5 (@md5) e Booleano indicando se pode ser um recurso (@checkResource).

## Retornar valor(es)

**existe** Lista de resultados (@md5 e @exists)

## Recursos

**Esquema:** [xtk:job](s-xtk-job.md)

**Estático:**

Sim
