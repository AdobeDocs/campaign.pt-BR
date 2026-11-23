---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 23%
---
# hasPackage

Testa se um pacote está instalado.

```text
hasPackage (name)
```

## Parâmetros

**name** Nome completo do pacote.

## Valor de retorno

True se o pacote estiver instalado.

## Observações

Exemplo:

```javascript
var hasMRM = application.hasPackage("nms:mrm")
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
