---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 19%
---
# GetMidDeliveries

Recupera o status das entregas modificadas por último no modo de mid-sourcing.

```text
[ XML result, Date nextDate ] = GetMidDeliveries ( Date startDate, Number maxCount, Date emitterDate )
```

## Parâmetros

**startDate** Recupere as modificações feitas desde esta data (no servidor mid-sourcing).

**maxCount** Número máximo de entregas a serem recuperadas, desde que não tenham sido atualizadas durante o mesmo segundo.

**emitterDate** Data de referência do servidor emissor. Usado para ajustar datas de entregas.

## Retornar valor(es)

**resultado** Documento de saída, lista de entregas atualizada.

**nextDate** Data de início da próxima chamada.

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
