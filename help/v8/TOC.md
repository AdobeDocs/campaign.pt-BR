---
audience: end-user
user-guide-title: Campaign v8
description: Documentação do Campaign v8
breadcrumb-title: Visão geral da campanha
title: Documentos do Campaign v8
source-git-commit: ec46a6f41d640b11306a88d6a966f81f8c2e43e0
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 87%

---


# Documentação do Adobe Campaign v8 {#campaign-v8}

+ [Documentação do Campaign v8](campaign-home.md)
+ Versões e atualizações mais recentes {#releases}
   + [Notas de versão anteriores](start/e-release-notes.md)
   + [Notas de versão](start/release-notes.md)
   + [Medidas de proteção](start/ac-guardrails.md)
   + [Problemas conhecidos](start/known-issues.md)
   + [Matriz de compatibilidade](start/compatibility-matrix.md)
+ Introdução {#start}
   + [Introdução ao Adobe Campaign](start/get-started.md)
   + [Principais recursos](start/whats-new.md)
   + [Componentes e processos](start/ac-components.md)
   + [Conectar-se ao Campaign](start/connect.md)
   + Interface do Campaign {#ac-ui}
      + [Conheça a interface do Campaign](start/campaign-ui.md)
      + [Personalizar a interface do Campaign](start/customize-ui.md)
      + [Gerenciar pastas e visualizações](audiences/folders-and-views.md)
   + [Do Classic v7 para v8](start/v7-to-v8.md)
   + [Perguntas frequentes](start/campaign-faq.md)
+ Campaign Management {#campaigns}
   + [Introdução às campanhas](start/campaigns.md)
   + [Documentação da orquestração de campanha](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=pt-BR)
   + Enviar mensagens{#send}
      + [Introdução a mensagens](start/create-message.md)
      + Emails {#emails}
         + [Criar e validar emails](send/email.md)
         + [Enviar e monitorar emails](send/send.md)
      + [SMS](send/sms.md)
      + [Notificações por push](send/push.md)
      + [Mensagens LINE](send/line.md)
      + [Correspondência direta](send/direct-mail.md)
      + [Twitter](send/twitter.md)
      + [Mensagens transacionais](send/transactional.md)
      + Falhas, rejeições e quarentenas{#failures}
         + [Quarentenas](send/quarantines.md)
         + [Falhas de entrega](send/delivery-failures.md)
      + [Otimização da hora de envio](send/predictive.md)
      + [Gerenciar subscrições](start/subscriptions.md)
+ Gerenciamento de perfil e público-alvo {#audience}
   + [Introdução a perfis e públicos](audiences/gs-audiences.md)
   + [Trabalhar com públicos](start/audiences.md)
   + [Acessar perfis](audiences/view-profiles.md)
   + Adicionar perfis {#add-profiles}
      + [Criar perfis manualmente](audiences/create-profiles.md)
      + [Importar perfis de um arquivo](audiences/import-profiles.md)
      + [Trabalhar com perfis externos](audiences/external-profiles.md)
      + [Coletar dados de perfil em formulários web](audiences/collect-profiles.md)
      + [Trabalhar com target mappings](audiences/target-mappings.md)
   + Criar públicos {#create-audiences}
      + [Criar uma lista de contatos](audiences/create-audiences.md)
      + [Criar e gerenciar filtros](audiences/create-filters.md)
   + [Compartilhar públicos-alvo com soluções da Adobe](start/shared-audiences.md)
   + [Práticas recomendadas](audiences/audiences-best-practices.md)
+ Gestão de conteúdo {#content}
   + [Criar aplicativos e formulários Web](dev/webapps.md)
+ Gerenciamento de privacidade e segurança {#privacy}
   + [Gerenciar solicitações de privacidade](start/privacy.md)
   + [Diretrizes de segurança](config/security.md)
+ Gerenciamento de decisões {#offers}
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
   + [Métricas e relatórios](start/reporting.md)
+ Gerenciamento de dados {#data}
   + [Introdução a workflows](config/workflows.md)
   + [Importar dados](start/import.md)
   + [Documentação do workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)
+ Integrações {#connect}
   + [Conectar o Campaign com outras soluções](connect/integration.md)
   + [Campanha + Experience Platform](connect/ac-aep.md)
   + [Campanha + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Experience Cloud Triggers](connect/ac-triggers.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + Banco de dados externo](connect/fda.md)
   + Campaign + seu CRM {#ac-crm}
      + [Introdução aos conectores CRM](connect/crm.md)
      + [Trabalhar com o Campaign e o SFDC](connect/ac-sfdc.md)
      + [Trabalhar com o Campaign e o Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Sincronizar dados](connect/crm-data-sync.md)
+ Administração {#admin}
   + [Permissões](start/permissions.md)
   + [Painel de controle do Campaign](config/self-service.md)
+ Arquitetura e configuração {#config}
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
   + Implementação {#implement}
      + [Etapas de implementação](start/implement.md)
      + [Personalizar sua instância](dev/customize.md)
      + [Práticas recomendadas do Modelo de dados](dev/datamodel-best-practices.md)
   + Configuração {#configuration}
      + [Configurações de email](config/email-settings.md)
      + [Configurações de mensagens transacionais](config/transactional-msg-settings.md)
      + [Integrar os SDKs do Campaign ao seu aplicativo](config/push-config.md)
      + [Contas externas](config/external-accounts.md)
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
+ [Guia de automação de campanha](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=pt-BR)
