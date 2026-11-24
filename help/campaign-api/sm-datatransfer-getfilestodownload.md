---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 28%
---
# GetFilesToDownload

Retorna a lista de arquivos usados por esta transferência e encontrados no servidor

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number jobId )
```

## Parâmetros

**jobId** Identificador de transferência

## Retornar valor(es)

**filesToDownload** Retorna a lista de arquivos que podem ser baixados como um elemento \[dataTransfer/properties/filesToDownload\]

**filesNotToDownload** Retorna a lista de arquivos que não podem ser baixados como um elemento \[dataTransfer/properties/filesNotToDownload\]

## Recursos

**Esquema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Estático:**

Sim
