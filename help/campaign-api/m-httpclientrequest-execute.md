---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 6%
---
# executar

Executa a consulta HTTP.

```text
execute ( [hasProxy ] [, async ] [, reuseaddr ] [, context ] [, timeout ])
```

## Parâmetros

**hasProxy** Booleano definido como verdadeiro se você precisar usar um proxy HTTP. Por padrão, defina como falso.

**async** Booleano definido como verdadeiro se a consulta for assíncrona. Por padrão, defina como falso.

**reuseaddr** Booleano definido como verdadeiro se o soquete subjacente deveria permitir a reutilização de endereços locais. Por padrão, defina como falso.

**context** O contexto é qualquer objeto que será encaminhado para o segundo argumento da função [complete](p-httpclientrequest-complete.md) no caso de uma consulta assíncrona.Por padrão, defina como nulo.

**tempo limite** Tempo de espera máximo em milissegundos no caso de consulta assíncrona. Se esse parâmetro não estiver definido, o tempo de espera será de 5 minutos.

## Valor de retorno

Nenhum.

## Observações

Se a conexão HTTP falhar, uma exceção será gerada. A propriedade [response](p-httpclientrequest-response.md) só se torna válida após uma chamada bem-sucedida para a função execute. Exemplo:

```javascript
          
        var http = new HttpClientRequest("http://www.google.com")
        http.method = "GET"
        // Note: Here, http.response == undefined
        http.execute()
        var response = http.response
      
```

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
