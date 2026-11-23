---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 4%
---
# fluxo de trabalho

Definições de fluxos de trabalho

## Métodos

| Método | Descrição |
| --- | --- |
| [Limpeza](sm-workflow-cleanup.md) | Limpa o histórico do workflow. |
| [ExcluirResultado](sm-workflow-deleteresult.md) | Apaga os resultados de uma ou mais atividades. |
| [Executar](sm-workflow-execute.md) | Executa um fluxo de trabalho imediatamente e aguarda sua conclusão. |
| [ExecuteInstance](sm-workflow-executeinstance.md) | Executa um fluxo de trabalho imediatamente e aguarda sua conclusão. |
| [GetLogin](sm-workflow-getlogin.md) | Retorna informações da conta de execução. |
| [GetValidationParameters](sm-workflow-getvalidationparameters.md) | Retorna os parâmetros de uma tarefa de workflow em andamento. |
| [Eliminar](sm-workflow-kill.md) | Interrompe incondicionalmente um workflow. |
| [Pause](sm-workflow-pause.md) | Suspende a execução de um fluxo de trabalho em andamento. |
| [PostEvent](sm-workflow-postevent.md) | Gera um evento de qualquer tipo de atividade. |
| [Responder](sm-workflow-reply.md) | Responde a uma tarefa do tipo validação em andamento. |
| [Restart](sm-workflow-restart.md) | Vincula uma interrupção de workflow e um início de workflow. |
| [TarefaDeReinicialização](sm-workflow-restarttask.md) | Força a reinicialização de uma ou mais tarefas concluídas. |
| [DefinirLogon](sm-workflow-setlogin.md) | Altera a conta de execução. |
| [Simular](sm-workflow-simulate.md) | Inicia um workflow no modo de simulação. |
| [SimularComParâmetros](sm-workflow-simulatewithparameters.md) | Inicia um fluxo de trabalho no modo de simulação e fornece parâmetros. |
| [Geração](sm-workflow-spawn.md) | Cria uma instância de workflow a partir de um modelo, aplica uma correção e inicia este workflow. |
| [SpawnWithParameters](sm-workflow-spawnwithparameters.md) | Cria uma instância de fluxo de trabalho a partir de um modelo e invoca o método [StartWithParameters](sm-workflow-startwithparameters.md) nessa instância. |
| [SpawnWithParametersEx](sm-workflow-spawnwithparametersex.md) | Cria uma instância de fluxo de trabalho a partir de um modelo e invoca o método [StartWithParameters](sm-workflow-startwithparameters.md) ou [SimulateWithParameters](sm-workflow-simulatewithparameters.md) nessa instância. |
| [Start](sm-workflow-start.md) | Inicia ou reinicia a execução de um workflow. |
| [StartWithParameters](sm-workflow-startwithparameters.md) | Inicia um fluxo de trabalho e fornece parâmetros a ele. |
| [Stop](sm-workflow-stop.md) | Interrompe um fluxo de trabalho em andamento. |
| [Ativação](sm-workflow-wakeup.md) | Força o processamento avançado de todas as tarefas pendentes. |
| [TarefaDeAtivação](sm-workflow-wakeuptask.md) | Força o processamento avançado de uma ou mais tarefas pendentes. |

## Métodos genéricos

| Método | Descrição |
| --- | --- |
| [criar](f-create.md) | Cria uma nova entidade correspondente a um determinado esquema. |
| [carregar](f-load.md) | Carrega e retorna uma entidade correspondente a um determinado esquema e chave. |
| [salvar](m-entity-save.md) | Salva uma entidade no banco de dados. |
