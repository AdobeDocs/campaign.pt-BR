---
audience: end-user
user-guide-title: Campaign v8
title: Documentação do Adobe Campaign v8
description: Documentação do Campaign v8
breadcrumb-title: Visão geral da campanha
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 97%

---


# Documentação do Adobe Campaign v8 {#campaign-v8}

+ [Documentação do Campaign v8](campaign-home.md)
+ Versões e atualizações mais recentes {#releases}
   + [Notas de versão anteriores](start/e-release-notes.md)
   + [Notas de versão](start/release-notes.md)
   + Notas de versão anteriores {#previous-rn}
      + [2022](start/release-notes-2022.md)
      + [2021](start/release-notes-2021.md)
   + [Medidas de proteção](start/ac-guardrails.md)
   + [Problemas conhecidos](start/known-issues.md)
   + [Matriz de compatibilidade](start/compatibility-matrix.md)
+ Introdução {#new}
   + [Introdução ao Adobe Campaign](start/get-started.md)
   + [Principais recursos](start/whats-new.md)
   + [Componentes e processos](start/ac-components.md)
   + [Conectar-se ao Campaign](start/connect.md)
   + [Interface do Campaign](start/campaign-ui.md)
   + [Do Classic v7 para o v8](start/v7-to-v8.md)
   + [Perguntas frequentes](start/campaign-faq.md)
+ Gerenciamento de campanhas {#campaigns}
   + [Introdução às campanhas](start/campaigns.md)
   + [Orquestração de campanha >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=pt-BR)
   + Enviar mensagens{#send}
      + [Introdução a mensagens](start/create-message.md)
      + [Trabalho com modelos de entrega](send/create-templates.md)
      + Emails {#emails}
         + [Criar e validar emails](send/email.md)
         + [Link para a mirror page](send/mirror-page.md)
         + [Enviar e monitorar emails](send/send.md)
      + [SMS](send/sms.md)
      + Notificações por push {#push}
         + [Criar e enviar notificações por push](send/push.md)
         + [Configurar canal de notificação por push](send/push-settings.md)
         + [Configurar as notificações por push com a Coleção de dados](send/push-data-collection.md)
      + [Mensagens LINE](send/line.md)
      + [Correspondência direta](send/direct-mail.md)
      + [Twitter](send/twitter.md)
      + Mensagens transacionais {#real-time}
         + [Introdução a mensagens transacionais](send/transactional.md)
         + [Criação e publicação do seu modelo](send/transactional-template.md)
         + Gerenciamento de eventos {#event}
         + [Coletar e processar eventos](send/event-processing.md)
         + [Entender a descrição do evento](send/event-description.md)
         + [Enviar e monitorar mensagens](send/delivery-execution.md)
      + Falhas, rejeições e quarentenas{#failures}
         + [Quarentenas](send/quarantines.md)
         + [Falhas de entrega](send/delivery-failures.md)
      + [Otimização da hora de envio](send/predictive.md)
      + [Gerenciar subscrições](start/subscriptions.md)
      + Personalizar conteúdo {#personalize}
         + [Introdução à personalização](send/personalize.md)
         + [Dados de personalização](send/personalization-data.md)
         + [Adicionar campos de personalização](send/personalization-fields.md)
         + [Usar blocos de personalização](send/personalization-blocks.md)
         + [Criar condições](send/conditions.md)
      + Validar a entrega {#validate}
         + [Visualização e provas](send/preview-and-proof.md)
         + [Análise de entrega](send/delivery-analysis.md)
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
      + [Criar perfis de teste](audiences/test-profiles.md)
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
   + Trabalho com relatórios{#reports}
      + [Introdução aos relatórios](reporting/gs-reporting.md)
      + Criar cubos{#cubes}
         + [Introdução aos cubos](reporting/gs-cubes.md)
         + [Criar um cubo](reporting/cube-indicators.md)
         + [Usar cubos para criar relatórios](reporting/cube-tables.md)
         + [Personalizar os seus cubos](reporting/customize-cubes.md)
      + Relatórios incorporados{#ac-reports}
         + [Lista de relatórios incorporados](reporting/built-in-reports.md)
         + [Relatórios globais](reporting/global-reports.md)
         + [Relatórios de entrega](reporting/delivery-reports.md)
         + [Cálculo de métricas incorporadas](reporting/metrics-calculation.md)
      + [Relatórios personalizados](reporting/custom-reports.md)
+ Gerenciamento de dados {#data}
   + [Introdução a workflows](config/workflows.md)
   + [Importar dados](start/import.md)
   + [Documentação do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=pt-BR)
+ Integrações {#connect}
   + [Conectar o Campaign a outras soluções](connect/integration.md)
   + [Campaign + Experience Platform](connect/ac-aep.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
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
   + Usuários e permissões {#permissions}
      + [Introdução a permissões](start/gs-permissions.md)
      + [Gerenciar permissões do usuário](start/manage-permissions.md)
      + [Adicionar permissões em pastas](start/folder-permissions.md)
   + [Painel de controle](config/self-service.md)
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
   + Definições e configuração {#configuration}
      + [Configurações da interface](config/ui-settings.md)
      + [Gerenciar pastas e visualizações](audiences/folders-and-views.md)
      + [Configurações de email](config/email-settings.md)
      + [Configurações de mensagens transacionais](config/transactional-msg-settings.md)
      + [Integrar os SDKs do Campaign ao seu aplicativo - PÁGINA OBSOLETA](config/push-config.md)
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
+ [Painel de controle do Campaign >](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR)
+ [Guia de automação de campanha >](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=pt-BR)
