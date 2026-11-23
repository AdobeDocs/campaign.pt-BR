---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 15%
---
# queryWithTypes

Executa uma consulta SQL tipo SELECT com especificação de tipo de coluna.

```text
queryWithTypes (command, types [, value1, ... ])
```

## Parâmetros

**comando** comando SQL.

**tipos** Tabela contendo o tipo de coluna.

**value1, ...** Variáveis de comando.

## Valor de retorno

Um cursor que permite a iteração no resultado da consulta.

## Observações

Aviso: ao contrário do que é declarado na seção Recursos, a função queryWithTypes não está disponível no WebApp. A função é idêntica à [consulta](m-dbengine-query.md), com o tipo de colunas adicionado. Na maioria dos casos, o tipo de coluna não é usado, pois pode ser inferido automaticamente. É por isso que a [consulta](m-dbengine-query.md) deve ser preferida. No entanto, em alguns casos, especialmente com colunas de Oracle e tipo de data, pode ser necessário explicitar o tipo. Os tipos de coluna são cadeias de caracteres na seguinte lista:

* sequência de caracteres
* data e hora
* data
* tempo
* intervalo de tempo
* duplo
* flutuante
* booleano
* byte
* curto
* longo
* int64
* nota
* blob
* link
* compartimento

Exemplo:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)",
                     ["long", "string", "datetime"],
                     1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

O operador deve ter direitos &#39;sql&#39; para usar essa função, caso contrário, uma exceção será gerada.

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
