---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '30'
ht-degree: 16%
---
# getHeader

Retorna um atributo definido no cabeçalho da consulta.

```text
getHeader (name)
```

## Parâmetros

**nome** Nome do atributo do cabeçalho.

## Valor de retorno

Nenhum.

## Observações

Exemplo:

```javascript
Host: <%= request.getHeader("host") %>
```

## Recursos

**Método de classe:** [HttpServletRequest](c-httpservletrequest.md)

**Disponível em:**

* JSSP
* WebApp
