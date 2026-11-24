---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 5%
---
# Limpeza

Limpa o histórico do workflow.

```text
Cleanup ( String workflowId )
```

## Parâmetros

**workflowId** Identificador ou nome interno do fluxo de trabalho.

## Retornar valor(es)

Nenhum.

## Observações

Exclui todos os eventos processados, tarefas concluídas, tarefas com falha e mensagens de log. Também exclui o progresso do diagrama se o workflow estiver concluído. Esse método exclui os dados que não são mais usados apenas pelo mecanismo de workflow e não afeta o comportamento do workflow.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
