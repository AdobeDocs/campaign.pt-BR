---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 12%
---
# serverName

Retorna o nome do servidor de consulta.

```text
serverName
```

## Observações

Exemplo: o serverName do seguinte URL:

```javascript
      http://adobe.com/br:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

retorna a seguinte cadeia de caracteres:

```javascript
adobe.com
```

## Recursos

**Propriedade da classe:** [HttpServletRequest](c-httpservletrequest.md)

**Somente leitura:**

Sim

**Disponível em:**

* JSSP
* WebApp
