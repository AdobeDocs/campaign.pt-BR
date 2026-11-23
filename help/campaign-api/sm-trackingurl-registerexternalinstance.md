---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 37%
---
# RegisterExternalInstance

Aprova uma instância de rastreamento em um servidor de retransmissão para os servidores de redirecionamento (definindo o identificador do banco de dados).

```text
RegisterExternalInstance ( String login, String instanceName, String dbId, Boolean saveParams )
```

## Parâmetros

**logon** Logon de acesso ao Relay Server

**instanceName** Nome da instância a ser aprovada

**dbId** Identificador do banco de dados do cliente que está executando uma entrega

**saveParams** Salvar opções se bem-sucedido

## Retornar valor(es)

Nenhum.

## Recursos

**Esquema:** [nms:trackingUrl](s-nms-trackingurl.md)

**Estático:**

Sim
