---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 7%
---
# obter

Carrega e retorna uma entidade correspondente a um determinado esquema e chave.

```text
get ( [key or content ])
```

## Parâmetros

**chave ou conteúdo** Uma cadeia de caracteres correspondente à chave da entidade de conteúdo XML para criar ou iniciar uma nova entidade.

## Valor de retorno

Retorna a entidade no formato de um objeto JavaScript.

## Observações

get não é uma função global, mas um método de esquema. Para chamá-lo, você deve prefixá-lo pelo esquema desejado. Por exemplo:

```javascript
var delivery = NLWS.nmsDelivery.get("12435")
```

As propriedades e subpropriedades desse objeto podem ser modificadas à vontade. O documento é salvo automaticamente no banco de dados quando o script conclui a execução se for modificado. Se não for uma criação e a entidade ainda não estiver no banco de dados, será um erro e o script será interrompido.

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
