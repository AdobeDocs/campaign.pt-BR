---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 14%
---
# EntityCollection (Classe)

Representa uma coleção de uma entidade.

Esse objeto não pode ser instanciado diretamente. Você deve usar os métodos create(), get() ou load().

Os elementos de uma coleção podem ser enumerados com `for` ou `for each`. Este exemplo mostra uma lista discriminada de arquivos vinculados a uma ação de entrega.

```text
var delivery = NLWS.nmsDelivery.load("12345") for each(var attach in delivery.attachment) logInfo(attach.label)
```

## Métodos

| Método | Descrição |
| --- | --- |
| [adicionar](m-entitycollection-add.md) | Adiciona uma nova entidade à coleção. |
| [remover](m-entitycollection-remove.md) | Exclui uma entidade da coleção. |
| [removerTudo](m-entitycollection-removeall.md) | Exclui todas as entidades da coleção. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [comprimento](p-entitycollection-length.md) | Retorna o número da entidade da coleção. |

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
