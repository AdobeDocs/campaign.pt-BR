---
audience: user
user-guide-title: Guia de automação de campanha
user-guide-description: Guia de automação de campanha
source-git-commit: 7fe079c5473fa164405753c2be6cc8be16329f58
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 87%

---


# Guias de automação de campanha {#automation}

+ [Guia de automação de campanha](home.md)
+ Automatizar com workflows {#workflows}
   + Introdução a workflows {#introduction}
      + [Sobre workflows](workflow/about-workflows.md)
      + Tipos de workflows {#wf-type}
         + [Fluxos de trabalho para construção do target](workflow/targeting-workflows.md)
         + [Fluxos de trabalho da campanha](workflow/campaign-workflows.md)
         + [Workflows técnicos](workflow/technical-workflows.md)
      + [Criar um workflow](workflow/build-a-workflow.md)
      + [Práticas recomendadas](workflow/workflow-best-practices.md)
      + [Usar dados de fluxo de trabalho](workflow/use-workflow-data.md)
   + Executar um fluxo de trabalho {#executing-a-workflow}
      + [Iniciar um fluxo de trabalho](workflow/start-a-workflow.md)
      + [Ciclo de vida do fluxo de trabalho](workflow/workflow-life-cycle.md)
      + [Configurar aprovações](workflow/define-approvals.md)
   + Monitorar workflows {#monitoring-workflows}
      + [Monitorar a execução do fluxo de trabalho](workflow/monitor-workflow-execution.md)
      + [Monitorar workflows técnicos](workflow/monitor-technical-workflows.md)
      + [Workflow HeatMap](workflow/heatmap.md)
   + Atividades de fluxos de trabalho {#wf-activities}
      + [Introdução a atividades](workflow/activities.md)
      + Atividades de direcionamento {#targeting-activities}
         + [Lista de atividades de direcionamento](workflow/targeting-activities.md)
         + [Células](workflow/cells.md)
         + [Alterar fonte de dados](workflow/change-data-source.md)
         + [Mudar dimensão](workflow/change-dimension.md)
         + [Conector CRM](workflow/crm-connector.md)
         + [Desduplicação](workflow/deduplication.md)
         + [Outline de entrega](workflow/delivery-outline.md)
         + [Editar esquema](workflow/edit-schema.md)
         + [Enriquecimento](workflow/enrichment.md)
         + [Exclusão](workflow/exclusion.md)
         + [Consulta incremental](workflow/incremental-query.md)
         + [Intersecção](workflow/intersection.md)
         + [Atualização de lista](workflow/list-update.md)
         + [Ofertas por célula](workflow/offers-by-cell.md)
         + [Mecanismo de oferta](workflow/offer-engine.md)
         + [Consulta](workflow/query.md)
         + [Lista de leitura](workflow/read-list.md)
         + [Divisão](workflow/split.md)
         + [Serviços de assinatura](workflow/subscription-services.md)
         + [União](workflow/union.md)
         + [Atualizar dados](workflow/update-data.md)
      + Atividades de controle de fluxo {#flow-control-activities}
         + [Lista de atividades de controlo de fluxo](workflow/flow-control-activities.md)
         + [Alerta](workflow/alert.md)
         + [AND-join](workflow/and-join.md)
         + [Aprovação](workflow/approval.md)
         + [Sinal externo](workflow/external-signal.md)
         + [Bifurcação](workflow/fork.md)
         + [Jump (ponto inicial e ponto final)](workflow/jump--start-point-and-end-point-.md)
         + [Início e término](workflow/start-and-end.md)
         + [Scheduler](workflow/scheduler.md)
         + [Sub-workflow](workflow/sub-workflow.md)
         + [Teste](workflow/test.md)
         + [Restrição de tempo](workflow/time-constraint.md)
         + [Aguardar](workflow/wait.md)
      + Atividades de ação {#action-activities}
         + [Lista de atividades](workflow/action-activities.md)
         + [Gerenciamento de conteúdo](workflow/content-management.md)
         + [Entrega contínua](workflow/continuous-delivery.md)
         + [Entregas entre canais](workflow/cross-channel-deliveries.md)
         + [Extração de dados (arquivo)](workflow/extraction--file-.md)
         + [Carregamento de dados (arquivo)](workflow/data-loading--file-.md)
         + [Carregamento de dados (RDBMS)](workflow/data-loading--rdbms-.md)
         + [Delivery](workflow/delivery.md)
         + [Controle de Delivery](workflow/delivery-control.md)
         + [Aprovação local](workflow/local-approval.md)
         + [Carregamento (SOAP)](workflow/loading-soap.md)
         + [Módulo nlserver](workflow/nlserver-module.md)
         + [Entrega recorrente](workflow/recurring-delivery.md)
         + [Código SQL e código JavaScript](workflow/sql-code-and-javascript-code.md)
         + [Gerenciamento de dados SQL](workflow/sql-data-management.md)
         + [Atualizar agregado](workflow/update-aggregate.md)
      + Atividades de evento {#event-activities}
         + [Lista de atividades de evento](workflow/event-activities.md)
         + [File collector](workflow/file-collector.md)
         + [Transferência de arquivos](workflow/file-transfer.md)
         + [Emails de entrada](workflow/inbound-emails.md)
         + [SMS de entrada](workflow/inbound-sms.md)
         + [Download da Web](workflow/web-download.md)
   + Casos de uso {#use-cases}
      + [Sobre casos de uso de fluxo de trabalho](workflow/workflow-use-cases.md)
      + Entregas {#deliveries}
         + [Usar a atividade de aprovação local](workflow/local-approval-activity.md)
         + [Enviar email de aniversário](workflow/send-a-birthday-email.md)
         + [Carregar conteúdo de entrega](workflow/load-delivery-content.md)
         + [Fluxo de trabalho de entrega entre canais](workflow/cross-channel-delivery-workflow.md)
         + [Enriquecimento de email com campos de data personalizados](workflow/email-enrichment-with-custom-date-fields.md)
      + Monitoramento {#monitoring}
         + [Enviar um relatório a uma lista](workflow/send-a-report-to-a-list.md)
         + [Supervisionar os workflows](workflow/workflow-supervision.md)
         + [Enviar alertas personalizados aos operadores](workflow/send-alerts-to-operators.md)
      + Gerenciamento de dados {#data-management}
         + [Coordenar atualizações de dados](workflow/coordinate-data-updates.md)
         + [Criar uma lista de resumo](workflow/create-a-summary-list.md)
         + [Enriquecer dados](workflow/enrich-data.md)
         + [Usar agregações](workflow/using-aggregates.md)
         + [Usar a funcionalidade de mesclagem da atividade de desduplicação](workflow/deduplication-merge.md)
         + [Configurar um fluxo de trabalho de importação recorrente](workflow/recurring-import-workflow.md)
      + Criar consultas {#designing-queries}
         + [Atualização da lista trimestral usando uma consulta incremental](workflow/quarterly-list-update.md)
      + Consulta e filtro {#designing-queries}
         + [Consultar a tabela de recipients](workflow/querying-recipient-table.md)
         + [Consultar informações da entrega](workflow/query-delivery-info.md)
         + [Calcular agregados](workflow/compute-aggregates.md)
         + [Consultar usando gerenciamento de agrupamento](workflow/query-grouping-management.md)
         + [Consultar usando um relacionamento muitos para muitos](workflow/query-many-to-many-relationship.md)
         + [Adicionar um campo calculado do tipo lista discriminada](workflow/adding-enumeration-type-calculated-field.md)
         + [Criar um filtro](workflow/create-a-filter.md)
         + [Filtrar recipients duplicados](workflow/filter-duplicated-recipients.md)
   + Configurações avançadas {#advanced-management}
      + [Propriedades do fluxo de trabalho](workflow/workflow-properties.md)
      + [Parâmetros avançados](workflow/advanced-parameters.md)
      + [Modelos e scripts JavaScript](workflow/javascript-scripts-and-templates.md)
      + [Exemplos de código JavaScript em workflows](workflow/javascript-in-workflows.md)
      + [Acessar um banco de dados externo](workflow/accessing-an-external-database--fda-.md)
      + [Gerenciar permissões](workflow/managing-rights.md)
      + [Alterar imagens de atividade](workflow/change-activity-images.md)
      + [Gerenciar fusos horários](workflow/managing-time-zones.md)
+ Orquestração de campanha {#campaign-orchestration}
   + [Introdução a campanhas de marketing](campaigns/set-up-campaigns.md)
   + [Criar programas e campanhas](campaigns/marketing-campaign-create.md)
   + [Criar e configurar modelos](campaigns/marketing-campaign-templates.md)
   + [Adicionar entregas](campaigns/marketing-campaign-deliveries.md)
   + [Selecionar o público](campaigns/marketing-campaign-target.md)
   + [Gerenciar documentos e ativos](campaigns/marketing-campaign-assets.md)
   + [Configurar e gerenciar aprovações](campaigns/marketing-campaign-approval.md)
   + [Campanhas recorrentes e periódicas](campaigns/recurring-periodic-campaigns.md)
   + [Monitorar suas campanhas](campaigns/marketing-campaign-monitoring.md)
   + [Provedores, estoques e orçamentos](campaigns/providers--stocks-and-budgets.md)
+ Otimização de campanha (complemento){#campaign-optimization}
   + [Introdução às tipologias de campanha](campaign-opt/campaign-typologies.md)
   + [Regras de filtro](campaign-opt/filtering-rules.md)
   + [Regras de controle](campaign-opt/control-rules.md)
   + [Regras de pressão](campaign-opt/pressure-rules.md)
   + [Regras de consistência](campaign-opt/consistency-rules.md)
   + [Aplicar regras](campaign-opt/apply-rules.md)
   + [Simulações de campanha](campaign-opt/campaign-simulations.md)
+ Marketing distribuído (complemento) {#distributed-marketing}
   + [Sobre marketing distribuído](distributed-marketing/about-distributed-marketing.md)
   + [Criar uma campanha local](distributed-marketing/creating-a-local-campaign.md)
   + [Criar uma campanha colaborativa](distributed-marketing/creating-a-collaborative-campaign.md)
   + [Publicar o pacote da campanha](distributed-marketing/publishing-the-campaign-package.md)
   + [Acessar campanhas](distributed-marketing/accessing-campaigns.md)
   + [Rastrear uma campanha](distributed-marketing/tracking-a-campaign.md)
   + [Casos de uso](distributed-marketing/examples.md)
+ [Documentação do Campaign v8](https://experienceleague.adobe.com/docs/campaign/campaign-v8/campaign-home.html?lang=pt-BR)