---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 73%
---
# construtor

Serviços de geração do servidor de aplicativos

## Métodos

| Método | Descrição |
| --- | --- |
| [BuildOutputNavTree](sm-builder-buildoutputnavtree.md) | Mesclar as definições da árvore de navegação encontradas no banco de dados com a definição fornecida no parâmetro. |
| [BuildOutputSchema](sm-builder-buildoutputschema.md) | Gera um esquema a partir de um esquema de origem. |
| [BuildSchema](sm-builder-buildschema.md) | Gera um esquema a partir de um esquema de origem. |
| [BuildSchemaFromId](sm-builder-buildschemafromid.md) | Gera um esquema a partir de um identificador de esquema de origem. |
| [BuildSqlSchemaDiff](sm-builder-buildsqlschemadiff.md) | Gera um documento que descreve as diferenças entre a estrutura real do banco de dados e sua descrição lógica. |
| [BuildUpdateOneSchemaDiff](sm-builder-buildupdateoneschemadiff.md) | Gera um documento que descreve as diferenças entre uma tabela no banco de dados físico e a descrição lógica dessa tabela. |
| [BuildUpdateSchemaDiff](sm-builder-buildupdateschemadiff.md) | Gera um documento que descreve as diferenças entre a estrutura real do banco de dados e sua descrição lógica. |
| [CheckTableExists](sm-builder-checktableexists.md) | Verifica se uma tabela existe no banco de dados |
| [CriarBd](sm-builder-createdb.md) | Criar banco de dados |
| [Avaliar JavaScript](sm-builder-evaluatejavascript.md) | Avaliação do código JavaScript. |
| [EvaluateJavaScriptTemplate](sm-builder-evaluatejavascripttemplate.md) | Avaliação do modelo JavaScript (JST). |
| [ExecSql](sm-builder-execsql.md) | Executar uma instrução SQL |
| [ExecSqlScript](sm-builder-execsqlscript.md) | Executar um script SQL |
| [GenCreateDbDDL](sm-builder-gencreatedbddl.md) | Gera o script SQL usado para criar a estrutura do banco de dados. |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-gencreateorupdateschemasequenceddl.md) | Gera o script SQL usado para criar ou atualizar a sequência do esquema autoPk |
| [GenerateNavTree](sm-builder-generatenavtree.md) | Mescle todas as definições da árvore de navegação e salve o resultado como &quot;xtk:merged&quot;. |
| [GerarEsquema](sm-builder-generateschema.md) | Gera o código do esquema usando parâmetros de alto nível. |
| [GetDbParams](sm-builder-getdbparams.md) | Recupera os parâmetros atuais da fonte de dados. |
| [GetDefaultNamespace](sm-builder-getdefaultnamespace.md) | Recuperar o namespace padrão. |
| [InstalarPacote](sm-builder-installpackage.md) | Instalar um pacote. |
| [InstallPackageImpl](sm-builder-installpackageimpl.md) | Instalar um pacote (método interno, não usar). |
| [InstallVendorPackages](sm-builder-installvendorpackages.md) | Instalar um ou mais pacotes padrão. |
| [RemoveSchemaLinkRef](sm-builder-removeschemalinkref.md) | Remove o esquema e os links reversos que fazem referência a ele. |
| [ResolvePackageReferences](sm-builder-resolvepackagereferences.md) | Resolve as dependências do pacote |
| [UpdateDb](sm-builder-updatedb.md) | Atualização da estrutura do banco de dados. |
| [AtualizarEsquemaDoBancoDeDados](sm-builder-updateschemafromdatabase.md) | Atualizar o esquema com base em sua representação física no banco de dados. |
| [AtualizarEsquemasTempDoBancoDeDados](sm-builder-updatetempschemasfromdatabase.md) | Atualiza uma coleção de esquemas com base em sua representação física no banco de dados. |

## Métodos genéricos

| Método | Descrição |
| --- | --- |
| [criar](f-create.md) | Cria uma nova entidade correspondente a um determinado esquema. |
| [carregar](f-load.md) | Carrega e retorna uma entidade correspondente a um determinado esquema e chave. |
| [salvar](m-entity-save.md) | Salva uma entidade no banco de dados. |
