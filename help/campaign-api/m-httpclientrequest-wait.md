---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# aguardar

Aguarda até o fim de uma lista de consultas assíncronas.

```text
wait (requests,waitAll)
```

## Parâmetros

**solicitações** Uma tabela de consultas.

**waitAll** Booleano (por padrão true), aguarde a conclusão de todas as solicitações da lista de consulta. Quando definida como false, se pelo menos uma solicitação for concluída, a função sairá do loop de escuta.

## Valor de retorno

Nenhum.

## Observações

A função não se aplica a uma consulta, mas é uma função do compartimento HttpClientRequest. Exemplo:

```javascript
var req = new HttpClientRequest("http://www.adobe.com/br/")
req.complete = function(req, context, status) { logInfo(status) }
req.execute(false, true)

HttpClientRequest.wait( [req] )
```

Uma consulta só poderá ser adicionada à lista se for assíncrona e se a chamada [execute](m-httpclientrequest-execute.md) não tiver gerado uma exceção. Quando o query for concluído, ele será automaticamente excluído da lista. Isso significa que quando a função retornar o controle, a tabela transmitida como parâmetro estará vazia. A lista pode ser modificada pela função [complete](p-httpclientrequest-complete.md): por exemplo, é possível iniciar uma nova consulta e adicioná-la à lista.

## Recursos

**Método de classe:** [HttpClientRequest](c-httpclientrequest.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
