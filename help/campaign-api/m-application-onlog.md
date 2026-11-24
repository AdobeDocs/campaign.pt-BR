---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 6%
---
# onLog

Adiciona ou exclui uma função de interceptação para as mensagens gravadas no diário

```text
onLog ( [function ])
```

## Parâmetros

**função** A função de interceptação a ser adicionada. Se esse parâmetro for deixado de fora, a função adicionada mais recentemente será excluída.

## Valor de retorno

Nenhum.

## Observações

A função adicionada mais recentemente é chamada primeiro. A função assume um objeto com as seguintes propriedades como argumento:

* type (Number) - O tipo de mensagem (0=erro, 1=aviso, 2=informações, 3=status, 4=detalhado)
* code (Number) - O código de erro (0 se não for um erro)
* object (String) - objeto vinculado à mensagem (não usado)
* mensagem (String) - A mensagem

A função deve retornar um valor booleano. O valor true impedirá que qualquer função de interceptação seguinte receba a mensagem. A função é protegida contra a reentrada: não interceptará mensagens que escreveu no próprio diário. Exemplo:

```javascript
var file = new File("c:/temp/log.txt")
file.open("w")

// Add a new log handler
application.onLog(function(log) {
  file.writeln(log.type.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the log handler
application.onLog()

// This message won't be caught
logInfo("Finished.")

file.close()
```

## Recursos

**Método da classe:** [Aplicativo](c-application.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
