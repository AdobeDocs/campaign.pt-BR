---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 17%
---
# ArquivoZip

> Aviso:
>
> O acesso por meio de APIs de arquivo é limitado a **var**, **sftp** e pastas temporárias do Adobe Campaign.

Cria um novo objeto Zip associado a um arquivo.

```text
ZipFile (filename)
```

## Parâmetros

**filename** O nome do arquivo a ser carregado ou criado.

## Valor de retorno

Nenhum.

## Observações

Exemplo:

```javascript
var zip = new ZipFile("/tmp/archive.zip")
```

## Recursos

**Método de classe:** [ZipFile](c-zipfile.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
