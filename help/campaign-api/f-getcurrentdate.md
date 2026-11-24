---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# getCurrentDate

Retorna a data atual do servidor de banco de dados.

```text
getCurrentDate ()
```

## Parâmetros

Nenhum.

## Valor de retorno

A data atual do servidor de banco de dados.

## Observações

Exemplo:

```javascript
      date = formatDate(getCurrentDate(),"%4Y/%2M/%2D %02H:%02N:%02S")
```

Para obter mais informações sobre a função formatDate(), consulte [formatDate(date, format)](f-formatdate.md)

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
