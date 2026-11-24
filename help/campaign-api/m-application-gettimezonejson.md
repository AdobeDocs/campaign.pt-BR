---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 5%
---
# getTimezoneJson

Retorna uma cadeia de caracteres que é a representação em JSON da lista de diferenças de tempo com o horário UTC e sua data de início em comparação ao período UNIX de um fuso horário.

```text
getTimezoneJson ( [timezone ])
```

## Parâmetros

**fuso horário** O nome do fuso horário para o qual você precisa retornar a lista de diferenças de tempo comparadas com UTC. Cada diferença de tempo está vinculada a uma data de início aplicável até a próxima data de início. Se nenhum valor for retornado, o usará o fuso horário padrão do operador.

## Valor de retorno

Retorna uma cadeia de caracteres que é a representação em JSON das diferenças de tempo a serem aplicadas com base nas datas. A sequência JSON retornada é avaliada em uma tabela de {startDate, offset} casais. A cadeia de caracteres retornada tem o seguinte formato:

```javascript
[
  {"startDate" : -1855958901000, "offset" : 0},
  {"startDate" : -1689814800000, "offset" : 3600000}
]
```

* startDate é a hora Posix a partir da qual o lapso se aplica.
* offset é o valor em milissegundos da diferença de tempo com UTC. Por exemplo, UTC+02:00 é igual a 7200000.

## Observações

getTimezoneJson é chamado por meio da instância do aplicativo.

```javascript
var tzList = eval(application.getTimezoneJson());
```

## Recursos

**Método da classe:** [Aplicativo](c-application.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
