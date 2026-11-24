---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 58%
---
# tarefa

Processos em lote executados no servidor de aplicativos

## Métodos

| Método | Descrição |
| --- | --- |
| [Cancelar](sm-job-cancel.md) | Cancelar um processo |
| [CheckIfJobInProcess](sm-job-checkifjobinprocess.md) | Verifique se o processo ainda está em execução |
| [Executar](sm-job-execute.md) | Executa um processo de forma síncrona (nesse modo, as informações de progresso e o cancelamento não estão disponíveis). |
| [ArquivosExistem](sm-job-filesexist.md) | Verifica se os arquivos já existem no servidor (como arquivos ou na tabela de recursos). |
| [GetJobsInProcess](sm-job-getjobsinprocess.md) | Retorna os processos não externos em execução no momento |
| [ObterStatus](sm-job-getstatus.md) | Obter informações sobre o progresso do processamento do trabalho. Aviso: essa API não garante o retorno de uma lista de entradas de log exclusivas (o chamador precisa desduplicá-las usando a ID ). |
| [HasWarning](sm-job-haswarning.md) | Consulta se foram gerados avisos ou erros para este processo |
| [Pause](sm-job-pause.md) | Pausar um processo |
| [Enviar](sm-job-submit.md) | Envia um processo para processamento assíncrono |
| [EnviarDoModelo](sm-job-submitfrommodel.md) | Envia um processo a partir de um modelo |
| [EnviarChamadaSoap](sm-job-submitsoapcall.md) | Envia um processo para processamento assíncrono |
| [WaitJobCancelled](sm-job-waitjobcancelled.md) | Aguardando o cancelamento do processo |

## Métodos genéricos

| Método | Descrição |
| --- | --- |
| [criar](f-create.md) | Cria uma nova entidade correspondente a um determinado esquema. |
| [carregar](f-load.md) | Carrega e retorna uma entidade correspondente a um determinado esquema e chave. |
| [salvar](m-entity-save.md) | Salva uma entidade no banco de dados. |
