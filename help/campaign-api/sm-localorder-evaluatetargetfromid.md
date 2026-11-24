---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%
---
# EvaluateTargetFromId

Avalia o direcionamento de campanha para cada entrega de campanha vinculada a um pedido. Essa avaliação será realizada ao fazer pedidos usando direitos de operador e antes da criação da campanha local.

```text
XML result = EvaluateTargetFromId ( Number orderId )
```

## Parâmetros

ID do pedido **orderId**.

## Retornar valor(es)

**resultado** Resultado das contagens de cada uma das entregas da campanha.

## Recursos

**Esquema:** [nms:localOrder](s-nms-localorder.md)

**Estático:**

Sim
