---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 9%
---
# onTrace

Adiciona ou exclui uma função de interceptação de mensagem de rastreamento.

```text
onTrace ( [function ])
```

## Parâmetros

**função** A função de interceptação a ser adicionada. Se esse parâmetro for deixado de fora, a função adicionada mais recentemente será excluída.

## Valor de retorno

Nenhum.

## Observações

A função assume um objeto com as seguintes propriedades como argumento:

* gravidade (String) - A gravidade da mensagem (&quot;error&quot;, &quot;warning&quot;, &quot;info&quot;, &quot;status&quot;, &quot;verbose&quot;)
* Tipo (String) - O tipo de mensagem (&quot;log&quot;, &quot;wdbc&quot; etc.)
* mensagem (String) - A mensagem

A função é protegida contra reentrada: ela não interceptará mensagens de rastreamento que ela própria criou. Exemplo:

```javascript
var file = new File("c:/temp/trace.txt")
file.open("w")

// Add a new trace handler
application.onTrace(function(log) {
  file.writeln(log.gravity.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the trace handler
application.onTrace()

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
