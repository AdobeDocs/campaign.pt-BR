---
title: Opções de campanha
description: Saiba o que são opções do Campaign, onde elas estão armazenadas e como usar as opções documentadas para o Campaign v8
feature: Architecture
role: Admin, Developer
level: Intermediate
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 92bab89570eca3eb13d6010db0deec74e7860c91
workflow-type: tm+mt
source-wordcount: '2849'
ht-degree: 3%
---
# Opções de campanha {#campaign-options}

As opções são parâmetros que controlam como sua instância do Campaign se comporta, por exemplo, o limite de tamanho padrão de imagens em emails, o número de workflows executados ao mesmo tempo ou o provedor de roteamento padrão de templates de delivery. Algumas opções são incorporadas e outras são criadas quando necessário. As opções disponíveis dependem dos pacotes instalados na sua instância. Saiba mais em [Pacotes internos](built-in-packages.md).

>[!CAUTION]
>
>Modifique somente as opções documentadas na documentação do Campaign e somente conforme descrito. As opções que não estão documentadas são internas e não devem ser modificadas. A modificação de opções é reservada para usuários especialistas.

## Onde as opções são armazenadas {#where-options-are-stored}

As opções são armazenadas no banco de dados do Campaign, na tabela **xtkOption** (schema **xtk:option**). No Campaign Explorer, eles estão disponíveis em **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. Na interface da Web do Campaign, eles estão disponíveis em **[!UICONTROL Administration]** > **[!UICONTROL Options]**. Ambas as listas são idênticas. Saiba mais em [Configurar opções do Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options){target="_blank"}.

## Usar opções {#use-options}

1. No Campaign Explorer, navegue até **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**.
1. Selecione a opção e atualize seu valor. Se a opção não existir, crie-a com o nome exato fornecido na documentação.
1. Defina um valor do tipo que a documentação espera. Por exemplo, uma opção de texto para a data de sincronização do CRM ou uma opção de número inteiro para o atraso de reinicialização do fluxo de trabalho.

