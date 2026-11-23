---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%
---
# serverPort

Retorna o número da porta usada para contatar o servidor.

```text
serverPort
```

## Observações

Exemplo: o serverPort do seguinte URL:

```javascript
http://adobe.com:8080/nms/test.jst
```

retorna a seguinte cadeia de caracteres:

```javascript
8080
```

O serverPort do seguinte URL:

```javascript
http://adobe.com/nms/test.jst
```

retorna a seguinte cadeia de caracteres:

```javascript
80
```

## Recursos

**Propriedade da classe:** [HttpServletRequest](c-httpservletrequest.md)

**Somente leitura:**

Sim

**Disponível em:**

* JSSP
* WebApp
