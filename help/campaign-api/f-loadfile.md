---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 22%
---
# loadFile

> Aviso:
>
> O acesso por meio de APIs de arquivo é limitado a **var**, **sftp** e pastas temporárias do Adobe Campaign.

Retorna o conteúdo de um arquivo de texto

```text
loadFile (filename [, codePage ])
```

## Parâmetros

**filename** O nome completo do arquivo a ser carregado.

**codePage** Este parâmetro opcional permite que você especifique a codificação de caracteres. Exemplo:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valor de retorno

Uma sequência de caracteres correspondente ao conteúdo do arquivo de texto.

## Observações

Se a codificação de caracteres não for especificada, o padrão do servidor será usado.

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
