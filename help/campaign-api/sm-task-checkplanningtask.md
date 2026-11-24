---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 6%
---
# VerificarTarefaDePlanejamento

Função interna usada para verificar sobrecargas dentro das programações de operadores de tarefa (retorna &#39;true&#39; em caso de sobrecarga). Essa função também verifica a consistência dos agendamentos de tarefas relacionadas e as atualiza se necessário.

```text
Boolean workloadAlert = CheckPlanningTask ( Number taskId )
```

## Parâmetros

**taskId** Identificador da tarefa.

## Retornar valor(es)

**workloadAlert** Aviso de sobrecarga de recurso

## Recursos

**Esquema:** [nms:task](s-nms-task.md)

**Estático:**

Sim
