---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 25%
---
# copyTo

Copia um arquivo.

```text
copyTo (fileName)
```

## Parâmetros

**fileName** Nome do arquivo ou pasta de destino (deve ser um caminho completo).

## Valor de retorno

Nenhum.

## Observações

Exemplos:

```javascript
var f = new File("c:/file.txt")
f.copyTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.copyTo("c:/dir/")
```

## Recursos

**Método da classe:** [Arquivo](c-file.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
