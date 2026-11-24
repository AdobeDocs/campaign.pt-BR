---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 23%
---
# remover

Exclui uma entidade da coleção.

```text
remove (index|object)
```

## Parâmetros

**índice\|objeto** Índice da entidade a ser excluída ou a própria entidade.

## Valor de retorno

Nenhum.

## Observações

Exemplos:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.remove(1)
delivery.save()
```

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
var attach = delivery.attachment[1]
delivery.attachment.remove(attach)
delivery.save()
```

## Recursos

**Método de classe:** [EntityCollection](c-entitycollection.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
