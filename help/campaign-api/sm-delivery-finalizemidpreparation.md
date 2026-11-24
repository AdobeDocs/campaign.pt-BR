---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%
---
# FinalizeMidPreparation

Finalizar a análise de uma entrega no modo de mid-sourcing.

```text
[ Number fatalError, String fatalErrorMsg ] = FinalizeMidPreparation ( Number deliveryId, Number errorCode, XML properties, Boolean retry )
```

## Parâmetros

**deliveryId** Identificador de entrega

**errorCode** Código de erro retornado pela análise no banco de dados de marketing (o código de erro de nível de método não é usado para isso)

**propriedades** Propriedades de entrega a serem atualizadas

**repetir** Especifica se esta é uma nova tentativa para a chamada de método.

## Retornar valor(es)

**fatalError** Retorna um código de erro que impede o chamador de executar desativações. Caso contrário, o erro pode ser temporário.

**fatalErrorMsg** Mensagem de erro associada ao código de erro &#39;fatalError&#39;.

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