Você também pode criar suas próprias opções, por exemplo, para armazenar dados intermediários de um workflow. Insira um nome, selecione o tipo de dados e defina o valor. Saiba mais em [Configurar opções do Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#create){target="_blank"}.

Algumas opções mantêm as credenciais. Criptografe segredos com a função `cryptString`, conforme descrito em [Trabalhar com páginas de aterrissagem do Campaign e do Adobe Experience Platform](../connect/ac-aep-landing-pages.md). Ao girar as credenciais, também gire as armazenadas nas opções. Saiba mais no [guia de rotação de credencial](../../technotes/security/credential-rotation-guide.md#ac-options-credentials).

## Usar opções em fluxos de trabalho e personalização {#use-options-in-processes}

Você pode ler e gravar valores de opção no código, na personalização e em consultas do JavaScript.

* **Código JavaScript**, como uma atividade de fluxo de trabalho de código JavaScript: `getOption('OptionName')` retorna o valor de uma opção, e `setOption('OptionName', value, 'description')` o define. Por exemplo, `getOption('IMS_ORG_ID')`. Saiba mais em [getOption](../../campaign-api/f-getoption.md) e [setOption](../../campaign-api/f-setoption.md).
* **Personalização de entrega**: `<%@ include option='OptionName' %>` insere o valor de uma opção. Por exemplo, `<%@ include option='NmsServer_URL' %>` inclui a URL do servidor em um link para um aplicativo Web em uma mensagem LINE. Saiba mais em [Enviar mensagens LINE diretas com o Adobe Campaign](../send/line/line.md).
* **Editor de consultas**: digite `$(options:OPTION_NAME)` no campo **Valor** para usar o valor de uma opção. Saiba mais em [Criar consultas](../start/design-queries.md).

## Opções disponíveis {#available-options}

As tabelas abaixo listam as opções disponíveis no Campaign v8, agrupadas por área. Quando outra página da documentação descreve uma opção, a tabela é vinculada a ela. Algumas entradas são opções informativas ou de manutenção. Listar uma opção não significa que é seguro alterá-la.

### Entregas {#delivery-options}

Essas opções controlam como os deliveries são preparados e enviados. Elas abrangem limites de imagem e anexo, o provedor de roteamento padrão, o limite dividido de mid-sourcing, o script de rastreamento aberto, o URL do servidor público, a validade do delivery, o tratamento de duplicatas e deliveries atrasados e códigos de barras. Saiba mais em [Anexando arquivos](../send/attaching-files.md), [Parâmetros de email](../send/email-parameters.md), [Práticas recomendadas de entrega](../start/delivery-best-practices.md), [Introdução à arquitetura do Campaign](architecture.md#split), [Orientação sobre Pixels de Acompanhamento de Email](../start/cnil-pixel-tracking.md) e [Enviar mensagens LINE diretas](../send/line/line.md).

| Opção | Descrição |
|---|---|
| NmsDelivery_MaxDownloadedImageSize | Tamanho máximo, em bytes, de uma imagem baixada de um URL personalizado e anexada a um email. O valor padrão é 100.000 bytes (100 KB). [Saiba mais](../send/attaching-files.md) |
| NmsDelivery_MaxRecommendedAttachments | Número máximo de anexos em um email ou modelo de email transacional antes da exibição de um aviso. O valor padrão é 1. [Saiba mais](../send/attaching-files.md) |
| NmsEmail_EndereçoDeErroPadrão | Endereço de email de erro padrão da instância, usado quando o delivery deixa o endereço de erro vazio. [Saiba mais](../send/email-parameters.md) |
| XtkEmail_Characters | Caracteres válidos para um endereço de email. [Saiba mais](../start/delivery-best-practices.md) |
| NmsBroadcast_DefaultProvider | Provedor de roteamento padrão de novos modelos de entrega. Defina-o com o nome de uma conta externa dividida para usar a entrega dividida por padrão. [Saiba mais](architecture.md#split) |
| NmsDelivery_MultiMidSplitThreshold | Tamanho do qual um delivery é dividido entre várias instâncias de mid-sourcing. O valor padrão é 100K. [Saiba mais](architecture.md#split) |
| NmsTracking_OpenFormula | Script que calcula o URL de rastreamento aberto. Defina uma opção por finalidade de pixel. [Saiba mais](../start/cnil-pixel-tracking.md) |
| NmsServer_URL | URL base do servidor público de aplicativos Web. Usado, por exemplo, para incluir um link de aplicativo Web em uma mensagem LINE. [Saiba mais](../send/line/line.md) |
| NmsBroadcast_MsgValidityDuration | Período de validade padrão de uma entrega, em segundos. |
| NmsBroadcast_RemoveDuplicatesRecipients | Defina como 1 para ignorar automaticamente os recipients duplicados. |
| NmsDelivery_ImageServerTimeout | Tempo limite, em segundos, para obter uma resposta do servidor ao recuperar uma imagem baixada de um URL personalizado e anexada a um email. Se o tempo limite for excedido, a mensagem não poderá ser enviada. O valor padrão é de 60 segundos. |
| NmsDeliveryWizard_ShowDeliveryWeight | Exibe o peso da mensagem no assistente de entrega. |
| NmsMTA_Alert_Delay | Atraso, em minutos, após o qual um delivery é considerado atrasado. O valor padrão é de 30 minutos. |
| NmsServer_MirrorPageUrl | URL do servidor de mirror pages. É o valor padrão de deliveries de email quando a definição de roteamento não especifica um URL. Por padrão, é idêntico ao URL do servidor de rastreamento. |
| XtkBarcode_CaractereEspecial | Ativa ou desativa o suporte de caracteres especiais para os códigos de barras do Código 128. |
| NMS_AtivateOwnerConfirmation | Defina-o como 1 para que o operador encarregado do delivery possa confirmar o envio, quando um operador ou grupo específico for designado para iniciar o delivery. Defina-o como 0 para desativar: somente o operador ou grupo designado, ou um administrador, pode confirmar o envio. |
| NmsDelivery_senderAddressMask | Lista separada por vírgulas dos endereços de remetente permitidos no campo De email de deliveries de email. Quando a opção tem um valor, o campo se torna uma lista suspensa. A restrição é global: se aplica a todas as marcas e modelos de entrega e aceita somente endereços estáticos. [Saiba mais](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#restrict-sender-address){target="_blank"} |

### Campanhas e workflows {#campaign-workflow-options}

Essas opções controlam como as campanhas e os workflows são executados. Elas abrangem a confirmação do proprietário de um envio, o número de trabalhos processados ao mesmo tempo e a verificação e reinicialização automática de workflows. Elas também abrangem a proteção de atividades SQL, a validade da campanha padrão e o logotipo dos relatórios exportados. Saiba mais em [Entregas de campanha de marketing](../../automation/campaigns/marketing-campaign-deliveries.md), [Práticas recomendadas de fluxo de trabalho](../../automation/workflow/workflow-best-practices.md), [Monitorar a execução do fluxo de trabalho](../../automation/workflow/monitor-workflow-execution.md), [Propriedades do fluxo de trabalho](../../automation/workflow/workflow-properties.md) e [Código SQL e código JavaScript](../../automation/workflow/sql-code-and-javascript-code.md#important-notes).

| Opção | Descrição |
|---|---|
| NmsCampaign_Ativate_OwnerConfirmation | Crie-o e defina-o como 1 para que o proprietário da campanha possa confirmar o envio, mesmo que os revisores estejam definidos. Defina como 0 para desativar. [Saiba mais](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | Número máximo de trabalhos de entrega, fluxo de trabalho, hipótese e simulação que uma campanha processa ao mesmo tempo. O valor padrão é 10. [Saiba mais](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | Número de dias entre duas verificações para workflows pausados. [Saiba mais](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | Crie-o como uma opção de número inteiro para alterar o intervalo de 30 segundos em que os workflows são verificados e reiniciados automaticamente. [Saiba mais](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | Defina-o como 0 para desativar a proteção das atividades de código SQL contra métodos SQL bloqueados. [Saiba mais](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | Lista de métodos SQL que as atividades SQL bloqueiam ou avisam. [Saiba mais](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| NmsOperation_Duration | Período de validade padrão de uma campanha, em segundos. |
| NmsOperation_TimeRange | Período para as condições de direcionamento e extração no modo agendado. |
| NmsOperation_OperationMgtDebug | Defina-o como 1 para registrar as informações de execução do workflow técnico operationMgt nos logs de auditoria do workflow. |
| NmsOperation_DeliveryPreparationWindow | Número de dias nos quais os deliveries com status inconsistente são excluídos da contagem de deliveries em execução pelo fluxo de trabalho técnico operationMgt. O valor padrão é 7. |
| Workflow_AnalysisThreshold | Número de registros afetados após o qual as estatísticas da tabela são recalculadas automaticamente. |
| XtkReport_Logo | Logotipo exibido no canto superior direito dos relatórios exportados. |

### Padrões de email {#email-default-options}

Essas opções definem o remetente padrão, os endereços de resposta e os rótulos dos seus emails. O Campaign os usa quando um delivery deixa o campo correspondente vazio. Saiba mais em [Parâmetros de email](../send/email-parameters.md) e [Trabalhar com modelos de entrega](../send/create-templates.md).

| Opção | Descrição |
|---|---|
| NmsEmail_DefaultFromAddr | Endereço &quot;De&quot; padrão da instância, usado quando o delivery a deixa vazia. |
| NmsEmail_FromName | Rótulo padrão De da instância, usado quando o delivery a deixa vazia. |
| NmsEmail_DefaultReplyToAddr | Endereço de resposta padrão da instância, usado quando o delivery a deixa vazia. |
| NmsEmail_ReplyToName | Rótulo Padrão de Responder para da instância, usado quando o delivery a deixa vazia. |
| NmsEmail_EndereçoDeErroPadrão | Endereço de erro padrão da instância, usado quando o delivery a deixa vazia. [Saiba mais](../send/email-parameters.md) |
| NmsDelivery_FromAddressMasks | Sintaxe do endereço From usado ao enviar uma mensagem. |
| NmsDelivery_ErrorAddressMasks | Sintaxe do endereço de erro usado ao responder a uma mensagem. |
| NmsEmail_ExpOrganization | Nome comum da organização, usado em algumas mensagens de aviso exibidas para os recipients. |

### Erros leves e quarentena {#error-options}

Essas opções definem quando um recipient é colocado em quarentena após erros leves, que são falhas temporárias de delivery. Saiba mais em [Gerenciamento de quarentena no Campaign](../send/quarantines.md#soft-error-management) e [Falhas de entrega no Campaign](../send/delivery-failures.md#retries).

| Opção | Descrição |
|---|---|
| NmsNPAI_EmailMaxError | Número máximo de erros de software aceitos no canal de email antes que o recipient seja colocado em quarentena. |
| NmsNPAI_EmailAtrasoErroSignificativo | Tempo mínimo que deve passar após o erro de software anterior no canal de email antes que um novo erro de software seja considerado. |
| NmsNPAI_MobileMaxError | Número máximo de erros leves aceitos no canal móvel antes que o recipient seja colocado em quarentena. |
| NmsNPAI_MobileSignificantErrorDelay | Tempo mínimo que deve passar após o erro de software anterior no canal móvel antes que um novo erro de software seja considerado. |

### Canais {#channel-options}

Essas opções definem o endereço do remetente da correspondência direta, as configurações dos canais LINE e SMS e os endereços de encaminhamento permitidos do email de entrada. Saiba mais em [Enviar correspondência direta com o Adobe Campaign](../send/direct-mail.md), [Enviar mensagens LINE diretas com o Adobe Campaign](../send/line/line.md) e [Enviar SMS com o Adobe Campaign](../send/sms/sms.md).

| Opção | Descrição |
|---|---|
| NmsPaper_SenderLine1, NmsPaper_SenderLine3, NmsPaper_SenderLine4, NmsPaper_SenderLine6, NmsPaper_SenderLine7 | Linhas 1, 3, 4, 6 e 7 do endereço do remetente de deliveries de correspondência direta. |
| NmsLine_AESKey | Chave AES usada pelo servlet lineImage para codificar URLs no canal LINE. |
| NmsLine_MessageCenterURL | URL do servidor do Centro de Mensagens usado para enviar mensagens de boas-vindas no canal LINE. |
| NmsSMS_Priority | Prioridade de mensagens SMS enviadas, transmitidas para o gateway de SMS. |
| NmsInmail_AllowlistEmails | Endereços de email de encaminhamento autorizados do módulo de processamento de emails de entrada, separados por vírgulas. Use * para permitir todos os endereços. |

### Limites do Centro de mensagens {#message-center-options}

Essas opções definem os limites que geram um aviso ou um alerta quando o processamento de eventos em tempo real, que acionam mensagens transacionais, é degradado. Cada métrica tem um limite de aviso e um limite de alerta. O nome da opção termina com Warning ou Alert, por exemplo MC_RtEventErrorWarning e MC_RtEventErrorAlert. Saiba mais em [Mensagens transacionais de campanha](../send/transactional.md) e [Configurações de mensagens transacionais de campanha](../config/transactional-msg-settings.md).

| Prefixo do nome da opção | Métrica |
|---|---|
| MC_RtEventAvgDeliveryTime | Tempo médio de envio de eventos em tempo real. |
| MC_RtEventAvgProcessTime | Tempo médio de processamento de eventos em tempo real. |
| MC_RtEventAvgQueueTime | Tempo médio de enfileiramento de eventos em tempo real. |
| MC_RtEventAvgQueue | Número médio de eventos em tempo real enfileirados. |
| MC_RtEventMaxQueue | Número máximo de eventos em tempo real enfileirados. |
| MC_RtEventMinQueue | Número mínimo de eventos em tempo real em fila. |
| MC_RtEventQueue | Fila de eventos em tempo real pendentes. O limite de alerta é a condição crítica. |
| MC_RtEventError | Processamento de erros de eventos em tempo real. |
| MC_RtEventThroughput | Taxa de transferência de eventos em tempo real. |

### Retenção de dados e banco de dados {#database-options}

O workflow de limpeza limpa registros antigos para impedir o crescimento do banco de dados. Essas opções definem por quanto tempo o Campaign mantém cada tipo de dados. Uma opção de atraso de limpeza é criada automaticamente quando você altera o atraso na interface. Se você editá-lo na lista de opções, expresse o valor em segundos. Saiba mais em [Arquitetura geral](general-architecture.md) e [Diretrizes de segurança](../config/security.md#consent).

Somente administradores podem modificar as opções de atraso de limpeza. Os valores apropriados dependem do seu ambiente, portanto, verifique o valor atual na sua instância e não assuma um padrão universal.

| Opção | Descrição |
|---|---|
| NmsCleanup_BroadLogPurgeDelay | Atraso após o qual os logs do delivery (broadlogs) são apagados. |
| NmsCleanup_TrackingLogPurgeDelay | Atraso após o qual os logs de rastreamento são apagados. |
| NmsCleanup_TrackingStatPurgeDelay | Atraso após o qual as estatísticas de rastreamento são apagadas. |
| NmsCleanup_EventPurgeDelay | Atraso após o qual os eventos são apagados. |
| NmsCleanup_EventHistoPurgeDelay | Atraso após o qual o histórico do evento é apagado. |
| NmsCleanup_EventStatPurgeDelay | Atraso após o qual as estatísticas de evento são apagadas. |
| NmsCleanup_PropositionPurgeDelay | Atraso após o qual as apresentações são apagadas. |
| NmsCleanup_QuarantineMailboxFull | Atraso após o qual as quarentenas são apagadas. |
| NmsCleanup_RecycledDeliveryPurgeDelay | Atraso após o qual os deliveries reciclados são apagados. |
| NmsCleanup_RejectsPurgeDelay | Atraso após o qual as rejeições são apagadas. |
| NmsCleanup_VisitorPurgeDelay | Atraso após o qual os visitantes são apagados. |
| NmsCleanup_WorkflowResultPurgeDelay | Atraso após o qual os resultados do fluxo de trabalho são apagados. |
| WdbcKillSessionPolicy | Comportamento da interrupção incondicional de workflows no PostgreSQL. 0 (padrão): interrompe o processo de workflow sem impacto no banco de dados. 1: interrompe o processo e cancela a consulta (pg_cancel_backend). 2: interrompe o processo e encerra a consulta (pg_terminate_backend). |
| XtkSequence_AutoGeneration | Aplica-se a esquemas personalizados criados após a definição desta opção, com autopk=&quot;true&quot; e nenhum atributo pkSequence: o Campaign gera a sequência automaticamente. |

### Personalização do Centro de mensagens {#message-center-customization}

Essas opções permitem personalizar como o Campaign enriquece e roteia eventos em lote e em tempo real. Saiba mais em [Mensagens transacionais de campanha](../send/transactional.md) e [Configurações de mensagens transacionais de campanha](../config/transactional-msg-settings.md).

| Opção | Descrição |
|---|---|
| MC_EnrichmentCustomJs | Biblioteca da JavaScript que enriquece eventos. Deve implementar enrichRtEvents(aiEventId) para eventos em tempo real e enrichBatchEvents(aiEventId) para eventos em lote. Ambas as funções enriquecem os eventos e os salvam no banco de dados. |
| MC_RoutingCustomJs | Biblioteca da JavaScript que roteia eventos. Ele deve implementar dispatRtEvent(iEventId) e dispatBatchEvent(iEventId), que retornam o nome interno da mensagem transacional selecionada para o evento em tempo real ou em lote. |
| NmsMessageCenter_RoutingBatchSize | Tamanho dos grupos usados para roteamento de eventos. |
| NmsTracking_RT_ClickFormula, NmsTracking_RT_OpenFormula | Fórmulas usadas para rastreamento de cliques e aberturas de deliveries em tempo real (RT) quando a identidade visual está ativada. Eles são configurados na instância de controle RT. [Saiba mais](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |
| Branding_RT_ListXtkOptions_toPublish | Lista das opções, separadas por vírgulas, que contêm suas fórmulas de rastreamento personalizadas, para que os deliveries de RT possam aplicá-las. [Saiba mais](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |

### Interação (gerenciamento de ofertas) {#interaction-options}

Essas opções se aplicam à Interação do Campaign, o módulo de gestão de ofertas. Eles controlam como as propostas são escritas e como as instâncias de controle e de execução são sincronizadas. Saiba mais em [Interação do Campaign - Gerenciamento de ofertas](../interaction/interaction.md) e nas [opções de manutenção](../interaction/interaction-architecture.md#maintenance-options) da arquitetura do Interaction.

| Opção | Descrição |
|---|---|
| NmsInteraction_UseDaemon | Defina-o como 1 para ativar a gravação assíncrona de apresentações ou como 0 para desativá-la. |
| NmsInteraction_MapWorkflowId | Lista de todos os workflows de sincronização gerados. Opção de manutenção informativa da instância de controle: não a modifique. |
| NmsExecutionInstanceId | Identificador da instância de execução. Opção informativa disponível em instâncias de execução: não a modifique. |

As seguintes opções também são opções de manutenção da instância de controle:

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: última data em que um ambiente foi sincronizado em uma determinada instância.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: última data em que as propostas de um esquema foram sincronizadas de uma instância para outra.

>[!CAUTION]
>
>Use as opções de manutenção somente para casos de manutenção específicos.

As opções a seguir se aplicam aos cupons, que não estão disponíveis em implantações corporativas (FFDA). Saiba mais em [Cupons personalizados](../send/personalized-coupons.md).

| Opção | Descrição |
|---|---|
| NmsModule_CouponsEnabled | Habilita cupons. |
| NmsCoupons_MaxPerTransac | Número de cupons atualizados por transação SQL. |

### Solicitações de privacidade {#privacy-options}

Essas opções controlam como o Campaign processa solicitações de privacidade, como a confirmação de exclusões, o número de erros permitidos e por quanto tempo os dados da solicitação são mantidos. Saiba mais em [Gerenciar solicitações de privacidade no Campaign](../start/privacy.md).

| Opção | Descrição |
|---|---|
| Privacy_Request_ConfirmDeletePending | Defina como 1 para confirmar cada exclusão manualmente na interface em uma segunda etapa. Caso contrário, os dados serão excluídos sem confirmação. |
| Privacy_Request_ConfirmDeletePendingDelay | Atraso após o qual uma solicitação que aguarda a confirmação da exclusão é cancelada. |
| Privacy_Request_MaxErrorAllowed | Número máximo de erros permitidos ao processar ou excluir uma solicitação de acesso a dados pessoais. |
| Privacy_Request_PurgeDelay | Atraso entre a criação de uma solicitação na fila e a exclusão de seus dados. |
| realtimeReporting_collectPII | Escolha do contrato de informações de identificação pessoal (PII) para relatórios dinâmicos. O valor 1 corresponde a Pergunte-me mais tarde, 2 para Recusar e 3 para Aceitar. [Saiba mais](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reporting/dynamic-reporting/pii-agreement){target="_blank"} |

### Trilha de auditoria {#audit-trail-options}

A trilha de auditoria registra as alterações feitas nas entidades do Campaign. Use essas opções para ativá-la ou desativá-la para uma entidade, por exemplo, para salvar espaço no banco de dados. Defina o valor como 1 para ativar a trilha de auditoria e como 0 para desativá-la. Saiba mais em [Trilha de auditoria](../reporting/audit-trail.md#enable-disable-audit-trail).

| Opção | Entidade auditada |
|---|---|
| XtkAudit_Workflows | Fluxos de trabalho |
| XtkAudit_DataSchema | Esquemas |
| XtkAudit_Option | Opções |
| XtkAudit_Delivery | Entregas |
| XtkAudit_ExtAccount | Contas externas |
| XtkAudit_DeliveryMapping | Mapeamentos de entrega |
| XtkAudit_WebApp | Aplicativos web |
| XtkAudit_Offer | Ofertas |
| XtkAudit_Operator | Operadores |
| XtkAudit_Enable_All | Todas as entidades |

### Integrações e pesquisas {#integration-options}

Essas opções armazenam as configurações de integrações e pesquisas: as credenciais do Adobe Developer Console para landing pages, a data da última sincronização da atividade do Conector CRM e o backup padrão das respostas da pesquisa. Saiba mais em [Atualizar perfis do Adobe Experience Platform nas páginas de aterrissagem do Adobe Campaign](../connect/ac-aep-landing-pages.md), [sincronização de dados do CRM Connectors](../connect/crm-data-sync.md) e [Gerenciar respostas](../dev/surveys/managing-answers.md).

| Opção | Descrição |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Credenciais do Adobe Developer Console usadas para páginas de aterrissagem com o Adobe Experience Platform. [Saiba mais](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_ seguido pelo nome interno da instância e pelo nome da atividade | Data da última sincronização da atividade genérica do Conector CRM. Criar manualmente como uma opção de texto, no formato `yyyy/MM/dd hh:mm:ss`. [Saiba mais](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | Crie-o e defina-o como 1 para salvar uma cópia das respostas brutas por padrão para todas as pesquisas. [Saiba mais](../dev/surveys/managing-answers.md) |
| AEMResourceTypeFilter | Tipos de recursos do Adobe Experience Manager que podem ser usados no Campaign, separados por vírgulas. [Saiba mais](../connect/ac-aem.md) |
| nmsPipeline_config | Configuração de acionadores da Adobe Experience Cloud, no formato JSON. Crie-a como uma opção de texto longo. [Saiba mais](../connect/ac-triggers.md) |
| TNT_EdgeServer | Servidor do Adobe Target usado para a integração, definido por padrão. É o servidor de domínio do Adobe Target seguido por /m2, por exemplo tt.omtrdc.net/m2. [Saiba mais](../connect/ac-at.md) |
| TNT_TenantName | Nome da organização (cliente) da Adobe Target. [Saiba mais](../connect/ac-at.md) |
| AAM_DataSourceId, AAM_DestinationId | Identificadores usados pela integração com o Adobe Audience Manager. [Saiba mais](../start/shared-audiences.md) |
| WdbcCapabilities_AzureDw | Opções do conector do Azure Synapse (Azure SQL Data Warehouse). [Saiba mais](../connect/fda.md) |

## Tópicos relacionados {#related-topics}

* [Pacotes incorporados](built-in-packages.md)
* [Princípios globais](general-architecture.md)
* [Guia de rotação de credenciais](../../technotes/security/credential-rotation-guide.md)
