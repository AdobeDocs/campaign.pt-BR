---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 74%
---
# session

Sessões do servidor de aplicativos

## Métodos

| Método | Descrição |
| --- | --- |
| [ApplyDuplicateRules](sm-session-applyduplicaterules.md) | Aplica as configurações de duplicação (incluindo valores padrão) ao documento especificado |
| [TokenLogonPortador](sm-session-bearertokenlogon.md) | token de conexão |
| [AlterarSenha](sm-session-changepassword.md) | Alterar senha atual |
| [DeleteCollection](sm-session-deletecollection.md) | Excluir uma lista de entidades com base em uma condição |
| [Dif](sm-session-diff.md) | Retorna a versão atual e a versão original de um documento. |
| [Duplicar](sm-session-duplicate.md) | Cria um novo documento a partir de um documento de origem |
| [DuplicarPara](sm-session-duplicateto.md) | Duplica um novo documento a partir de um documento de origem para uma determinada pasta |
| [DuplicateWithMappingId](sm-session-duplicatewithmappingid.md) | Duplica um novo documento a partir do documento de origem com o mapeamento de ID |
| [Criptografar](sm-session-encrypt.md) | Criptografa a string de caracteres com a chave de instância. |
| [EncryptServerPassword](sm-session-encryptserverpassword.md) | Criptografa a string de caracteres com a chave do servidor. |
| [FormatDataPolicy](sm-session-formatdatapolicy.md) | Aplica uma transformação à cadeia de caracteres de acordo com a política de dados transmitida como um parâmetro. Deixa a string inalterada em caso de falha. |
| [GetActiveApplicationMenus](sm-session-getactiveapplicationmenus.md) | Retorna um documento contendo os menus dos aplicativos habilitados para o logon atual |
| [GetCnxInfo](sm-session-getcnxinfo.md) | Recupera informações das conexões atuais. |
| [GetDefaultEntity](sm-session-getdefaultentity.md) | Retorna um documento contendo uma entidade vazia com seus valores padrão |
| [GetDirtyCacheEntities](sm-session-getdirtycacheentities.md) | Retornar entidades em cache inadequadas |
| [GetEntityIfMoreRecent](sm-session-getentityifmorerecent.md) | Carregar uma entidade se sua chave MD5 for diferente da fornecida como um parâmetro |
| [GetImages](sm-session-getimages.md) | Carregar uma lista de imagens |
| [GetNewIds](sm-session-getnewids.md) | Coleta uma lista de identificadores de chaves internas para o banco de dados. |
| [GetNewIdsEx](sm-session-getnewidsex.md) | Obtém uma lista dos identificadores exclusivos do banco de dados, com um nome de sequência. |
| [GetOption](sm-session-getoption.md) | Retorna o valor de uma opção armazenada no banco de dados. |
| [GetPkList](sm-session-getpklist.md) | Obter a lista de identificadores de instância |
| [GetServerTime](sm-session-getservertime.md) | Retorna a data e a hora do servidor |
| [GetUserInfo](sm-session-getuserinfo.md) | Informações sobre o operador atual |
| [HashPassword](sm-session-hashpassword.md) | Hash de uma senha com a chave do servidor. |
| [ImportCollection](sm-session-importcollection.md) | Atualizar uma lista de entidades usando uma importação |
| [EliminarSessão](sm-session-killsession.md) | Fecha a sessão especificada |
| [Carregar](sm-session-load.md) | Carregar a entidade |
| [CarregarComoTexto](sm-session-loadastext.md) | Recuperar conteúdo da entidade em formato de texto |
| [LoadIfExists](sm-session-loadifexists.md) | Carregar a entidade, se ela existir |
| [Logoff](sm-session-logoff.md) | Fechar sessão atual |
| [Logon](sm-session-logon.md) | Abre uma sessão |
| [NovaInstância](sm-session-newinstance.md) | Criação de novo documento, pré-inicializado, mas não salvo |
| [Remover](sm-session-remove.md) | Excluir entidade |
| [ServerShutdown](sm-session-servershutdown.md) | Solicita o desligamento do servidor |
| [DefinirValoresPadrão](sm-session-setdefaultvalues.md) | Corrigir valores por padrão com base em xpath |
| [DefinirPadrões](sm-session-setdefaults.md) | Definir valores padrão |
| [CnxTeste](sm-session-testcnx.md) | Testa a conexão. |
| [Write](sm-session-write.md) | Atualizar uma entidade |
| [WriteCollection](sm-session-writecollection.md) | Atualizar uma lista de entidades |

## Métodos genéricos

| Método | Descrição |
| --- | --- |
| [criar](f-create.md) | Cria uma nova entidade correspondente a um determinado esquema. |
| [carregar](f-load.md) | Carrega e retorna uma entidade correspondente a um determinado esquema e chave. |
| [salvar](m-entity-save.md) | Salva uma entidade no banco de dados. |
