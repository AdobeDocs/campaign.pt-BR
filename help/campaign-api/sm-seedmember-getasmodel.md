---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# getAsModel

```text
XML parentOut = getAsModel ( String refIdName, Number refIdValue, XML selection, XML parentIn )
```

## Parâmetros

Atributo **refIdName** que contém o identificador da entidade a ser associada (por exemplo, &#39;delivery-id&#39;)

**refIdValue** Identificador da entidade a ser associada (valor de &#39;refIdName&#39;)

**selection** Elemento que contém os identificadores de modelo selecionados

Elemento **parentIn** que contém os seed addresses existentes

## Retornar valor(es)

**parentOut** retorna o elemento com os novos modelos adicionados

## Recursos

**Esquema:** [nms:seedMember](s-nms-seedmember.md)

**Estático:**

Sim
