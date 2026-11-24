---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%
---
# carregar

> Aviso:
>
> O acesso por meio de APIs de arquivo é limitado a **var**, **sftp** e pastas temporárias do Adobe Campaign.

Carrega e retorna uma entidade correspondente a um determinado esquema e chave.

```text
load (key)
```

## Parâmetros

**chave** Uma cadeia de caracteres correspondente à chave da entidade.

## Valor de retorno

Retorna a entidade no formato de um objeto JavaScript.

## Observações

load não é uma função global, mas um método de esquema. Para chamá-lo, você deve prefixá-lo pelo esquema desejado. Por exemplo:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

As propriedades e subpropriedades desse objeto podem ser modificadas à vontade. Diferentemente do método [get()](f-get.md), o documento não é salvo automaticamente no banco de dados. Você deve chamar o método [save()](m-entity-save.md) no objeto. Se a entidade não for encontrada no banco de dados, será um erro e o script será interrompido.

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
