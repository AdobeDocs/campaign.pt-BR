---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 15%
---
# exec

Alias do comando execute. Esta função é obsoleta, use [executar()](m-dbengine-execute.md)

```text
exec (command [, value1, ... ])
```

## Parâmetros

**comando** comando SQL.

**value1, ...** Variáveis do comando.

## Valor de retorno

O número de gravações atualizadas ou inseridas se isso se aplicar ao comando executado, se não for zero.

## Recursos

**Método de classe:** [DBEngine](c-dbengine.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
