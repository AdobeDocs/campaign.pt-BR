---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%
---
# GetQuarantines

Recupera as últimas quarentenas e saídas de quarentena.

```text
[ XML result, Date nextDate, Boolean hasMore ] = GetQuarantines ( Date startDate, String pointerName, Number quarantineCount, Date callerDate )
```

## Parâmetros

**startDate** Recupere as quarentenas modificadas desde esta data. Quando vazio, o valor do ponteiro é usado.

**pointerName** Recupere as quarentenas modificadas desde este ponteiro (opcional).

**quarantineCount** Número máximo de quarentenas a serem recuperadas, desde que não tenham sido atualizadas durante o mesmo segundo.

**callerDate** Data de referência do chamador. Permite modificar a data de quarentena de referência (opcional).

## Retornar valor(es)

**resultado** Documento de saída, lista de quarentenas.

**nextDate** Data da primeira quarentena não recuperada (estritamente superior à startDate).

**hasMore**. Nesse caso, ainda há quarentenas a serem recuperadas.

## Recursos

**Esquema:** [nms:address](s-nms-address.md)

**Estático:**

Sim
