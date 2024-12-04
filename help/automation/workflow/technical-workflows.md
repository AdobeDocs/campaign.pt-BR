---
product: campaign
title: Workflows técnicos
description: Saiba mais sobre os workflows técnicos disponíveis com o Campaign
feature: Workflows
role: User, Admin
exl-id: 2693856c-80b2-4e35-be8e-2a9760f8311f
source-git-commit: 97ab8259c0044b65fec2ad5ddc44d28f0cbf65e5
workflow-type: tm+mt
source-wordcount: '1804'
ht-degree: 80%

---

# Workflows técnicos{#about-technical-workflows}

O Adobe Campaign vem com um conjunto de workflows técnicos incorporados. Eles controlam operações e tarefas agendadas para execução periódica no servidor. Os workflows técnicos executam operações de manutenção no banco de dados do Campaign, gerenciam dados de rastreamento em deliveries e também configuram processos provisionais em deliveries.

Por padrão, os fluxos de trabalho técnicos estão disponíveis em uma subpasta do seguinte nó **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**.

![](assets/navtree.png){width="50%" align="center" zoomable="yes"}

>[!NOTE]
>
>* A lista de fluxos de trabalho técnicos instalados com cada módulo está disponível em uma [esta seção](#list-technical-workflows).
>
>* Os fluxos de trabalho técnicos relacionados ao complemento do Centro de Mensagens são armazenados por padrão no nó **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Message Center]** > **[!UICONTROL Technical workflows]**.

A subpasta **[!UICONTROL Campaign process]** centraliza os fluxos de trabalho necessários para executar processos nas campanhas: notificação de tarefa, gestão de estoque, cálculo de custos, etc.

![](assets/campaign-processes-wf.png){width="70%" align="center" zoomable="yes"}


## Gerenciar e criar workflows técnicos {#manage-tech-workflows}

Os fluxos de trabalho técnicos do Campaign só podem ser iniciados e modificados por operadores com permissões de **Administração**. Saiba como monitorar workflows técnicos nesta [seção dedicada](monitor-technical-workflows.md).

Você pode criar fluxos de trabalho técnicos personalizados no nó **[!UICONTROL Administration > Production > Technical workflows]** da estrutura da árvore. Templates nativos estão disponíveis para criar workflows técnicos. Eles podem ser configurados para atender às suas necessidades. No entanto, esse processo é reservado para usuários especialistas. As atividades disponíveis em workflows técnicos são as mesmas para workflows para construção do target. [Saiba mais](targeting-workflows.md).

## Lista de workflows técnicos {#list-technical-workflows}

Os workflows detalhados nesta página são instalados com os pacotes integrados do Adobe Campaign. Esses pacotes e os fluxos de trabalho técnicos associados dependem do contrato de licença e dos complementos.

