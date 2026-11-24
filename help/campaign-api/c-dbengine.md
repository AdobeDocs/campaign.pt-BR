---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 4%
---
# DBEngine (Classe)

Representa uma conexão de banco de dados.

Este objeto permite que você consulte o banco de dados e execute operações relacionadas.

A maioria dos métodos nesta classe requer direitos &#39;sql&#39;. Se o operador chamar um método e não tiver os direitos apropriados, uma exceção será gerada. De modo geral, todos os métodos que alteram o banco de dados exigem direitos &#39;sql&#39;, enquanto os métodos que simplesmente visualizam informações não exigem. Consulte a documentação de cada método para descobrir se os direitos são necessários ou não.

## Métodos

| Método | Descrição |
| --- | --- |
| [exclusãoLote](m-dbengine-batchdelete.md) | Exclui os registros de uma tabela por pacotes. |
| [descartar](m-dbengine-dispose.md) | Libera a conexão de todos os recursos vinculados a ela. |
| [executar](m-dbengine-execute.md) | Executa um comando SQL. |
| [exec](m-dbengine-exec.md) | Alias do comando execute. Esta função é obsoleta, use [executar()](m-dbengine-execute.md) |
| [consulta](m-dbengine-query.md) | Executa uma consulta SQL tipo SELECT. |
| [queryWithTypes](m-dbengine-querywithtypes.md) | Executa uma consulta SQL tipo SELECT com especificação de tipo de coluna. |
| [iniciar](m-dbengine-begin.md) | Inicia uma nova transação na conexão. |
| [confirmar](m-dbengine-commit.md) | Aprova a transação em andamento na conexão. |
| [reversão](m-dbengine-rollback.md) | Cancela a transação em andamento na conexão. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [isOracle](p-dbengine-isoracle.md) | Retorna verdadeiro se o banco de dados for Oracle. |
| [isDB2](p-dbengine-isdb2.md) | Retorna verdadeiro se o banco de dados for do tipo DB2. |
| [isMySQL](p-dbengine-ismysql.md) | Retorna verdadeiro se o banco de dados for do tipo MySQL. |
| [isMSSQL](p-dbengine-ismssql.md) | Retorna verdadeiro se o banco de dados for SQL Server. |
| [isPostgreSQL](p-dbengine-ispostgresql.md) | Retorna verdadeiro se o banco de dados for PostgreSQL. |
| [isSybase](p-dbengine-issybase.md) | Retorna verdadeiro se o banco de dados for Sybase. |
| [isSybaseIQ](p-dbengine-issybaseiq.md) | Retorna verdadeiro se o banco de dados for Sybase IQ. |
| [isFDA](p-dbengine-isfda.md) | Retorna verdadeiro se o banco de dados for acessado pelo FDA. |
| [isBroken](p-dbengine-isbroken.md) | Retorna verdadeiro se a conexão não puder mais ser usada. |
| [useUnicodeData](p-dbengine-useunicodedata.md) | Retorna verdadeiro se o banco de dados contiver dados unicode. |
| [useNChar](p-dbengine-usenchar.md) | Retorna verdadeiro se o Adobe Campaign usar os campos de tipo NCHAR, NVARCHAR, NCLOB, NTEXT. |

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
