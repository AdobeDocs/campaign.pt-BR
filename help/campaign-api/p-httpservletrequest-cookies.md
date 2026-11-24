---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 13%
---
# cookies

Retorna os cookies da query.

```text
cookies
```

## Observações

A propriedade cookies retorna um objeto, com um cookie correspondente para cada uma de suas propriedades. Exemplo:

```javascript
var cookies = request.cookies
for(var name in cookies)
{
var value = cookies[name].value
document.write(name + " : " + value + "<br>")
}
```

## Recursos

**Propriedade da classe:** [HttpServletRequest](c-httpservletrequest.md)

**Somente leitura:**

Sim

**Disponível em:**

* JSSP
* WebApp
