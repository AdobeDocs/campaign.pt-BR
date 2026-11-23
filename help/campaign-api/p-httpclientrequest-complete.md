---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# concluído

Função a ser chamada quando uma consulta assíncrona é concluída.

```text
complete
```

## Observações

A função deve aceitar três argumentos:

* A consulta
* O contexto
* O status: &quot;sucesso&quot;, &quot;erro&quot; ou &quot;tempo limite&quot;

O status &quot;sucesso&quot; significa que uma resposta foi recebida, mas a resposta pode ter qualquer código (200, 404, 503 etc.). O status de &quot;erro&quot; pode apontar para uma interrupção da comunicação de uma resposta mal estruturada. O status &quot;timeout&quot; significa que a conexão não pôde ser estabelecida ou que nenhuma resposta foi recebida dentro do prazo configurado. Exemplo:

```javascript
http.complete = function(req, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + req.response.code)
}
```

## Recursos

**Propriedade da classe:** [HttpClientRequest](c-httpclientrequest.md)

**Somente leitura:**

Não

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
