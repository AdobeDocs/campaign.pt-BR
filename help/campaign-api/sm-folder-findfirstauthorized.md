---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# FindFirstAuthorized

Localiza a primeira pasta qualificada para o usuário atual, cumprindo a condição folderFilter.

```text
XML folderEntity = FindFirstAuthorized ( String folderFilter, Boolean writeAccess, Number orgUnit )
```

## Parâmetros

Filtro **folderFilter** em pastas

**writeAccess** A pasta retornada deve ser gravável

**orgUnit** A pasta retornada deve ser compatível com a entidade organizacional especificada

## Retornar valor(es)

**folderEntity** Retorna a entidade de pasta associada (nulo se nenhuma pasta for encontrada)

## Recursos

**Esquema:** [xtk:folder](s-xtk-folder.md)

**Estático:**

Sim
