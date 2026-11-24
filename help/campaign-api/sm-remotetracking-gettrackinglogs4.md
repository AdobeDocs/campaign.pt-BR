---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 18%
---
# GetTrackingLogs4

Permite recuperar os logs de rastreamento gerados pelo servidor de redirecionamento remoto e rastreamento web, usando um formato POST 4.00.

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs4 ( String instance, String dbId, String pointer, Number logCount )
```

## Parâmetros

**instância** Identificador curto

**dbId** Identificador do banco de dados do cliente que está executando uma entrega

**ponteiro** Identificador (int64 serializado) do log do qual os logs devem ser recuperados.

**logCount** Número de logs a serem recuperados para a solicitação (0 significa o valor padrão), número de logs retornados pela resposta.

## Retornar valor(es)

**ponteiro** Identificador (int64 serializado) do log do qual os logs devem ser recuperados.

**logCount** Número de logs a serem recuperados para a solicitação (0 significa o valor padrão), número de logs retornados pela resposta.

**logs** logs recuperados

**srvDate** hora GMT do servidor no momento da solicitação de recuperação do log

## Recursos

**Esquema:** [nms:remoteTracking](s-nms-remotetracking.md)

**Estático:**

Sim
