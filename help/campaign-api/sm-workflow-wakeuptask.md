---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 3%
---
# TarefaAtivação

Força o processamento avançado de uma ou mais tarefas pendentes.

```text
WakeupTask ( String workflowId, String taskIdentifier, String activityName )
```

## Parâmetros

**workflowId** Identificador ou nome interno do fluxo de trabalho.

**taskIdentifier** O identificador da tarefa (campo @taskIdentifier) ou uma cadeia de caracteres vazia para forçar o processamento antecipado de todas as tarefas pendentes associadas a uma determinada atividade.

**activityName** O nome da atividade que força o processamento antecipado de todas as tarefas associadas ou uma cadeia de caracteres vazia.

## Retornar valor(es)

Nenhum.

## Observações

Se taskIdentifier e activityName não forem especificados, todas as tarefas pendentes serão consideradas.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
