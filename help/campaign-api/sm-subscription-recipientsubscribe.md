---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 31%
---
# RecipientSubscribe

Assinar/cancelar assinatura de destinatários selecionados em uma lista de Serviços informativos.

```text
XML confirmationIds = RecipientSubscribe ( XML recipientList, XML serviceList, Boolean subscribe, XML sendConfirmation )
```

## Parâmetros

**recipientList** Lista de destinatários

**serviceList** Lista de serviços

**inscrever-se** inscrever-se/cancelar inscrição de destinatários

**sendConfirmation** Enviar uma mensagem de confirmação

## Retornar valor(es)

**confirmationIds** Lista de IDs de confirmação

## Recursos

**Esquema:** [nms:subscription](s-nms-subscription.md)

**Estático:**

Sim
