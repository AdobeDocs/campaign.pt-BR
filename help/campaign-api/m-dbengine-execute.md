---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# executar

Executa um comando SQL.

```text
execute (command [, value1, ... ])
```

## Parâmetros

**comando** comando SQL.

**value1, ...** Variáveis do comando.

## Valor de retorno

O número de registros atualizados ou inseridos, se aplicável, ao comando executado; caso contrário, zero.

## Observações

As variáveis são usadas para substituir os parâmetros do comando. O tipo de variável deve corresponder ao tipo declarado no comando. Os tipos são os seguintes:

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

Os parâmetros substitutos a seguir são substituídos automaticamente por um valor e não exigem uma variável associada.

* $(id) gera um identificador
* $(id:NmsTrackingLogId) Gera um identificador graças a uma sequência específica
* $(curdate) Data e hora atuais

O operador precisa de direitos &#39;sql&#39; para usar esta função, caso contrário, uma exceção será gerada.

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
