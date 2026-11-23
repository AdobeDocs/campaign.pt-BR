---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%
---
# SubmitDelivery

Criação e envio de uma entrega a partir de um cenário (a partir de seu nome interno).

```text
Number deliveryId = SubmitDelivery ( String scenarioName, XML content )
```

## Parâmetros

**scenarioName** Nome interno do modelo de entrega

**conteúdo** conteúdo XML a ser adicionado ao modelo

## Retornar valor(es)

**deliveryId** Identificador da nova entrega (retornado mesmo se a análise falhar)

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
