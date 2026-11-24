---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 35%
---
# Executar

Executa um processo de forma síncrona (nesse modo, as informações de progresso e o cancelamento não estão disponíveis).

```text
String id = job.Execute ( String methodName ) const
```

## Parâmetros

**methodName** Nome do método a ser chamado na entidade

## Retornar valor(es)

**id** Identificador do trabalho criado (o evento retornado do trabalho falhou se foi criado no banco de dados)

## Recursos

**Esquema:** [xtk:job](s-xtk-job.md)

**Estático:**

Não

**Const:**

Sim

**Somente chave:**

Não
