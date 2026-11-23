---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%
---
# lista

Lista o conteúdo de um diretório.

```text
list ( [mask ] [, sort ] [, noCase ])
```

## Parâmetros

**mask** A máscara de pesquisa (\* por padrão).

**sort** true para classificar o resultado (false por padrão).

**noCase** true para ignorar a classe ao classificar (false por padrão).

## Valor de retorno

Uma tabela contendo a lista de arquivos ( [Arquivo](c-file.md) ) que correspondem ao caminho e à máscara especificados.

## Observações

O nome do diretório deve terminar com / no Linux e \\ no Windows. Exemplo:

```javascript
var dir = new File("c:\\temp\\")
var files = dir.list("*.*")
for each (var file in files)
  logInfo(file.name)
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
