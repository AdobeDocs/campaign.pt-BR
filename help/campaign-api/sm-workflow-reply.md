---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%
---
# Responder

Responde a uma tarefa do tipo validação em andamento.

```text
Reply ( String workflowId, String taskIdentifier, String response, String choice )
```

## Parâmetros

**workflowId** Identificador ou nome interno do fluxo de trabalho.

**taskIdentifier** O identificador da tarefa do tipo aprovação (campo @taskIdentifier).

**resposta** O comentário associado à resposta.

**escolha** A escolha da resposta. Essa opção deve corresponder ao nome da transição a ser ativada.

## Retornar valor(es)

Nenhum.

## Observações

O operador atual deve estar no grupo atribuído à tarefa.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
