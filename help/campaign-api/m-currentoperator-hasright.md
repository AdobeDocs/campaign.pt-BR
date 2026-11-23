---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 23%
---
# hasRight

Testa se o operador tem um direito nomeado específico.

```text
hasRight (name)
```

## Parâmetros

**nome** Nome correto.

## Valor de retorno

True se o operador tiver esse direito.

## Observações

Exemplo:

```javascript
      var hasAdminRight = application.operator.hasRight("admin")
```

## Recursos

**Método de classe:** [CurrentOperator](c-currentoperator.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
