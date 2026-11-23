---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 2%
---
# aguardar

Aguarda um sinal.

```text
wait (timeout)
```

## Parâmetros

**tempo limite** Tempo de espera em milissegundos.

## Valor de retorno

Um valor booleano a true se um sinal for recebido antes da expiração do tempo de espera.

## Observações

O sinal é emitido pelos métodos SOAP [Wakeup](sm-workflow-wakeup.md) e [WakeupTask](sm-workflow-wakeuptask.md). O protocolo usado (UDP) não garante a recepção da mensagem. Esse sinal só é útil para executar uma operação mais rapidamente. Aviso: esse sinal nunca será recebido em um subworkflow. Exemplo: este é um exemplo típico de uso: um loop processa operações provenientes de uma fila (poll()) e, em seguida, aguarda uma certa quantidade de tempo entre cada operação. Um atraso adicional é adicionado para forçar a passivação do workflow.

```javascript
var lifetime = 30 * 60 * 1000 // 30 minutes
var frequency = 30 * 1000 // 30 seconds
var start = new Date().getTime()
while( new Date().getTime() - start < lifetime )
{
  poll()
  task.wait(frequency)
}
 
```

## Recursos

**Método de classe:** [WorkflowTask](c-workflowtask.md)

**Disponível em:**

* Fluxo de trabalho
