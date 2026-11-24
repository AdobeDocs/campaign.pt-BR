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
source-git-commit: 2c6140065272892d40ad66da0c0c89dfe169ce19
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 5%
---
# Opções de campanha {#campaign-options}

As opções são parâmetros que controlam como sua instância do Campaign se comporta, por exemplo, o limite de tamanho padrão de imagens em emails, o número de workflows executados ao mesmo tempo ou o provedor de roteamento padrão de templates de delivery. Algumas opções são incorporadas e outras são criadas quando necessário. As opções disponíveis dependem dos pacotes instalados na sua instância. Saiba mais em [Pacotes internos](built-in-packages.md).

>[!CAUTION]
>
>Modifique somente as opções documentadas na documentação do Campaign e somente conforme descrito. As opções que não estão documentadas são internas e não devem ser modificadas. A modificação de opções é reservada para usuários especialistas.

## Onde as opções são armazenadas {#where-options-are-stored}

As opções são armazenadas no banco de dados do Campaign, na tabela **xtkOption** (schema **xtk:option**). No Campaign Explorer, eles estão disponíveis em **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**.

## Usar opções {#use-options}

1. No Campaign Explorer, navegue até **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**.
1. Selecione a opção e atualize seu valor. Se a opção não existir, crie-a com o nome exato fornecido na documentação.
1. Defina um valor do tipo que a documentação espera. Por exemplo, uma opção de texto para a data de sincronização do CRM ou uma opção de número inteiro para o atraso de reinicialização do fluxo de trabalho.

Algumas opções mantêm as credenciais. Criptografe segredos com a função `cryptString`, conforme descrito em [Trabalhar com páginas de aterrissagem do Campaign e do Adobe Experience Platform](../connect/ac-aep-landing-pages.md). Ao girar as credenciais, também gire as armazenadas nas opções. Saiba mais no [guia de rotação de credencial](../../technotes/security/credential-rotation-guide.md#ac-options-credentials).

## Opções documentadas para o Campaign v8 {#documented-options}

As tabelas abaixo listam as opções que a documentação do Campaign v8 solicita que você use, com um link para a página que descreve como.

### Entregas {#delivery-options}

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

### Campanhas e workflows {#campaign-workflow-options}

| Opção | Descrição |
|---|---|
| NmsCampaign_Ativate_OwnerConfirmation | Crie-o e defina-o como 1 para que o proprietário da campanha possa confirmar o envio, mesmo que os revisores estejam definidos. Defina como 0 para desativar. [Saiba mais](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | Número máximo de trabalhos de entrega, fluxo de trabalho, hipótese e simulação que uma campanha processa ao mesmo tempo. O valor padrão é 10. [Saiba mais](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | Número de dias entre duas verificações para workflows pausados. [Saiba mais](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | Crie-o como uma opção de número inteiro para alterar o intervalo de 30 segundos em que os workflows são verificados e reiniciados automaticamente. [Saiba mais](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | Defina-o como 0 para desativar a proteção das atividades de código SQL contra métodos SQL bloqueados. [Saiba mais](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | Lista de métodos SQL que as atividades SQL bloqueiam ou avisam. [Saiba mais](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |

### Padrões de email {#email-default-options}

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

| Opção | Descrição |
|---|---|
| NmsNPAI_EmailMaxError | Número máximo de erros de software aceitos no canal de email antes que o recipient seja colocado em quarentena. |
| NmsNPAI_EmailAtrasoErroSignificativo | Tempo mínimo que deve passar após o erro de software anterior no canal de email antes que um novo erro de software seja considerado. |
| NmsNPAI_MobileMaxError | Número máximo de erros leves aceitos no canal móvel antes que o recipient seja colocado em quarentena. |
| NmsNPAI_MobileSignificantErrorDelay | Tempo mínimo que deve passar após o erro de software anterior no canal móvel antes que um novo erro de software seja considerado. |

Saiba mais sobre erros de software e quarentenas em [Falhas de entrega](../send/delivery-failures.md).

### Limites do Centro de mensagens {#message-center-options}

Cada métrica de evento em tempo real tem um limite de aviso e um limite de alerta. O nome da opção termina com Warning ou Alert, por exemplo MC_RtEventErrorWarning e MC_RtEventErrorAlert. Saiba mais sobre mensagens transacionais em [Mensagens transacionais do Campaign](../send/transactional.md).

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

### Solicitações de privacidade {#privacy-options}

| Opção | Descrição |
|---|---|
| Privacy_Request_ConfirmDeletePending | Defina como 1 para confirmar cada exclusão manualmente na interface em uma segunda etapa. Caso contrário, os dados serão excluídos sem confirmação. |
| Privacy_Request_ConfirmDeletePendingDelay | Atraso após o qual uma solicitação que aguarda a confirmação da exclusão é cancelada. |
| Privacy_Request_MaxErrorAllowed | Número máximo de erros permitidos ao processar ou excluir uma solicitação de acesso a dados pessoais. |
| Privacy_Request_PurgeDelay | Atraso entre a criação de uma solicitação na fila e a exclusão de seus dados. |

Saiba mais sobre solicitações de privacidade em [Gerenciar solicitações de privacidade](../start/privacy.md).

### Trilha de auditoria {#audit-trail-options}

Defina uma opção de trilha de auditoria como 1 para ativar a trilha de auditoria para uma entidade ou como 0 para desativá-la: XtkAudit_Workflows, XtkAudit_DataSchema, XtkAudit_Option, XtkAudit_Delivery, XtkAudit_ExtAccount, XtkAudit_DeliveryMapping, XtkAudit_WebApp, XtkAudit_Offer, XtkAudit_Operator. Use XtkAudit_Enable_All para cada entidade. Saiba mais em [Trilha de auditoria](../reporting/audit-trail.md#enable-disable-audit-trail).

### Integrações e pesquisas {#integration-options}

| Opção | Descrição |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Credenciais do Adobe Developer Console usadas para páginas de aterrissagem com o Adobe Experience Platform. [Saiba mais](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_<instance>_<activity> | Data da última sincronização da atividade genérica do Conector CRM. Criar manualmente como uma opção de texto, no formato `yyyy/MM/dd hh:mm:ss`. [Saiba mais](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | Crie-o e defina-o como 1 para salvar uma cópia das respostas brutas por padrão para todas as pesquisas. [Saiba mais](../dev/surveys/managing-answers.md) |

## Tópicos relacionados {#related-topics}

* [Pacotes incorporados](built-in-packages.md)
* [Princípios globais](general-architecture.md)
* [Guia de rotação de credenciais](../../technotes/security/credential-rotation-guide.md)
