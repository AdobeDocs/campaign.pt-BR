---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 10%
---
# esquema

Retorna o nome do protocolo usado (HTTP, HTTPS etc.) para acessar esta página.

```text
scheme
```

## Observações

Exemplo: o esquema do seguinte URL:

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

retorna a seguinte cadeia de caracteres:

```javascript
http
```

## Recursos

**Propriedade da classe:** [HttpServletRequest](c-httpservletrequest.md)

**Somente leitura:**

Sim

**Disponível em:**

* JSSP
* WebApp
