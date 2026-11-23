---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 14%
---
# descartar

Libera a conexão de todos os recursos vinculados a ela.

```text
dispose ()
```

## Parâmetros

Nenhum.

## Valor de retorno

Nenhum.

## Observações

Uma conexão criada usando o método [application.getConnection()](m-application-getconnection.md) é liberada automaticamente no final do script. Chamar esse método é útil para scripts que podem ter uma longa vida útil.

## Recursos

**Método de classe:** [DBEngine](c-dbengine.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
