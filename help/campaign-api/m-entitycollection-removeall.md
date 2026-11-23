---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 31%
---
# removeAll

Exclui todas as entidades da coleção.

```text
removeAll ()
```

## Parâmetros

Nenhum.

## Valor de retorno

Nenhum.

## Observações

Exemplo:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.removeAll()
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
