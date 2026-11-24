---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 16%
---
# getConnection

Retorna uma nova conexão com o servidor de banco de dados.

```text
getConnection ()
```

## Parâmetros

Nenhum.

## Valor de retorno

Uma [conexão](c-dbengine.md) com o servidor de banco de dados.

## Observações

É possível liberar a conexão antes do fim da execução do script usando o método [dispose](m-dbengine-dispose.md).

## Recursos

**Método da classe:** [Aplicativo](c-application.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
