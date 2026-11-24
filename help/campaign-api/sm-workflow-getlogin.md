---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 2%
---
# GetLogin

Retorna informações da conta de execução.

```text
[ Number id, String login, String cs ] = GetLogin ( String workflowId )
```

## Parâmetros

**workflowId** Identificador ou nome interno do fluxo de trabalho.

## Retornar valor(es)

**id** Identificador do operador ou 0 se nenhum operador estiver associado a este fluxo de trabalho.

**logon** Logon do operador ou cadeia de caracteres vazia se nenhum operador estiver associado a este fluxo de trabalho.

**cs** Cadeia de caracteres de descrição do operador ou cadeia de caracteres vazia se nenhum operador estiver associado a este fluxo de trabalho.

## Observações

A conta de execução associada a um workflow permite forçar os direitos de execução a um operador específico em vez do operador que iniciou o workflow. A conta de execução não é propagada quando um workflow é duplicado.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
