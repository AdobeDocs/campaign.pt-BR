---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 15%
---
# parâmetros

Retorna os parâmetros de consulta.

```text
parameters
```

## Observações

A propriedade parameters retorna um objeto com propriedades que correspondem a um parâmetro da query. Exemplo:

```javascript
var parameters = request.parameters
for(var name in parameters)
{
var value = parameters[name]
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
