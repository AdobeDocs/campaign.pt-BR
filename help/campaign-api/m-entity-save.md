---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 31%
---
# save

Salva uma entidade no banco de dados.

```text
save ()
```

## Parâmetros

Nenhum.

## Valor de retorno

Nenhum.

## Observações

Exemplo:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.label = "Diffusion 12345"
delivery.save()
```

## Recursos

**Método da classe:** [Entidade](c-entity.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
