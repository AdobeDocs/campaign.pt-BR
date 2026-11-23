---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 12%
---
# getNewIds

Retorna uma lista de IDs das chaves do banco de dados interno.

```text
getNewIds (count [, sequence ])
```

## Parâmetros

**count** Número de IDs que o método deve retornar.

**sequência** Nome da sequência a ser usada.

## Valor de retorno

Uma tabela contendo a lista de IDs:

## Observações

Este método é equivalente aos métodos SOAP NLWS.xtkSession.GetNewIds() e NLWS.xtkSession.GetNewIdsEx() enquanto é mais eficiente.

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
