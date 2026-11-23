---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%
---
# PostEvent

Gera um evento de qualquer tipo de atividade.

```text
PostEvent ( String workflowId, String activity, String transition, XML parameters, Boolean complete )
```

## Parâmetros

**workflowId** Identificador ou nome interno do fluxo de trabalho.

**atividade** O nome da atividade a partir da qual o evento começa

**transição** O nome da transição a ser ativada. Se esse nome estiver vazio, o evento será emitido na primeira transição válida (os eventos de tipo de expiração são ignorados).

**parâmetros** Os parâmetros do evento na forma de um elemento XML. O nome do elemento deve ser variáveis. Se não quiser transmitir uma variável, você pode usar um elemento vazio &lt;variables/> ou uma string vazia &quot;&quot;.

**concluído** Todas as tarefas pendentes da atividade especificada foram concluídas.

## Retornar valor(es)

Nenhum.

## Observações

* O comando é executado no modo assíncrono e não tem efeito imediato após o retorno do método.
* O workflow desejado deve ser iniciado quando esse método é chamado. Se não for iniciado, um erro será gravado no arquivo de log correspondente.
* Se o workflow desejado for suspenso quando o método for chamado, o comando será deixado na fila até que o workflow seja retomado.
* Não há restrição para a atividade: não é necessário que ela tenha uma tarefa em andamento ou até mesmo concluída.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