| Fluxo de trabalho técnico | Pacote | Descrição |
|------|--------|-----------|
| **Limpeza de alias** (aliasCleansing) | Instalado por padrão | Esse workflow padroniza os valores de enumeração. É acionado todos os dias às 3h por padrão. |
| **Faturamento** (billing) | Instalado por padrão | Esse fluxo de trabalho envia o relatório de atividades do sistema para o operador &quot;faturamento&quot; por email. É acionado todo dia 25 de cada mês na instância de marketing. |
| **Processos do Campaign** (operationMgt) | Instalado por padrão | Esse fluxo de trabalho gerencia os processos das campanhas de marketing (inicia o direcionamento, faz a extração de arquivos etc.). Ele também cria workflows relacionados a campanhas recorrentes e periódicas. |
| **Coletar dados para o serviço HeatMap** (collectDataHeatMapService) | Instalado por padrão | Esse fluxo de trabalho recupera dados exigidos pelo serviço HeatMap. |
| **Coletar solicitações de privacidade** (collectPrivacyRequests) | Regulamento de Proteção de Dados de Privacidade | Esse fluxo de trabalho gera os dados do destinatário armazenados no Adobe Campaign e os disponibiliza para baixar na tela de solicitação de privacidade. |
| **Cálculo de custo** (budgetMgt) | Instalado por padrão | Esse fluxo de trabalho inicia o cálculo das linhas de despesas e custos nos orçamentos, planos, programas, campanhas, entregas e tarefas. |
| **Limpeza do banco de dados** (limpeza) | Instalado por padrão | Este é o fluxo de trabalho manutenção do banco de dados: faz diferentes cálculos das estatísticas e dos processos e exclui dados obsoletos do banco de dados de acordo com a configuração definida no assistente de implantação. É acionado todos os dias às 4h por padrão. |
| **Excluir usuários do LINE bloqueados** (deleteBlockedLineUsersV2) | Canal LINE | Esse fluxo de trabalho garante que os dados dos usuários do LINE V2 sejam excluídos após bloquearem a conta oficial do LINE por 180 dias. |
| **Excluir dados de solicitação de privacidade** (deletePrivacyRequestsData) | Regulamento de Proteção de Dados de Privacidade | Esse fluxo de trabalho exclui os dados do destinatário armazenados no Adobe Campaign. |
| **Indicadores de entrega** (deliveryIndicators) | Instalado por padrão | Esse fluxo de trabalho atualiza os indicadores de rastreamento de entrega para uma entrega. Esse fluxo de trabalho é acionado a cada hora por padrão. |
| **Processos de marketing distribuído** (centralLocalMgt) | Marketing central/local (Marketing distribuído) | Este fluxo de trabalho inicia o processamento relacionado ao uso do módulo de marketing distribuído. Ele inicia a criação de campanhas locais e gerencia notificações de pedidos e disponibilidade de pacotes de campanha. |
| **Limpeza de evento** (webAnalyticsPurgeWebEvents) | Conectores de análise da Web | Esse fluxo de trabalho permite excluir todos os eventos do campo de banco de dados de acordo com o período configurado no campo Vida útil. |
| **Exportar audiências para a Adobe Experience Cloud** (exportSharedAudience) | Integração com a Adobe Experience Cloud | Esse fluxo de trabalho exporta públicos-alvo como públicos-alvo/segmentos compartilhados. Esses públicos-alvo podem ser usados nas diferentes soluções da Adobe Experience Cloud que você usa. |
| **ffdaUnsubscribe** | Instalado por padrão | Esse fluxo de trabalho manipula cancelamentos de assinatura recebidos como emails devolvidos (por meio do uso do método List-Unsubscribe `<mailto>`). Ele é executado diariamente, a cada 1h, apenas em instâncias de marketing com uma implantação corporativa (FFDA).<br/><br/>O fluxo de trabalho verifica broadlogs de um determinado intervalo de tempo (hora do último processamento e hora atual) que são marcados como rejeições de unsubscription pelo módulo inMail (marca definida na coluna iFlags da tabela NmsBroadLog) e processa uma unsubscription dependendo se o serviço da broadlog estiver definido ou não:<ul><li>Incluir na lista de bloqueios Se serviceId for 0 (não definido), o recipient será.</li><li>Se a serviceId não for 0 (vinculada a um serviço existente), a subscrição do recipient será cancelada desse serviço.</li></ul><br/>Observação: este fluxo de trabalho trata apenas de cancelamentos de assinatura rejeitados; os cancelamentos de assinatura feitos por meio de link para opção de não participação e cancelamento de assinatura com um clique (método de URL) são tratados separadamente fora deste fluxo de trabalho. |
| **Previsão** (forecasting) | Instalado por padrão | Esse fluxo de trabalho analisa as entregas salvas no calendário provisional (cria logs provisionais). É acionado todos os dias à 1h por padrão. |
| **Cálculo agregado completo (propositionrcp cube)** (agg_nmspropositionrcp_full) | Dispositivo de oferta (interação) | Esse fluxo de trabalho atualiza o agregado completo do cubo de apresentação da oferta. É acionado todos os dias às 6h por padrão. Esse agregado captura as seguintes dimensões: canal, entrega, oferta de marketing e data. O cubo de apresentação da oferta é usado para gerar relatórios com base em ofertas. Saiba mais sobre cubos em [esta seção](../../v8/reporting/gs-cubes.md). |
| **Identificação de contatos convertidos** (webAnalyticsFindConverted) | Conectores de análise da Web | Esse fluxo de trabalho indexa os visitantes do site que concluíram sua compra após uma campanha de remarketing. Os dados recuperados por esse fluxo de trabalho podem ser acessados no relatório de eficiência de remarketing (consulte esta página). |
| **Importar audiências da Adobe Experience Cloud** (importSharedAudience) | Integração com a Adobe Experience Cloud | Esse fluxo de trabalho permite importar públicos-alvo/segmentos de diferentes soluções da Adobe Experience Cloud para o Adobe Campaign. |
| **Processos de entregas em campanhas** (deliveryMgt) | Instalado por padrão | Esse fluxo de trabalho aciona as entregas aprovadas e inicia o pós-processamento no provedor de serviços para uma entrega externa. Também envia notificações e lembretes de aprovação. |
| **Processos de provedores de serviços** (supplierMgt) | Instalado por padrão | Esse fluxo de trabalho inicia processos do provedor de serviços (email para o roteador e o pós-processamento) após a aprovação de entregas. |
| **Migração do MID para LineUserID** (MIDToUserIDMigration) | Canal LINE | Esse fluxo de trabalho gera a ID de usuários do LINE V2 para a migração de LINE V1 para LINE V2. |
| **Centro de mensagens &lt;external_account_name>** (mcSynch_&lt;external_account_name>) | Controle de mensagens transacionais (Centro de mensagens - Controle) | Esse fluxo de trabalho: <ul><li>recupera a lista de eventos processados pela(s) operação(s).</li><li>sincroniza com a tabela NmsBroadLogMsg para recuperar as qualificações da mensagem de entrega.</li><li>recupera logs de entrega de eventos assim que a sincronização com a tabela NmsBroadLogMsg for concluída.</li><li>sincroniza com a tabela NmsTrackingUrl para recuperar o rastreamento para as URLs de entrega.</li><li>recupera as URLs de rastreamento de eventos assim que a sincronização com a tabela NmsTrackingUrl for concluída.</li><li>permite recuperar todos os endereços de email colocados em quarentena a cada três horas após o envio de uma entrega.</li></ul> |
| **Cálculo agregado completo do MessageCenter** (agg_messageCenter_full) | Controle de mensagens transacionais (Centro de mensagens - Controle) | Esse fluxo de trabalho atualiza o agregado completo para o cubo do centro de mensagens. É acionado todos os dias às 3h por padrão. Esse agregado captura as seguintes dimensões: canal, data, status e tipo de evento. O cubo do centro de mensagens é usado para gerar relatórios com base em eventos. Você pode saber mais sobre cubos em  |
| **Mid-sourcing (contadores de entrega)** (defaultMidSourcingDlv) | Transferência para mid-sourcing | Esse fluxo de trabalho coleta informações de contagem para entregas no servidor mid-sourcing. Informações de contagem incluem indicadores de entregas gerais, como número de entregas enviadas, etc. As informações de rastreamento, como aberturas, não são incluídas. É acionado a cada dez minutos por padrão. |
| **Mid-sourcing (logs de entrega)** (defaultMidSourcingLog) | Transferência para mid-sourcing | Esse fluxo de trabalho coleta logs da entrega no servidor mid-sourcing. É acionado a cada hora por padrão. |
| **Gerenciamento de recusa de NMAC** (mobileAppOptOutMgt) | Canal de aplicativo móvel (push) | Esse workflow atualiza a notificação de unsubscriptions em dispositivos móveis. É acionado a cada 6 horas entre 1:00 AM e meia-noite. |
| **Notificação de oferta** (offerMgt) | Instalado por padrão | Esse fluxo de trabalho implanta ofertas aprovadas no ambiente online, bem como todas as categorias contidas no catálogo de oferta. |
| **Limpeza de fluxos de trabalho pausados** (cleanupPausedWorkflows) | Instalado por padrão | Triggers is translated correctly in this case. Esse fluxo de trabalho analisa fluxos de trabalho pausados que têm a severidade definida como normal e emite avisos e notificações quando ficam pausados por muito tempo. Após um mês, os workflows técnicos pausados são interrompidos definitivamente. Por padrão, é acionado toda segunda-feira às 5h. Para obter mais informações, consulte[Tratamento de fluxos de trabalho pausados](monitor-workflow-execution.md#handling-of-paused-workflows). |
| **Limpeza de solicitação de privacidade** (cleanupPrivacyRequests) | Regulamento de Proteção de Dados de Privacidade | Esse fluxo de trabalho apaga os arquivos de solicitação de acesso criados há mais de 90 dias. |
| **Processamento de eventos em lote** (batchEventsProcessing) | Execução de mensagens transacionais (Centro de Mensagens - Execução) | Esse fluxo de trabalho permite colocar eventos em lote em uma fila antes de associá-los a um modelo de mensagem. |
| **Processamento de eventos em tempo real** (rtEventsProcessing) | Execução de mensagens transacionais (Centro de Mensagens - Execução) | Esse fluxo de trabalho permite colocar eventos em tempo real em uma fila antes de associá-los a um modelo de mensagem. |
| **Sincronização de apresentação** (propositionSynch) | Controle do mecanismo de oferta com instância de execução | Esse fluxo de trabalho sincroniza as apresentações entre a instância de marketing e a instância de execução usada para interações. |
| **Recuperação de eventos da Web** (webAnalyticsGetWebEvents) | Conectores de análise da Web | A cada hora, esse fluxo de trabalho baixa segmentos do comportamento do usuário na Internet em um determinado site, os coloca no banco de dados do Adobe Campaign e inicia o fluxo de trabalho de remarketing. |
| **Agregados de relatórios** (reportingAggregates) | Entrega | Esse fluxo de trabalho atualiza agregados usados em relatórios. É acionado todos os dias às 2h por padrão. |
| **Envio de indicadores e atributos de campanha** (webAnalyticsSendMetrics) | Conectores de análise da Web | Esse fluxo de trabalho permite enviar indicadores de campanha de email do Adobe Campaign para o Adobe Experience Cloud Suite por meio do conector do Adobe® Analytics. Os indicadores relacionados são: Enviado (iSent), Contagem total de aberturas (iTotalRecipientOpen), Número total de destinatários que clicaram (iTotalRecipientClick), Erros (iError), Recusa (opt-out) (iOptOut). |
| **Estoque: pedidos e alertas** (stockMgt) | Instalado por padrão | Esse fluxo de trabalho inicia o cálculo de estoque nas linhas de pedido e gerencia os limites de aviso. |
| **Sincronizar aplicativos móveis da Coleção de dados da Adobe Experience Platform** (syncWithLaunch) | Instalado por padrão, a partir da v8.5 | Este fluxo de trabalho sincronizará automaticamente as propriedades móveis com o Adobe Campaign a partir da Coleção de dados. |
| **Rastreamento** (rastreamento) | Instalado por padrão | Esse workflow realiza a recuperação e a consolidação de informações de rastreamento. Também garante o recálculo de rastreamento e estatísticas de entrega, principalmente aqueles usados pelos workflows de arquivamento do Centro de Mensagens. Por padrão, é acionado uma vez por hora. |
| **Atualizar status do evento** (updateEventsStatus) | Execução de mensagens transacionais (Centro de Mensagens - Execução) | Esse fluxo de trabalho permite atribuir um status a um evento. Os status do evento são descritos a seguir:<ul><li>Pendente: o evento está em uma fila. Nenhum modelo de mensagem foi associado a ele.</li><li>Entrega pendente: o evento está em uma fila, um modelo de mensagem foi associado a ele e está sendo processado no momento pela entrega.</li><li>Enviada: esse status é copiado dos logs da entrega. Significa que a entrega foi enviada.</li><li>Ignorado pela entrega: esse status é copiado dos logs da entrega. Significa que a entrega foi ignorada.</li><li>Erro de entrega: esse status é copiado dos logs da entrega. Significa que a entrega falhou.</li><li>Evento não coberto: o evento falhou ao ser associado a um modelo de mensagem. O evento não será reprocessado.</li></ul> |
| **Atualização para capacidade de entrega** (deliverabilityUpdate) | Instalado por padrão | Depois que o pacote de monitoramento de capacidade de entrega (capacidade de entrega por email) é instalado, esse fluxo de trabalho é executado durante à noite e gerencia as regras de qualificação de emails rejeitados, bem como a lista de domínios e MXs. Isso requer que a porta HTTPS esteja aberta na plataforma. |
