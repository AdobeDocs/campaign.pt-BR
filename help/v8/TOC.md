---
audience: end-user
user-guide-title: Campaign v8
description: Documentação do Campaign v8
breadcrumb-title: Campaign v8
title: Documentos do Campaign v8
source-git-commit: 9fa6666532a6943c438268d7ea832f0908588208
workflow-type: ht
source-wordcount: '351'
ht-degree: 100%

---


# Documentação do Adobe Campaign v8 {#campaign-v8}

+ [Documentação do Campaign v8](campaign-home.md)
+ Novidades? {#new}
   + [Principais recursos](start/whats-new.md)
   + [Notas de versão](start/release-notes.md)
   + [Limitações conhecidas](start/known-limitations.md)
   + [Classic v7 para v8](start/capability-matrix.md)
+ Iniciar {#start}
   + [Introdução](start/get-started.md)
   + [Componentes e processos](start/ac-components.md)
   + Interface do Campaign {#ac-ui}
      + [Conheça a interface do Campaign](start/campaign-ui.md)
      + [Personalizar a interface do Campaign](start/customize-ui.md)
   + [Trabalhar com públicos](start/audiences.md)
   + [Gerenciar solicitações de privacidade](start/privacy.md)
   + [Importar dados](start/import.md)
   + [Criar campanhas](start/campaigns.md)
   + [Enviar mensagens](start/create-message.md)
   + [Gerenciar subscrições](start/subscriptions.md)
   + [Rastrear e monitorar](start/tracking.md)
   + [Métricas e relatórios](start/reporting.md)
   + [Perguntas frequentes](start/campaign-faq.md)
+ Arquitetura {#architecture}
   + [Princípios globais](architecture/general-architecture.md)
   + [Arquitetura](architecture/architecture.md)
   + Implantação do FDA no Snowflake{#fda}
      + [O que é o FDA-Snowflake?](architecture/fda-deployment.md)
   + Implantação corporativa (FFDA) {#ffda}
      + [O que é o FFDA do Campaign?](architecture/enterprise-deployment.md)
      + Características {#ffda-characteristics}
         + [Gerenciamento de chaves e unicidade](architecture/keys.md)
         + [Novas APIs](architecture/new-apis.md)
         + [Mecanismo de preparo da API](architecture/staging.md)
         + [Mecanismo de replicação](architecture/replication.md)
+ Implementar {#implement}
   + [Etapas de implementação](start/implement.md)
   + [Personalizar sua instância](dev/customize.md)
   + [Diretrizes de segurança](config/security.md)
   + [Criar aplicativos e formulários Web](dev/webapps.md)
   + [Práticas recomendadas do Modelo de dados](dev/datamodel-best-practices.md)
+ Implantar {#deploy}
   + [Matriz de compatibilidade](start/compatibility-matrix.md)
   + [Conectar-se ao Campaign](start/connect.md)
   + [Permissões](start/permissions.md)
   + [Painel de controle do Campaign](config/self-service.md)
+ Perfis e públicos {#profiles-and-audiences}
   + [Introdução](audiences/gs-audiences.md)
   + [Acessar perfis](audiences/view-profiles.md)
   + Adicionar perfis {#add-profiles}
      + [Criar perfis manualmente](audiences/create-profiles.md)
      + [Importar perfis de um arquivo](audiences/import-profiles.md)
      + [Trabalhar com perfis externos](audiences/external-profiles.md)
      + [Coletar dados de perfil em formulários web](audiences/collect-profiles.md)
   + Criar públicos {#create-audiences}
      + [Criar uma lista de contatos](audiences/create-audiences.md)
      + [Criar e gerenciar filtros](audiences/create-filters.md)
   + [Gerenciar pastas e visualizações](audiences/folders-and-views.md)
   + [Práticas recomendadas](audiences/audiences-best-practices.md)
+ Enviar mensagens{#send}
   + Emails {#emails}
      + [Criar e validar emails](send/email.md)
      + [Enviar e monitorar emails](send/send.md)
   + [SMS](send/sms.md)
   + [Notificações por push](send/push.md)
   + [Mensagens LINE](send/line.md)
   + [Correspondência direta](send/direct-mail.md)
   + [Marketing social](send/twitter.md)
   + [Mensagens transacionais](send/transactional.md)
   + Falhas, rejeições e quarentenas{#failures}
      + [Quarentenas](send/quarantines.md)
      + [Falhas de delivery](send/delivery-failures.md)
+ Interação em tempo real{#interaction}
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
+ Configurar {#config}
   + [Automatizar com workflows](config/workflows.md)
   + [Configurações de email](config/email-settings.md)
   + [Configurações de mensagens transacionais](config/transactional-msg-settings.md)
   + [Integrar os SDKs do Campaign ao seu aplicativo](config/push-config.md)
   + [Contas externas](config/external-accounts.md)
+ Conectar {#connect}
   + [Conectar-se a outras soluções](connect/integration.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Acionadores da Experience Cloud](connect/ac-triggers.md)
   + [Campaign + RTCDP](connect/ac-rtcdp.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + Banco de dados externo](connect/fda.md)
   + Campaign + seu CRM {#ac-crm}
      + [Introdução aos conectores CRM](connect/crm.md)
      + [Trabalhar com o Campaign e o SFDC](connect/ac-sfdc.md)
      + [Trabalhar com o Campaign e o Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Sincronizar dados](connect/crm-data-sync.md)
+ Recursos do desenvolvedor {#developer}
   + [Modelo de dados do Campaign](dev/datamodel.md)
   + Esquemas e formulários {#shemas-forms}
      + [Trabalhar com esquemas](dev/schemas.md)
      + [Criar esquemas](dev/create-schema.md)
      + [Estender schemas](dev/extend-schema.md)
      + [Esquemas de filtro](dev/filter-schema.md)
      + [Estrutura de esquema](dev/schema-structure.md)
      + [Mapeamento de banco de dados](dev/database-mapping.md)
      + [Restringir visualização de IP](dev/restrict-pi-view.md)
      + [Usar tabela de recipient personalizada](dev/custom-recipient.md)
      + [Atualizar o banco de dados](dev/update-database-structure.md)
      + [Formulários de entrada](dev/forms.md)
   + [APIs do Campaign](dev/api.md)
+ [Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR)

