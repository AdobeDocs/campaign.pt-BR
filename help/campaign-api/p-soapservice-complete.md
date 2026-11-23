---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# concluído

Função a ser chamada quando uma consulta assíncrona é concluída.

```text
complete
```

## Observações

A função deve aceitar quatro argumentos:

* O serviço
* O resultado
* O contexto: este é o parâmetro passado para a função [start](m-soapservice-start.md)
* O status

O status pode ter os seguintes valores:

* &quot;sucesso&quot; significa que um resultado foi recebido.
* &quot;erro&quot; pode significar que a comunicação foi interrompida, que a resposta foi mal estruturada ou que ocorreu um erro HTTP.
* &quot;fault&quot; se um erro do SOAP for retornado. Nesse caso, o resultado contém um objeto que descreve o erro.
* &quot;timeout&quot; significa que a conexão não pôde ser estabelecida ou que nenhuma resposta foi recebida dentro do prazo configurado.

Quando o resultado é &quot;success&quot;, o resultado depende do número de parâmetros retornados:

* void se a consulta não retornar nenhum valor
* O valor se a consulta retornar um único parâmetro
* uma tabela se a consulta retornar vários parâmetros

Quando o status é &quot;fault&quot;, o resultado é um objeto que contém as seguintes propriedades:

* message: a mensagem de descrição do erro.
* object: um objeto XML que contém os detalhes do erro.

Exemplo:

```javascript
http.complete = function(result, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + result[0])
}
```

## Recursos

**Propriedade da classe:** [SoapService](c-soapservice.md)

**Somente leitura:**

Não

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
