---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# writeln

Grava uma linha de texto no arquivo.

```text
writeln (line)
```

## Parâmetros

**linha** A linha de texto a ser gravada.

## Valor de retorno

Nenhum.

## Observações

Exemplo:

```javascript
var f = new File("c:/file.txt")
f.open("a")
f.writeln("line 1")
f.writeln("line 2")
f.close()
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
