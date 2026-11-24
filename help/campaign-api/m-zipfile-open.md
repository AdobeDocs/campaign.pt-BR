---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%
---
# open

Carrega um arquivo existente.

```text
open ()
```

## Parâmetros

Nenhum.

## Valor de retorno

Nenhum.

## Observações

No caso de um arquivo existente, você deve primeiro chamar o método ⌐[fileCount](p-zipfile-filecount.md) para recuperar o número de arquivos ou [getEntry()](m-zipfile-getentry.md) para extrair um arquivo. O método gera uma exceção se o arquivo não existir ou se ele não for um arquivo válido.

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
