---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 12%
---
# logon

Altera o contexto de execução do script para o logon atual.

```text
logon (sessionToken)
```

```text
logon (login, password)
```

```text
logon (context)
```

## Parâmetros

**sessionToken** O token de sessão a ser usado.

**logon** O logon de operador a ser usado.

**senha** A senha do operador. A senha pode ser uma string vazia se o login atual tiver direitos de &quot;administrador&quot;.

**contexto** Um objeto que representa um logon, retornado por uma chamada anterior ao logon.

## Valor de retorno

Retorna um objeto que corresponde ao logon anterior. Isso permite restaurar o logon anterior ao passar esse parâmetro para a função de logon.

## Observações

Exemplo:

```javascript
var oldContext = logon("jdoe", "")

// ...

logon(oldContext)
```

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
