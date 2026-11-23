---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 33%
---
# BuildPreviewFromId

Criou a visualização de um conteúdo para entrega ou de uma linha do arquivo de saída (no modo externo).

```text
[ XML preview, XML queryResult ] = BuildPreviewFromId ( Number deliveryId, XML params ) const
```

## Parâmetros

**deliveryId** ID de Entrega.

**params** Condição de filtragem de destinatário (@filter = &#39;@id = 5673&#39;), identificador de conteúdo (@content = &#39;html&#39;, &#39;text&#39;, &#39;sms&#39;, &#39;webContent1&#39;, &#39;outputFile&#39;...), @targetPart = 1345686...

## Retornar valor(es)

**visualização** Retorna todos os parâmetros da visualização gerada.

**queryResult** Retorna os dados carregados para calcular a visualização.

## Exemplo

```javascript
var res = nms.delivery.BuildPreviewFromId(
                           deliveryId,
                           {params: {content: "html", filter: "@id=1234"}})
var preview     = res[0]
var queryResult = res[1]
```

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
