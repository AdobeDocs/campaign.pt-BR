---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 20%
---
# saveFile

> Aviso:
>
> O acesso por meio de APIs de arquivo é limitado a **var**, **sftp** e pastas temporárias do Adobe Campaign.

Salva uma cadeia de caracteres em um arquivo.

```text
saveFile (text, filename [, codePage ])
```

## Parâmetros

**texto** A sequência de texto a ser salva.

**filename** O nome completo do arquivo a ser salvo.

**codePage** Este parâmetro opcional permite que você especifique a codificação de caracteres. Exemplo:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valor de retorno

Nenhum.

## Observações

Se a codificação de caracteres não for especificada, o padrão do servidor será usado.

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
