---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 56%
---
# fileRes

Recurso de arquivo armazenado no servidor ou no banco de dados

## Métodos

| Método | Descrição |
| --- | --- |
| [PublicaçãoDeArquivos](sm-fileres-filepublishing.md) | Publica os recursos públicos nos servidores frontais. |
| [GetPublicFileResURL](sm-fileres-getpublicfileresurl.md) | Obtém o URL da pasta |
| [GetServerFileName](sm-fileres-getserverfilename.md) | Retorna o nome do arquivo no servidor para a pasta de upload após copiá-lo, se necessário. |
| [GetURL](sm-fileres-geturl.md) | Obtém a URL do arquivo |
| [Pós-carregamento](sm-fileres-postupload.md) | Processamento pós-upload dependendo do tipo de armazenamento definido. |
| [Pré-download](sm-fileres-predownload.md) | Preparar o download do recurso dependendo do tipo de armazenamento definido. |
| [PublishIfNeeded](sm-fileres-publishifneeded.md) | Se necessário, copia o arquivo para os servidores de mídia |
| [PublishIfNeededFromId](sm-fileres-publishifneededfromid.md) | Se necessário, copia o arquivo nos servidores de mídia usando a ID do recurso |
| [WebPostUpload](sm-fileres-webpostupload.md) | Finalize o armazenamento do recurso após o upload (de uma página da Web) no servidor, dependendo do tipo de armazenamento usado. Recupera a página de código e o tipo de conteúdo. |

## Métodos genéricos

| Método | Descrição |
| --- | --- |
| [criar](f-create.md) | Cria uma nova entidade correspondente a um determinado esquema. |
| [carregar](f-load.md) | Carrega e retorna uma entidade correspondente a um determinado esquema e chave. |
| [salvar](m-entity-save.md) | Salva uma entidade no banco de dados. |
