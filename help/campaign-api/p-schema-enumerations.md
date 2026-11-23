---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 27%
---
# enumerações

Retorna a tabela que contém a lista de [enumerações](c-enumeration.md) definidas neste esquema.

```text
enumerations
```

## Observações

Exemplo:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var e in schema.enumerations)
{
  logInfo(e.name)
}
```

## Recursos

**Propriedade da classe:** [Esquema](c-schema.md)

**Somente leitura:**

Sim

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
