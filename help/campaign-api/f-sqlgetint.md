---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 5%
---
# sqlGetInt

Retorna o número inteiro resultante de uma consulta SQL.

```text
sqlGetInt (query [, value1, ... ])
```

## Parâmetros

**consulta** A consulta SQL.

**value1, ...** Variáveis da consulta SQL.

## Valor de retorno

O valor inteiro que corresponde à consulta.

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

* $(id) gera um identificador
* $(id:NmsTrackingLogId) Gera um identificador usando uma sequência específica
* $(curdate) Data e hora atuais

Usar variáveis não altera o desempenho do Adobe Campaign. A consulta SQL deve selecionar uma única linha e um único campo de tipo de texto. O operador deve ter o direito &#39;sql&#39; para usar essa função, caso contrário, uma exceção será gerada. Exemplo:

```javascript
      var age = sqlGetInt('select sAge from nmsRecipient where sEmail =$(sz) order by tsCreated DESC LIMIT 1', email)
var iRecipientId = sqlGetInt("select irecipientId FROM NmsRecipient WHERE sLastName=$(sz) and tsCreated>$(ts)", strName);
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
