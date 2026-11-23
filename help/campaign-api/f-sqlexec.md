---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# sqlExec

Executa um script SQL.

```text
sqlExec (query [, value1, ... ])
```

## Parâmetros

**consulta** A consulta SQL.

**value1, ...** Variáveis da consulta SQL.

## Valor de retorno

O número de registros atualizados ou inseridos no caso de um comando SQL UPDATE ou INSERT.

## Observações

As variáveis substituem os parâmetros no comando. O tipo de variável deve corresponder ao parâmetro declarado no comando. Essas variáveis estão disponíveis em uma declaração do tipo &quot;selecionar&quot; ou &quot;atualizar&quot;. Temos os seguintes tipos:

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
* Período de tempo de $(dur) em milissegundos (ms)

Os seguintes parâmetros de substituição (válidos apenas para uma &quot;atualização&quot;) são substituídos automaticamente por um valor e não precisam de uma variável vinculada.

* $(id) gerar um identificador
* $(id:NmsTrackingLogId) gera um identificador usando uma sequência específica
* Data e hora atuais $(curdate)

O operador deve ter o direito &#39;sql&#39; para usar essa função, caso contrário, uma exceção será gerada. Exemplo:

```javascript
      var sql4 = "INSERT INTO Reporting (sClientdesc,sClient) values ('" + client.@description.toString() + "','" + client.@clientCode.toString() +"')";
sqlExec(sql4);
```

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
