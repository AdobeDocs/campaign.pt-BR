---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 15%
---
# nodeValue

Valor do nó. O valor depende do tipo de nó.

```text
nodeValue
```

## Observações

Esta propriedade pode ser acessada com permissões de leitura e gravação. Exemplo para recuperar uma linha de assunto e adicioná-la aos dados adicionais de uma atividade de query em um workflow:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',data), 1, 255)
```

Exemplo para recuperar uma linha de assunto de uma atividade de enriquecimento em um workflow:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',[target/data]), 1, 255)
```

## Recursos

**Propriedade da classe:** [DOMNode](c-domnode.md)

**Somente leitura:**

Sim

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Mensagem de entrega
* Regra de tipologia
* Importação
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
