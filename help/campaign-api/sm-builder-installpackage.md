---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 18%
---
# InstallPackage

Instalar um pacote.

```text
InstallPackage ( XML parameters )
```

## Parâmetros

**parâmetros** elemento XML que contém o pacote a ser importado.

## Retornar valor(es)

Nenhum.

## Observações

Um pacote gerado pelo método SpecFile.Generate() deve ser encapsulado em um elemento de construtor. Exemplo:

```javascript
var params =
  {builder:
    {package:
      { ... }
    }
  }

NLWS.xtkBuilder.InstallPackage(params)
```

## Recursos

**Esquema:** [xtk:builder](s-xtk-builder.md)

**Estático:**

Sim
