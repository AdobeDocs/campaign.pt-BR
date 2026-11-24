---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 3%
---
# EvaluateContent

Avalia o conteúdo de uma entrega vinculada a uma ordem. Essa avaliação será realizada ao fazer pedidos usando direitos de operador e antes da criação da campanha local.

```text
XML result = EvaluateContent ( XML order, Number deliveryId, String contentType, Number seedMemberId )
```

## Parâmetros

**order** Elemento que contém informações de ordem.

**deliveryId** ID da entrega a ser avaliada.

**contentType** Tipo de conteúdo a ser retornado (html ou texto para um email; cadeia vazia para outros canais).

**seedMemberId** ID de seed address usada para personalização de conteúdo.

## Retornar valor(es)

**resultado** Conteúdo avaliado.

## Recursos

**Esquema:** [nms:localOrder](s-nms-localorder.md)

**Estático:**

Sim
