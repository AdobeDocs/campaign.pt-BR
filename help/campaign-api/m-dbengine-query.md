---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 4%
---
# consulta

Executa uma consulta SQL tipo SELECT.

```text
query (command [, value1, ... ])
```

## Parâmetros

**comando** comando SQL.

**value1, ...** Variáveis do comando.

## Valor de retorno

Um cursor que permite a iteração no resultado da query.

## Observações

Aviso: ao contrário do que é declarado na seção Recursos, a função de consulta não está disponível no WebApp. As variáveis substituem os parâmetros do comando. O tipo de variável deve corresponder ao parâmetro declarado no comando. Os seguintes tipos estão disponíveis:

* $(sz) string
* Memorando $(m)
* $(l) long
* $(s) curto(s)
* $(b) byte
* $(d) duplo
* $(f) flutuante
* Carimbo de data e hora $(ts)
* data $(dt)
* $(tm) time
* Período de tempo $(dur)

Os parâmetros de substituição a seguir são substituídos automaticamente por um valor e não precisam de uma variável vinculada.

* $(id) gera um identificador
* $(id:NmsTrackingLogId) Gera um identificador graças a uma sequência específica
* $(curdate) Data e hora atuais

A iteração no cursor ocorre por meio de um &quot;for each&quot; e retorna uma tabela para cada linha recuperada. Cada elemento da tabela corresponde a um campo da query e o tipo de elemento depende do tipo de campo. Exemplo:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)", 1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

Neste exemplo, row\[0\] é um número que coincide com iOperatorId, row\[1\] é uma sequência de caracteres que coincide com sName e row\[2\] é uma data que coincide com tsLastModified. O operador precisa de direitos &#39;sql&#39; para usar esta função, caso contrário, uma exceção será gerada.

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
