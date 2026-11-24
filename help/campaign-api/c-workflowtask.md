---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 4%
---
# WorkflowTask (Classe)

Status de uma tarefa de workflow.

⌐`WorkflowTask` é uma classe que não pode ser instanciada e para a qual há apenas uma única instância acessível nas atividades de fluxo de trabalho chamadas `task`.

## Métodos

| Método | Descrição |
| --- | --- |
| [setCompleted](m-workflowtask-setcompleted.md) | Sinaliza a tarefa como concluída. |
| [postEvent](m-workflowtask-postevent.md) | Ativa uma transição. |
| [setNextProcessingDate](m-workflowtask-setnextprocessingdate.md) | Força a próxima data de processamento pela tarefa. |
| [TransiçãoConcluída](m-workflowtask-donetransition.md) | Retorna a transição &quot;concluído&quot; da atividade. |
| [transiçãoDeErro](m-workflowtask-errortransition.md) | Retorna a transição &quot;error&quot; da atividade. |
| [transitionByType](m-workflowtask-transitionbytype.md) | Retorna a transição correspondente ao tipo especificado. |
| [transitionByName](m-workflowtask-transitionbyname.md) | Retorna as transições correspondentes ao nome especificado. |
| [transições](m-workflowtask-transitions.md) | Retorna a lista de transições da atividade. |
| [espera](m-workflowtask-wait.md) | Aguarda um sinal. |

## Recursos

**Disponível em:**

* Fluxo de trabalho
