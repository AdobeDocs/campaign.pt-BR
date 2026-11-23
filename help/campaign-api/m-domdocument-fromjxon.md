---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 14%
---
# do JXON

Cria um novo documento de um objeto JXON.

```text
fromJXON (obj)
```

## Parâmetros

**obj** Um objeto JXON que representa o documento XML a ser criado.

## Valor de retorno

Nenhum.

## Observações

As funções que transmitem um DOMDocument ou DOMElement como parâmetro também aceitam diretamente um objeto JXON. Não é necessário construir um objeto intermediário usando essa função. Uma exceção será gerada se o objeto não for um objeto JXON válido. Essa função se aplica à classe DOMDocument. Exemplo:

```javascript
var doc = DOMDocument.fromJXON(
    {form : {name: "address", "namespace": "nms", colcount: 2}})
```

## Recursos

**Método de classe:** [DOMDocument](c-domdocument.md)

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
