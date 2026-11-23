---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# logError

Adiciona uma mensagem de erro ao log da instância do fluxo de trabalho e suspende a execução do script.

```text
logError (message)
```

## Parâmetros

**mensagem** A mensagem a ser adicionada ao log.

## Valor de retorno

Nenhum.

## Observações

A tarefa em andamento se comporta como se tivesse ocorrido um erro: um erro é sinalizado e o workflow é suspenso. Portanto, essa função é útil para acionar explicitamente um erro em um workflow e suspendê-lo.

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Mensagem de entrega
* Regra de tipologia
* Importação
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
