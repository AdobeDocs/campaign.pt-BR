---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 2%
---
# GetValidationParameters

Retorna os parâmetros de uma tarefa de workflow em andamento.

```text
XML content = GetValidationParameters ( String workflowId, String taskIdentifier )
```

## Parâmetros

**workflowId** Identificador ou nome interno do fluxo de trabalho.

**taskIdentifier** O identificador da tarefa do tipo aprovação (campo @taskIdentifier).

## Retornar valor(es)

**conteúdo** O documento XML que contém os parâmetros.

## Observações

O documento retornado contém todas as informações relacionadas à validação, quem respondeu e quem ainda pode responder.

* Os atributos title, creationDate, processingDate, timeout, status, abortReason e completionDate correspondem aos atributos na tarefa de validação.
* isAssignee: o operador atual está no grupo atribuído a essa tarefa.
* hasResponded: o operador atual já respondeu.
* canReply: o operador atual pode responder (ninguém respondeu ainda ou várias respostas estão autorizadas.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
