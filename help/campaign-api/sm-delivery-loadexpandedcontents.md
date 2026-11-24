---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 38%
---
# CarregarConteúdoExpandido

Carregar uma lista de componentes para pré-processamento com dependências (blocos de personalização, opções, objetos de script adicionais etc.).

```text
XML material = delivery.LoadExpandedContents ( String ids ) const
```

## Parâmetros

**ids** Lista de identificadores de componentes separados por vírgulas (por exemplo, &#39;option\|NmsServer\_URL\|text,includeView\|UnsubscriptionLink\|html&#39;).

## Retornar valor(es)

**material** Retorna o conteúdo como um elemento &#39;material&#39;.

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Não

**Const:**

Sim

**Somente chave:**

Não
