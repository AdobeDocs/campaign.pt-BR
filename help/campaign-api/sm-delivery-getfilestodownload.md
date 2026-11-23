---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# GetFilesToDownload

Retorna a lista de arquivos encontrados no servidor associado à entrega.

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number deliveryId )
```

## Parâmetros

**deliveryId** Identificador de entrega

## Retornar valor(es)

**filesToDownload** Retorna a lista de arquivos que podem ser baixados como elemento \[properties/filesToDownload\]

**filesNotToDownload** Retorna a lista de arquivos que não podem ser baixados como elemento \[properties/filesNotToDownload\]

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
