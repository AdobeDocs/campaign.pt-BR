---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%
---
# criar

Cria uma nova entidade correspondente a um determinado esquema.

```text
create ( [content ])
```

## Parâmetros

**conteúdo** Uma cadeia de caracteres opcional correspondente ao XML da entidade a ser criada.

## Valor de retorno

Retorna a entidade no formato de um objeto JavaScript.

## Observações

create não é uma função global, mas um método de esquema. Para chamá-lo, você deve prefixá-lo pelo esquema desejado. Por exemplo:

```javascript
var recipient = NLWS.nmsRecipient.create(
      {recipient: {
        email: "support@adobe.com", 
        lastName: "Adobe", 
        firstName: "Support"}})
recipient.save()
```

O documento não é salvo automaticamente no banco de dados. Você deve usar o método ⌐⌐[save()](m-entity-save.md) na entidade.

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
