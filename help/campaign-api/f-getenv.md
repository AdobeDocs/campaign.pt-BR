---
source-git-commit: 77f8182ea5b1fda08206021a164b2e0ff827890a
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# getEnv

>[!WARNING]
>
>Essa função está disponível para um ambiente no local.

>[!NOTE]
>
>Você pode desabilitar esta função passando a opção **XtkSecurity\_Disable\_GetSetEnv** para **true**.

Retorna o valor de uma variável de ambiente.

```text
getEnv (name [, default ])
```

## Parâmetros

**nome** Nome da variável.

**padrão** Valor padrão a ser usado se a variável de ambiente não for encontrada.

## Valor de retorno

O valor da variável.

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
