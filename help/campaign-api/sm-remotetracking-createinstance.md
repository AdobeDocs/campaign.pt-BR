---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 15%
---
# CreateInstance

> Aviso: essa função está disponível para um ambiente no local.

Usado para criar uma instância de rastreamento

```text
CreateInstance ( String instanceName, String hosts, String dbId, String cryptedPwd, String lang )
```

## Parâmetros

**instanceName** Nome da instância a ser criada

**hosts** máscaras de DNS associadas à instância

**dbId** Identificador do banco de dados do cliente que está executando uma entrega

**cryptedPwd** Senha criptografada usada para rastreamento

**lang** Idioma da instância

## Retornar valor(es)

Nenhum.

## Recursos

**Esquema:** [nms:remoteTracking](s-nms-remotetracking.md)

**Estático:**

Sim
