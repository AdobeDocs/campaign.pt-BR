---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 21%
---
# NotificaçãoFila

Solicitação para incluir na fila uma notificação que faz referência a um modelo de entrega.

```text
QueueNotification ( String scenarioName, XML target )
```

## Parâmetros

**scenarioName** Nome interno do modelo

**público-alvo** População do público-alvo da entrega

## Retornar valor(es)

Nenhum.

## Observações

Essa API só pode ser usada no contexto de aplicativos web/pesquisas online. Ao contrário de SubmitNotification, QueueNotification usa um thread dedicado para notificações enfileiradas.

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
