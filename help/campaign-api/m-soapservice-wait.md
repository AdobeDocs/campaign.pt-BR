---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%
---
# aguardar

Aguarda o fim de uma lista de consultas assíncronas do SOAP.

```text
wait (requests)
```

## Parâmetros

**solicitações** Uma tabela de consultas.

## Valor de retorno

Nenhum.

## Observações

A função não se aplica a um serviço, mas é uma função do compartimento SoapService. Exemplo:

```javascript
...
var req = service.start(1234, "GetOption", sessionToken, "XtkDatabaseId")

// Do some stuff here

// Wait until the end of the request
SoapService.wait( [req] )
```

Quando o query for concluído, ele será automaticamente excluído da lista. Isso significa que quando a função retornar o controle, a tabela transmitida como parâmetro estará vazia. A lista pode ser modificada pela função [complete](p-soapservice-complete.md): por exemplo, é possível iniciar uma nova consulta e adicioná-la à lista.

## Recursos

**Método de classe:** [SoapService](c-soapservice.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Mensagem de entrega
* Regra de tipologia
* Importação
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
