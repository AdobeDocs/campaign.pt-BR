---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# setEntry

Adiciona ou atualiza um arquivo no arquivo.

```text
setEntry (filename, buffer)
```

## Parâmetros

**filename** Nome do arquivo de origem.

**buffer** MemoryBuffer que contém o arquivo.

## Valor de retorno

Nenhum.

## Observações

O arquivo morto não será efetivamente modificado no disco até que o método [save()](m-zipfile-save.md) seja chamado.

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
