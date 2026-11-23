---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 9%
---
# WorkflowTransition (Classe)

Representa uma transição de workflow.

Uma transição é um objeto opaco recuperado por métodos como ou e usado para permitir a transição de tarefas.

Exemplo:

```text
var done = task.doneTransition() task.postEvent(done) task.setCompleted() return 0
```

## Recursos

**Disponível em:**

* Fluxo de trabalho
