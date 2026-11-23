---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 41%
---
# Cancelar assinatura

Cancela a assinatura de um Serviço de informação de um destinatário

```text
Unsubscribe ( String serviceName, XML recipient )
```

## Parâmetros

**serviceName** Lista de nomes de Serviços de Informações (separados por vírgula)

Destinatário **recipient**

## Retornar valor(es)

Nenhum.

## Exemplo

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Unsubscribe("SVC1", recipient)
        
```

## Recursos

**Esquema:** [nms:subscription](s-nms-subscription.md)

**Estático:**

Sim
