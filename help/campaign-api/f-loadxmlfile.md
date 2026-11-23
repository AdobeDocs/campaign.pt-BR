---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 13%
---
# loadXmlFile

> Aviso:
>
> O acesso por meio de APIs de arquivo é limitado a **var**, **sftp** e pastas temporárias do Adobe Campaign.

Esta função é obsoleta, use [DOMDocument.load()](m-domdocument-load.md). Carrega um arquivo no formato de um objeto de documento XML

```text
loadXmlFile (filename [, noErr ])
```

## Parâmetros

**filename** O nome completo do arquivo a ser carregado.

**noErr** Se verdadeiro, nenhum erro se o arquivo estiver vazio (padrão=falso).

## Valor de retorno

Um documento XML.

## Observações

Essa função oferece suporte à detecção da página de código do arquivo graças à detecção de BOM e ao prólogo XML.

## Recursos

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
