---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 77%
---
# entrega

Este esquema representa uma ação de entrega ou modelo.

Um template é um template de delivery incluindo todos os parâmetros necessários. Um template do delivery pode ser executado manualmente no console do cliente ou quando ocorre um evento (iniciado no scheduler ou programaticamente a partir de uma chamada SOAP).

## Métodos

| Método | Descrição |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-appenddeliverypart.md) | Adicione uma parte a uma entrega que está sendo preparada. |
| [BuildForward](sm-delivery-buildforward.md) | Cria a página HTML. |
| [BuildMirror](sm-delivery-buildmirror.md) | Crie a mirror page do HTML. |
| [BuildMirrorEx](sm-delivery-buildmirrorex.md) | Crie a mirror page do HTML. |
| [BuildPreview](sm-delivery-buildpreview.md) | Criou a visualização de um conteúdo para entrega ou de uma linha do arquivo de saída (no modo externo). |
| [BuildPreviewFromId](sm-delivery-buildpreviewfromid.md) | Criou a visualização de um conteúdo para entrega ou de uma linha do arquivo de saída (no modo externo). |
| [BuildTargetDataSchema](sm-delivery-buildtargetdataschema.md) |  |
| [CleanupDeliveries](sm-delivery-cleanupdeliveries.md) | Especifica que o servidor de mid-sourcing deve excluir determinadas entregas. |
| [CollectLogs](sm-delivery-collectlogs.md) | Cria uma tabela com todas as mensagens do log de entrega para uma lista de entregas |
| [CriarDeModelo](sm-delivery-createfrommodel.md) | Criação de uma entrega a partir de um modelo (a partir de seu nome interno). |
| [DeployTriggerMessageSingle](sm-delivery-deploytriggermessagesingle.md) | Publique a mensagem transacional nas instâncias de execução. Retorna verdadeiro se a publicação for bem-sucedida, e falso, se não for. |
| [DeployTriggerMessages](sm-delivery-deploytriggermessages.md) | Publicar as mensagens transacionais selecionadas nas instâncias de execução |
| [DiagnosticarHTML](sm-delivery-diagnosehtml.md) | Inicia o diagnóstico de conteúdo HTML |
| [ImagensEnviadas](sm-delivery-dispatchimages.md) | Instrui o servidor de aplicativos a enviar as imagens para o servidor de mid-sourcing. |
| [ExecCommand](sm-delivery-execcommand.md) | Executa um comando em uma entrega. |
| [ExecutarTrabalho](sm-delivery-executejob.md) | Executa um processo síncrono em uma entrega. |
| [FinalizeMidPreparation](sm-delivery-finalizemidpreparation.md) | Finalizar a análise de uma entrega no modo de mid-sourcing. |
| [GetDeviceList](sm-delivery-getdevicelist.md) |  |
| [GetDlStatusAndLogs](sm-delivery-getdlstatusandlogs.md) | Recuperar os últimos logs do journal e do status de entrega. |
| [GetFilesToDownload](sm-delivery-getfilestodownload.md) | Retorna a lista de arquivos encontrados no servidor associado à entrega. |
| [GetMidBroadLogs](sm-delivery-getmidbroadlogs.md) | Recupere os logs de entrega modificados por último no modo de mid-sourcing. |
| [GetMidDeliveries](sm-delivery-getmiddeliveries.md) | Recupera o status das entregas modificadas por último no modo de mid-sourcing. |
| [GetMidXtkKey](sm-delivery-getmidxtkkey.md) | Retorna a chave Xtk do servidor intermediário |
| [GetMirrorURL](sm-delivery-getmirrorurl.md) | Obtém a URL de uma mirror page HTML. |
| [GetSeedList](sm-delivery-getseedlist.md) |  |
| [HtmlToText](sm-delivery-htmltotext.md) | Converte conteúdo HTML em texto sem formatação |
| [PublicaçãoImagem](sm-delivery-imagepublishing.md) | Executa o pós-processamento: mover a imagem para uma pasta especificada e disponibilizá-la online |
| [InstallTransactionalMessage](sm-delivery-installtransactionalmessage.md) | Instale um modelo de mensagem transacional na instância de execução. |
| [InvalidateDeliveryCache](sm-delivery-invalidatedeliverycache.md) | Deve ser chamado no final da preparação da mensagem, exceto para mid-sourcing (método privado). |
| [LaunchFCP](sm-delivery-launchfcp.md) | Inicia uma cópia de prova para uma entrega |
| [LoadExpandedContents](sm-delivery-loadexpandedcontents.md) | Carregar uma lista de componentes para pré-processamento com dependências (blocos de personalização, opções, objetos de script adicionais etc.). |
| [Pause](sm-delivery-pause.md) | Suspender uma entrega. |
| [Reproduzir](sm-delivery-play.md) | Iniciar uma entrega. |
| [Preparar](sm-delivery-prepare.md) | Análise da entrega: direcionamento e personalização |
| [PrepareAndStart](sm-delivery-prepareandstart.md) | Analisa a entrega e a executa imediatamente se nenhum erro for encontrado |
| [PrepareFromId](sm-delivery-preparefromid.md) | Analisar uma entrega. |
| [PrepareMessage](sm-delivery-preparemessage.md) | Personalização de mensagens |
| [PrepareMessageImpl](sm-delivery-preparemessageimpl.md) | Personalização de mensagens |
| [PrepareMultipartRelated](sm-delivery-preparemultipartrelated.md) | Salvar as imagens para incluir no email no banco de dados |
| [PrepareNotification](sm-delivery-preparenotification.md) | Analisar uma notificação que está sendo adicionada a uma ação de entrega existente |
| [PrepareProof](sm-delivery-prepareproof.md) | Análise da entrega para geração de uma prova |
| [PrepareTarget](sm-delivery-preparetarget.md) | Contagem e arbitragem do público-alvo da entrega |
| [PrepareTargetImpl](sm-delivery-preparetargetimpl.md) | Contagem e arbitragem do público-alvo da entrega |
| [PreviewExtraction](sm-delivery-previewextraction.md) | Visualização do arquivo de extração |
| [PriorizarLogs](sm-delivery-prioritizelogs.md) | Priorizar o log de entrega para uma lista de entregas |
| [PriorizarDestino](sm-delivery-prioritizetarget.md) | Arbitragem do público-alvo da entrega |
| [NotificaçãoFila](sm-delivery-queuenotification.md) | Solicitação para incluir na fila uma notificação que faz referência a um modelo de entrega. |
| [RecomputeStats](sm-delivery-recomputestats.md) | Recalcular estatísticas de entrega e rastreamento para uma ação de entrega. |
| [SaveUrlInfo](sm-delivery-saveurlinfo.md) | Salvar URLs desta entrega como modelos de URL. |
| [Stop](sm-delivery-stop.md) | Parar uma entrega em andamento. |
| [StoreMirrorPageInfo](sm-delivery-storemirrorpageinfo.md) | Adiciona informações para gerar mirror pages para um conjunto de partes de entrega. |
| [StoreMirrorPageInfoEx](sm-delivery-storemirrorpageinfoex.md) | Adiciona informações para gerar mirror pages para um conjunto de partes de entrega. |
| [EnviarEntrega](sm-delivery-submitdelivery.md) | Criação e envio de uma entrega a partir de um cenário (a partir de seu nome interno). |
| [SubmitDeliveryById](sm-delivery-submitdeliverybyid.md) | Criar e enviar uma entrega a partir de um cenário (identificado por seu nome interno). |
| [EnviarTrabalho](sm-delivery-submitjob.md) | Envia um processo de entrega para processamento assíncrono |
| [SubmitMidSourcing](sm-delivery-submitmidsourcing.md) | Enviar uma entrega no modo mid-sourcing. |
| [EnviarNotificação](sm-delivery-submitnotification.md) | Criar e enviar uma notificação de um cenário. |
| [UpdateBroadLogs](sm-delivery-updatebroadlogs.md) | Atualize o status dos logs de entrega, execute o tratamento de erros e atualize os contadores de entrega. |
| [UpdateCachedDelivery](sm-delivery-updatecacheddelivery.md) | Deve ser chamado sempre que a entrega for modificada na memória para que outras threads tenham acesso a uma versão atualizada (método privado). |
| [UpdateImageConfig](sm-delivery-updateimageconfig.md) | Modifica o nó imageConfig para levar em consideração as imagens que já estão no servidor. |
| [ValidateWavesDefinition](sm-delivery-validatewavesdefinition.md) | Verifique a consistência das informações usadas na definição das ondas. |

## Métodos genéricos

| Método | Descrição |
| --- | --- |
| [criar](f-create.md) | Cria uma nova entidade correspondente a um determinado esquema. |
| [carregar](f-load.md) | Carrega e retorna uma entidade correspondente a um determinado esquema e chave. |
| [salvar](m-entity-save.md) | Salva uma entidade no banco de dados. |
