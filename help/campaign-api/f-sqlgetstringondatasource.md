---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 11%
---
# sqlGetStringOnDataSource

Retorna uma string resultante de uma consulta SQL em uma fonte de dados.

```text
sqlGetStringOnDataSource (query, dataSource [, value1, ... ])
```

## Parâmetros

**consulta** A consulta SQL.

**dataSource** A fonte de dados.

**value1, ...** Variáveis da consulta SQL.

## Valor de retorno

A sequência de caracteres de texto que corresponde à consulta.

## Observações

O parâmetro &quot;data source&quot; é definido no [sqlExecOnDataSource(query, dataSource, value1, ...)](f-sqlexecondatasource.md) função As variáveis opcionais definidas como parâmetros desta função são definidas em [sqlGetString(query, value1, ...)](f-sqlgetstring.md)

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
