---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 11%
---
# loadLibrary

Carrega uma biblioteca JavaScript.

```text
loadLibrary (filename [, boolean ])
```

## Parâmetros

**filename** O nome da biblioteca JavaScript a ser carregada.

**booleano** Habilita ou desabilita o cache de carga. Por padrão, é verdadeiro.

> Observação: quando o parâmetro é definido como false, é necessário usar a função logon() antes da chamada loadLibrary para ser autenticada como operador.

## Valor de retorno

Nenhum.

## Observações

O cache é ativado por padrão. Se o cache estiver desabilitado, o banco de dados será consultado para cada chamada. Esta query permite carregar a versão mais recente da biblioteca. Exemplo: loadLibrary(&#39;xtk:shared/nl.js&#39;)

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
