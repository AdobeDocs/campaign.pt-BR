---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# readln

Lê uma linha do arquivo de texto.

```text
readln ()
```

## Parâmetros

Nenhum.

## Valor de retorno

A cadeia de caracteres que contém a próxima linha do arquivo ou ⌐null se o final do arquivo for atingido.

## Observações

Exemplo:

```javascript
var f = new File("c:/dummy.xml")
f.open("r", File.CODEPAGE_UTF8)
var line
while( line = f.readln() )
  logInfo(line)
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
