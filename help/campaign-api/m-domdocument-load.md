---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 13%
---
# carregar

> Aviso:
>
> O acesso por meio de APIs de arquivo é limitado a **var**, **sftp** e pastas temporárias do Adobe Campaign.

Cria um novo documento de um arquivo XML.

```text
load (filename [, allowEmpty ])
```

## Parâmetros

**filename** Nome do arquivo a ser carregado.

**allowEmpty** Se true, não gerará uma exceção se o arquivo estiver vazio (padrão=false).

## Valor de retorno

Nenhum.

## Observações

Uma exceção será gerada se o arquivo não puder ser carregado ou se o conteúdo do arquivo não for um documento XML válido. Essa função se aplica à classe DOMDocument. Exemplo:

```javascript
var doc = DOMDocument.load("data/test.xml")
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
