---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# setNextProcessingDate

Força a próxima data de processamento pela tarefa.

```text
setNextProcessingDate (timestamp)
```

## Parâmetros

**carimbo de data/hora** Data do próximo processamento. Se estiver vazio, o próximo processamento será imediato.

## Valor de retorno

Nenhum.

## Observações

* O uso desse método substitui a próxima data de processamento, se fornecida pelo scheduler.
* O próximo processamento é sempre executado pela função \*\_recall().

## Recursos

**Método de classe:** [WorkflowTask](c-workflowtask.md)

**Disponível em:**

* Fluxo de trabalho
