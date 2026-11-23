---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 9%
---
# Operador Atual (Classe)

Objeto que contém informações sobre o operador atual (nome, identificadores, direitos, etc.).

Essa classe tem uma única instância que fornece acesso a determinadas propriedades do servidor do aplicativo. Este singleton pode ser acessado por meio da propriedade da variável global `application`.

Exemplo:

```text
var operator = application.operator logInfo("login: " + operator.login) logInfo("id: " + operator.id) logInfo("description: " + operator.computeString) logInfo("=== Groups ===") for each(var id in operator.groups) logInfo(id) logInfo("=== Rights ===") for each(var right in operator.rights) logInfo(right)
```

## Métodos

| Método | Descrição |
| --- | --- |
| [hasRight](m-currentoperator-hasright.md) | Testa se o operador tem um direito nomeado específico. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [logon](p-currentoperator-login.md) | Retorna o logon do operador atual. |
| [id](p-currentoperator-id.md) | Retorna o identificador interno do operador atual. |
| [computeString](p-currentoperator-computestring.md) | Retorna a cadeia de caracteres de descrição do operador atual. Por padrão, esse é o nome do operador seguido por seu logon. |
| [grupos](p-currentoperator-groups.md) | Retorna a lista de identificadores nos grupos de operadores atuais. |
| [direitos](p-currentoperator-rights.md) | Retorna a lista de direitos do operador atual. |
| [fuso horário](p-currentoperator-timezone.md) | Retorna o nome do fuso horário usado pelo operador atual. |
| [página inicial](p-currentoperator-home.md) | Retorna o nome da pasta raiz do operador atual. |

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
