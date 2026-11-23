---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 11%
---
# queryString

Retorna a parte do URL da consulta que corresponde aos parâmetros.

```text
queryString
```

## Observações

Exemplo: a queryString do seguinte URL:

```javascript
      http://adobe.com/nms/test.jst?id=1234&param=dummy#aFragment
```

retorna a seguinte cadeia de caracteres:

```javascript
id=1234&param=dummy
```

## Recursos

**Propriedade da classe:** [HttpServletRequest](c-httpservletrequest.md)

**Somente leitura:**

Sim

**Disponível em:**

* JSSP
* WebApp
