---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 6%
---
# Aplicativo (Classe)

Essa classe tem uma única instância que fornece acesso a determinadas propriedades do servidor do aplicativo. Este singleton pode ser acessado por meio da variável global `application`.

## Métodos

| Método | Descrição |
| --- | --- |
| [hasPackage](m-application-haspackage.md) | Testa se um pacote está instalado. |
| [getSchema](m-application-getschema.md) | Retorna um mapeamento para um esquema do Adobe Campaign ou nulo se o esquema não existir. |
| [getDBMSType](m-application-getdbmstype.md) | Retorna o tipo de servidor do banco de dados. |
| [getNewIds](m-application-getnewids.md) | Retorna uma lista de IDs das chaves do banco de dados interno. |
| [getConnection](m-application-getconnection.md) | Retorna uma nova conexão com o servidor de banco de dados. |
| [getTimezoneJson](m-application-gettimezonejson.md) | Retorna uma cadeia de caracteres que é a representação em JSON da lista de diferenças de tempo com o horário UTC e sua data de início em comparação ao período UNIX de um fuso horário. |
| [onLog](m-application-onlog.md) | Adiciona ou exclui uma função de interceptação para as mensagens gravadas no diário |
| [onTrace](m-application-ontrace.md) | Adiciona ou exclui uma função de interceptação de mensagem de rastreamento. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [númeroCompilação](p-application-buildnumber.md) | Retorna o número da compilação do servidor do aplicativo. |
| [instanceName](p-application-instancename.md) | Nome da instância em que o script é executado. |
| [instanceVarDir](p-application-instancevardir.md) | Caminho completo do diretório &quot;var&quot; da instância em que o script é executado. |
| [instanceUploadDir](p-application-instanceuploaddir.md) | Caminho completo do diretório &quot;upload&quot; para a instância em que o script é executado. |
| [operador](p-application-operator.md) | Retorna um objeto contendo informações sobre o operador atual (nome, identificadores, direitos, etc.). |
| [localidade](p-application-locale.md) | Retorna uma cadeia de caracteres que corresponde à instância Local. |

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
