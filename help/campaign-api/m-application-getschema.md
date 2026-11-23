---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 9%
---
# getSchema

Retorna um mapeamento para um esquema do Adobe Campaign ou nulo se o esquema não existir.

```text
getSchema (name [, checkIfUpdated ])
```

## Parâmetros

**name** Nome completo do esquema.

**checkIfUpdated** Verifique se o esquema foi atualizado no cache. Nenhum impacto se o schema já tiver sido instanciado no script.

## Valor de retorno

Um mapeamento de esquema (consulte o objeto [Esquema](c-schema.md)) ou o método inicia uma exceção se nenhum esquema coincidir com o nome.

## Observações

Todos os esquemas instanciados em um script permanecem alocados na memória até o final do script. Exemplo:

```javascript
      var schema = application.getSchema("nms:recipient")
```

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
