---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 9%
---
# getDBMSType

Retorna o tipo de servidor do banco de dados.

```text
getDBMSType ( [name ] [, checkIfUpdated ])
```

## Parâmetros

**nome** Nome da fonte de dados.

**checkIfUpdated** Verifique se o esquema foi atualizado no cache. Nenhum impacto se o schema já estiver instanciado no script.

## Valor de retorno

Uma string de texto que contém o tipo de servidor do banco de dados.

## Observações

Se a fonte de dados não for especificada, a função usará &#39;nms:default&#39; por padrão. A fonte de dados deve existir, caso contrário, uma exceção será gerada.

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
