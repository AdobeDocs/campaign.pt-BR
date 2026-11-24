---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# Assinar

Criar ou atualizar a assinatura de um Serviço de informação de um destinatário

```text
Subscribe ( String serviceName, XML recipient, Boolean create )
```

## Parâmetros

**serviceName** Lista de nomes de Serviços de Informações (separados por vírgula)

**recipient** Destinatário a registrar e, opcionalmente, criar

**criar** Criar destinatário se ele não existir

## Retornar valor(es)

Nenhum.

## Exemplo

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Subscribe("SVC1", recipient, false)
        
```

## Recursos

**Esquema:** [nms:subscription](s-nms-subscription.md)

**Estático:**

Sim
