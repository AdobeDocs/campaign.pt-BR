---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 10%
---
# getEntry

Extrai um arquivo do arquivo.

```text
getEntry (filename)
```

## Parâmetros

**filename** Nome do arquivo no arquivo morto.

## Valor de retorno

O ⌐ [MemoryBuffer](c-memorybuffer.md) que contém o conteúdo do arquivo.

## Observações

O arquivo morto deve ter sido aberto com o método ⌐[open()](m-zipfile-open.md) antes que você possa usar esse método. Caso contrário, uma exceção será gerada. Exemplo: o exemplo a seguir extrai o arquivo dir/content.xml de um arquivo e o salva na pasta /tmp/.

```javascript
var zip = new ZipFile("/tmp/archive.zip")
zip.open()

var content = zip.getEntry("dir/content.xml")
content.save("/tmp/content.xml")

zip.dispose()
content.dispose()
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
