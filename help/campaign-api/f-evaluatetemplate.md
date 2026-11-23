---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 14%
---
# evaluateTemplate

Avalia um modelo do JavaScript (&lt;%= ... %>).

```text
evaluateTemplate (template)
```

## Parâmetros

**modelo** O modelo a ser avaliado.

## Valor de retorno

A sequência de caracteres após substituir as expressões entre &lt;% e %>.

## Observações

Exemplo:

```javascript
      vars.filename = evaluateTemplate(activity.filename)
```

## Recursos

**Disponível em:**

* Fluxo de trabalho
