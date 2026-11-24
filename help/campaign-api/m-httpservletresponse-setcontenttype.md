---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 17%
---
# setContentType

Altera o tipo de documento da resposta.

```text
setContentType (name)
```

## Parâmetros

**nome** tipo MIME do documento.

## Valor de retorno

Nenhum.

## Observações

Exemplo:

```javascript
      response.setContentType("text/html;charset=ISO-8859-1")
```

## Recursos

**Método de classe:** [HttpServletResponse](c-httpservletresponse.md)

**Disponível em:**

* JSSP
* WebApp
