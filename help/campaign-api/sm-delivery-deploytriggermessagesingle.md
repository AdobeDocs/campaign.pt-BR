---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 6%
---
# DeployTriggerMessageSingle

Publique a mensagem transacional nas instâncias de execução. Retorna verdadeiro se a publicação for bem-sucedida, e falso, se não for.

```text
Boolean isSuccess = DeployTriggerMessageSingle ( Number deliveryId, Boolean localPublish )
```

## Parâmetros

**deliveryId** ID da entrega a ser implantada

**localPublish** Publicar somente na instância de controle?

## Retornar valor(es)

**isSuccess** Publicação concluída

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
