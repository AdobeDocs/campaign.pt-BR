---
audience: end-user
user-guide-title: Campaign v8
user-guide-description: Documentação do produto do Adobe Campaign v8 (console do cliente).
title: Documentação do Adobe Campaign v8
description: Documentação do Campaign v8
breadcrumb-title: Documentação do Campaign v8
source-git-commit: 338013ac999ae0fedac132adf730c6f9477d73ca
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 97%

---


# Documentação do Adobe Campaign v8 (console) {#campaign-v8}

+ [Documentação do Campaign v8](campaign-home.md)
+ Notas de versão {#releases}
   + [Notas de versão antecipadas](start/e-release-notes.md)
   + [Versões e atualizações](start/upgrades.md)
   + [Versões mais recentes](start/release-notes.md)
   + Versões anteriores {#previous-rn}
      + [2025](start/release-notes-2025.md)
      + [2024](start/release-notes-2024.md)
      + [2023](start/release-notes-2023.md)
      + [2022](start/release-notes-2022.md)
      + [2021](start/release-notes-2021.md)
   + [Medidas de proteção](start/ac-guardrails.md)
   + [Problemas conhecidos](start/known-issues.md)
   + [Matriz de compatibilidade](start/compatibility-matrix.md)
   + [Atualizações da documentação](start/documentation-updates.md)
+ Introdução {#new}
   + [Introdução ao Adobe Campaign](start/get-started.md)
   + [Principais recursos](start/whats-new.md)
   + [Conheça a interface](start/campaign-ui.md)
   + [Conectar ao Campaign](start/connect.md)
   + [Componentes e processos](start/ac-components.md)
   + [Do Campaign Classic v7 para o v8](start/v7-to-v8.md)
   + [Do Campaign Standard ao v8](start/acs-to-v8.md)
   + [Perguntas frequentes](start/campaign-faq.md)
+ Gerenciamento de campanhas {#campaigns}
   + [Introdução às campanhas](start/campaigns.md)
   + [Orquestração de campanha >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=pt-BR)
+ Enviar mensagens{#send}
   + [Introdução a mensagens](start/gs-message.md)
   + [Criar a primeira entrega](start/create-message.md)
   + [Trabalho com modelos de entrega](send/create-templates.md)
   + [Práticas recomendadas de entrega](start/delivery-best-practices.md)
   + Emails {#emails}
      + [Criar e validar emails](send/email.md)
      + [Definir o conteúdo do email](send/defining-the-email-content.md)
      + [Definir o conteúdo interativo](send/defining-interactive-content.md)
      + [Link para a mirror page](send/mirror-page.md)
      + [Adicionar um endereço CCO](send/email-bcc.md)
      + [Definir parâmetros de email adicionais](send/email-parameters.md)
      + [Enviar e monitorar emails](send/send.md)
      + [Enviar emails em dispositivos móveis japoneses](send/sending-emails-on-japanese-mobiles.md)
      + [Anexar arquivos a um email](send/attaching-files.md)
   + SMS {#sms}
      + [Introdução a SMS](send/sms/sms.md)
      + Configurar canal de SMS {#config-sms}
         + [Configurações de entrega de SMS](send/sms/sms-delivery-settings.md)
         + [Configurações da conta externa de SMPP](send/sms/smpp-external-account.md)
         + [Características do canal de SMS](send/sms/sms-channel.md)
         + [Validando uma conexão de SMPP](send/sms/smpp-connection.md)
         + [Instância independente](send/sms/sms-standalone-instance.md)
         + [Infraestrutura de mid-sourcing](send/sms/sms-mid-sourcing.md)
         + [Descrição do conector de SMPP](send/sms/smpp-connector-delivery.md)
      + Criar um SMS  {#create-sms}
         + [Criar uma entrega de SMS](send/sms/create-sms.md)
         + [Definição do conteúdo](send/sms/sms-content.md)
         + [Selecionar o público-alvo](send/sms/sms-audience.md)
      + Validar e enviar SMS {#validate-sms}
         + [Enviar provas por SMS](send/sms/sms-proofs.md)
         + [Enviar ao público-alvo](send/sms/sms-send.md)
      + [Monitorar e rastrear SMS](send/sms/sms-monitor.md)
   + Notificações por push {#push}
      + [Criar e enviar notificações por push](send/push.md)
      + Push avançado {#rich-push}
         + [Criar uma entrega de push avançada para Android](send/rich-push-android.md)
         + [Criar uma entrega por push avançada para iOS](send/rich-push-ios.md)
      + [Configurar canal de notificação por push](send/push-settings.md)
      + [Configurar as notificações por push com a Coleção de dados](send/push-data-collection.md)
   + [Mensagens LINE](send/line.md)
   + [Correspondência direta](send/direct-mail.md)
   + [X (Twitter)](send/twitter.md)
   + [Canal externo personalizado](send/custom-channel.md)
   + Personalizar conteúdo {#personalize}
      + [Introdução à personalização](send/personalize.md)
      + [Dados de personalização](send/personalization-data.md)
      + [Adicionar campos de personalização](send/personalization-fields.md)
      + [Usar blocos de personalização](send/personalization-blocks.md)
      + [Criar condições](send/conditions.md)
   + Validar e enviar a entrega {#validate}
      + [Visualização e provas](send/preview-and-proof.md)
      + [Análise de entrega](send/delivery-analysis.md)
      + [Configurar e enviar a entrega](send/configure-and-send.md)
      + [Otimização da hora de envio](send/predictive.md)
   + Falhas, rejeições e quarentenas {#failures}
      + [Quarentena](send/quarantines.md)
      + [Falhas de entrega](send/delivery-failures.md)
   + Gerenciamento de capacidade de entrega {#deliverability-management}
      + [O que é capacidade de entrega](send/about-deliverability.md)
      + [Controlar conteúdo da mensagem](send/control-message-content.md)
      + [Monitoramento da capacidade de entrega](send/monitoring-deliverability.md)
      + [Renderização da caixa de entrada](send/inbox-rendering.md)
      + [SpamAssassin](send/spamassassin.md)
   + Mensagens transacionais {#real-time}
      + [Introdução a mensagens transacionais](send/transactional.md)
      + [Criação e publicação do seu modelo](send/transactional-template.md)
      + Gerenciamento de eventos {#event}
         + [Coletar e processar eventos](send/event-processing.md)
         + [Entender a descrição do evento](send/event-description.md)
         + [Enviar e monitorar mensagens](send/delivery-execution.md)
+ Gerenciamento de público-alvo e perfil {#audience}
   + [Introdução a perfis e públicos-alvo](audiences/gs-audiences.md)
   + [Trabalhar com públicos-alvo](start/audiences.md)
   + [Acessar perfis](audiences/view-profiles.md)
   + Adicionar perfis {#add-profiles}
      + [Criar perfis manualmente](audiences/create-profiles.md)
      + [Importar perfis de um arquivo](audiences/import-profiles.md)
      + [Trabalhar com perfis externos](audiences/external-profiles.md)
      + [Coletar dados de perfil em formulários web](audiences/collect-profiles.md)
      + [Trabalhar com target mappings](audiences/target-mappings.md)
      + [Criar perfis de teste](audiences/test-profiles.md)
   + Criar públicos-alvo {#create-audiences}
      + [Criar uma lista de contatos](audiences/create-audiences.md)
      + [Criar e gerenciar filtros](audiences/create-filters.md)
      + [Compartilhar públicos-alvo com soluções da Adobe](start/shared-audiences.md)
   + [Práticas recomendadas](audiences/audiences-best-practices.md)
   + [Gerenciar assinaturas](start/subscriptions.md)
+ Gerenciamento de conteúdo {#content}
   + [Criar páginas de destino](dev/landing-pages.md)
   + [Criar aplicativos e formulários web](dev/webapps.md)
+ Automação e fluxos de trabalho {#automation}
   + [Guia de automação de campanha >](https://experienceleague.adobe.com/pt-br/docs/campaign/automation/home)
+ Gerenciamento de privacidade e segurança {#privacy}
   + [Gerenciar solicitações de privacidade](start/privacy.md)
   + [Diretrizes de segurança](config/security.md)
   + [Complemento de segurança aprimorado](config/enhanced-security.md)
+ Gestão de decisões {#offers}
   + [Introdução à interação em tempo real](interaction/interaction.md)
   + [Ambientes e arquitetura](interaction/interaction-architecture.md)
   + [Práticas recomendadas](interaction/interaction-best-practices.md)
   + Definir configurações{#interaction-settings}
      + [Criar operadores](interaction/interaction-operators.md)
      + [Criar ambientes](interaction/interaction-env.md)
      + [Criar filtros predefinidos](interaction/interaction-predefined-filters.md)
      + [Criar espaços de oferta](interaction/interaction-offer-spaces.md)
   + [Criar um catálogo de oferta](interaction/interaction-offer-catalog.md)
   + [Criar uma oferta](interaction/interaction-offer.md)
   + [Enviar uma oferta (saída)](interaction/interaction-send-offers.md)
   + Apresentar uma oferta (entrada){#inbound}
      + [Contexto](interaction/interaction-present-offers.md)
      + [Chamar uma oferta em uma página da web](interaction/interaction-integration.md)
      + [Gerenciar interações anônimas](interaction/anonymous-interactions.md)
   + [Relatórios e histórico](interaction/interaction-tracking.md)
   + [Casos de uso](interaction/interaction-use-cases.md)
+ Relatórios e análises {#analytics}
   + [Rastrear e monitorar](start/tracking.md)
   + [Trilha de auditoria](reporting/audit-trail.md)
   + Trabalho com relatórios{#reports}
      + [Introdução aos relatórios](reporting/gs-reporting.md)
      + Criar cubos{#cubes}
         + [Introdução aos cubos](reporting/gs-cubes.md)
         + [Criar um cubo](reporting/cube-indicators.md)
         + [Usar cubos para criar relatórios](reporting/cube-tables.md)
         + [Personalizar os seus cubos](reporting/customize-cubes.md)
      + Relatórios integrados{#ac-reports}
         + [Lista de relatórios integrados](reporting/built-in-reports.md)
         + [Relatórios globais](reporting/global-reports.md)
         + [Relatórios de entrega](reporting/delivery-reports.md)
         + [Cálculo de métricas integradas](reporting/metrics-calculation.md)
      + [Relatórios personalizados](reporting/custom-reports.md)
+ Gerenciamento de dados {#data}
   + [Introdução a workflows](config/workflows.md)
   + [Importar dados](start/import.md)
   + [Documentação do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=pt-BR)
+ Integrações {#connect}
   + [Conectar o Campaign a outras soluções](connect/integration.md)
   + Campaign + Experience Platform {#ac-aep}
      + [Compartilhar e sincronizar públicos-alvo e atributos de perfil](connect/ac-aep.md)
      + [Atualizar perfis da AEP a partir de landing pages do Campaign](connect/ac-aep-landing-pages.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Acionadores da Experience Cloud](connect/ac-triggers.md)
   + [Campaign + Workfront](connect/ac-workfront.md)
   + [Campaign + X (Twitter)](connect/ac-tw.md)
   + [Campaign + Banco de dados externo](connect/fda.md)
   + Campaign + seu CRM {#ac-crm}
      + [Introdução aos conectores CRM](connect/crm.md)
      + [Trabalhar com o Campaign e o SFDC](connect/ac-sfdc.md)
      + [Trabalhar com o Campaign e o Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Sincronizar dados](connect/crm-data-sync.md)
+ Administração {#admin}
   + Usuários e permissões {#permissions}
      + [Introdução a permissões](start/gs-permissions.md)
      + [Gerenciar permissões do usuário](start/manage-permissions.md)
      + [Adicionar permissões em pastas](start/folder-permissions.md)
   + [Painel de controle](config/self-service.md)
+ Arquitetura e configuração {#config}
   + Arquitetura do Campaign v8 {#architecture}
      + [Princípios globais](architecture/general-architecture.md)
      + [Modelos de arquitetura](architecture/architecture.md)
      + [Implantação de FDA no Campaign](architecture/fda-deployment.md)
      + Implantação corporativa (FFDA) {#ffda}
         + [O que é o FFDA do Campaign?](architecture/enterprise-deployment.md)
         + [Gerenciamento de chaves e unicidade](architecture/keys.md)
         + [Novas APIs](architecture/new-apis.md)
         + [Mecanismo de preparo da API](architecture/staging.md)
         + [Mecanismo de replicação](architecture/replication.md)
   + Implementação {#implement}
      + [Etapas de implementação](start/implement.md)
      + [Personalizar sua instância](dev/customize.md)
      + [Práticas recomendadas do modelo de dados](dev/datamodel-best-practices.md)
   + Definições e configuração {#configuration}
      + [Configurações da interface](config/ui-settings.md)
      + [Gerenciar pastas e visualizações](audiences/folders-and-views.md)
      + [Configurações de mensagens transacionais](config/transactional-msg-settings.md)
      + [Integrar os SDKs do Campaign ao seu aplicativo – PÁGINA DESCONTINUADA](config/push-config.md)
      + [Contas externas](config/external-accounts.md)
+ Recursos do desenvolvedor {#developer}
   + [Modelo de dados do Campaign](dev/datamodel.md)
   + Esquemas e formulários {#shemas-forms}
      + [Trabalhar com esquemas](dev/schemas.md)
      + [Criar esquemas](dev/create-schema.md)
      + [Estender esquemas](dev/extend-schema.md)
      + [Esquemas de filtro](dev/filter-schema.md)
      + [Estrutura de esquema](dev/schema-structure.md)
      + [Mapeamento de banco de dados](dev/database-mapping.md)
      + [Principais gerenciamentos](dev/database-keys.md)
      + [Gerenciamento de link](dev/database-links.md)
      + [Restringir visualização de IP](dev/restrict-pi-view.md)
      + [Usar tabela de destinatário personalizada](dev/custom-recipient.md)
      + [Atualizar o banco de dados](dev/update-database-structure.md)
      + [Formulários de entrada](dev/forms.md)
   + [Trabalhar com pacotes de dados](dev/packages.md)
   + [APIs do Campaign](dev/api.md)
   + REST APIs {#apis}
      + [Introdução às REST APIs](dev/api/get-started-apis.md)
      + [Recomendações e limitações](dev/api/limitations.md)
      + [Por que usar APIs REST](dev/api/why-using-campaign-standard-apis.md)
      + [Configuração do acesso à API](dev/api/setting-up-api-access.md)
      + Conceitos globais {#global-concepts}
         + [Leitura obrigatória](dev/api/must-read.md)
         + [Pontos de acesso](dev/api/endpoints.md)
         + [Mecanismo de metadados](dev/api/metadata-mechanism.md)
         + [Verbos](dev/api/verbs.md)
         + [Operações adicionais](dev/api/sorting.md)
         + [Recursos personalizados](dev/api/custom-resources.md)
      + [Interação com recursos personalizados](dev/api/interacting-with-custom-resources.md)
      + Gerenciamento de perfis {#managing-profiles}
         + [Recuperação de perfis](dev/api/retrieving-profiles.md)
         + [Atualização de perfis](dev/api/updating-profiles.md)
         + [Criação de perfis](dev/api/creating-profiles-api.md)
      + Gerenciamento de serviços e assinaturas {#managing-services-and-subscriptiopns}
         + [Criação de um serviço](dev/api/creating-a-service.md)
         + [Recuperação de subscrições](dev/api/retrieving-subscriptions.md)
         + [Realizar subscrições](dev/api/perform-subscriptions.md)
         + [Exclusão de subscrições](dev/api/deleting-subscriptions.md)
      + [Gerenciamento de mensagens transacionais](dev/api/managing-transactional-messages.md)
      + Gerenciamento de workflows {#managing-workflows}
         + [Controle de um fluxo de trabalho](dev/api/controlling-a-workflow.md)
         + [Acionamento de uma atividade de sinal](dev/api/triggering-a-signal-activity.md)
+ [Notas técnicas da campanha >](https://experienceleague.adobe.com/pt-br/docs/campaign/technotes-ac/technotes-home)
+ [Documentação da interface do Campaign Web>](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/campaign-web-home)

