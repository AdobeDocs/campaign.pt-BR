---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 15%
---
# batchDelete

Exclui os registros de uma tabela por pacotes.

```text
batchDelete (table, pk [, where ])
```

## Parâmetros

**tabela** nome SQL da tabela.

**pk** Nome do campo usado como chave primária.

Condição de filtragem de registros SQL **where**.

## Valor de retorno

Nenhum.

## Observações

Exemplo:

```javascript
      engine.batchDelete("NmsRecipient", "iRecipientId", "sName IS NULL")
```

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
