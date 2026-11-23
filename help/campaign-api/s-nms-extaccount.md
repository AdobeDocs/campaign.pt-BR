---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 53%
---
# extAccount

Definição de contas externas (email, SMS...) usado pelos módulos

## Métodos

| Método | Descrição |
| --- | --- |
| [CriarEsquemaFDAS](sm-extaccount-createfdaschema.md) | Cria o esquema de trabalho no banco de dados |
| [DeclareTableSpaces](sm-extaccount-declaretablespaces.md) | Declara as opções, necessárias para usar tablespaces específicos no banco de dados remoto acessível por meio da conta externa, no banco de dados do Adobe Campaign. |
| [ImplantarFunçõesSQL](sm-extaccount-deploysqlfunctions.md) | Implanta as funções exigidas pelo FDA do Adobe Campaign no servidor RDBMS remoto |
| [ContaDeTeste](sm-extaccount-testaccount.md) | Executa um teste de conexão |

## Métodos genéricos

| Método | Descrição |
| --- | --- |
| [criar](f-create.md) | Cria uma nova entidade correspondente a um determinado esquema. |
| [carregar](f-load.md) | Carrega e retorna uma entidade correspondente a um determinado esquema e chave. |
| [salvar](m-entity-save.md) | Salva uma entidade no banco de dados. |
