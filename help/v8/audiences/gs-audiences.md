---
title: Introdução a perfis e públicos no Campaign
description: Saiba como criar e gerenciar perfis e públicos no Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
version: Campaign v8, Campaign Classic v7
source-git-commit: 050612f6d7ab20aed5880454eec9cfc6e5fc18c2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 28%

---

# Introdução a perfis e públicos-alvo{#gs-profiles-and-audiences}

Perfis são contatos armazenados no banco de dados do Campaign, como clientes, assinantes de um serviço ou clientes potenciais. Há vários mecanismos possíveis para obter perfis e criar esse banco de dados: coleta online via formulários web, importação manual ou automática de arquivos de texto, replicação com bancos de dados corporativos ou outros sistemas de informações. Com o Adobe Campaign, você pode incorporar o histórico de marketing, informações de compras, preferências, dados de CRM e quaisquer dados de PI relevantes em uma exibição consolidada para analisar e tomar decisões. Os perfis contêm todas as informações necessárias para direcionamento, qualificação e rastreamento de indivíduos.

Um perfil é um registro na tabela **nmsRecipient** ou uma tabela externa que armazena todos os atributos do perfil, como nome, sobrenome, endereço de email, uma ID de cookie, ID do cliente, identificador móvel ou outras informações relevantes para um canal específico. Outras tabelas vinculadas à tabela de recipients contêm dados relacionados ao perfil, por exemplo, a tabela de logs do delivery, que contém registros de todos os deliveries enviados aos recipients. Saiba mais sobre perfis e tabelas de destinatários internos em [esta seção](../dev/datamodel.md#ootb-profiles).

![](assets/recipients-in-explorer.png)

No Adobe Campaign, **recipients** são os perfis padrão direcionados para envio de entregas (emails, SMS etc.).

Os dados do destinatário armazenados no banco de dados permitem filtrar o público-alvo que receberá qualquer entrega e adicionar dados de personalização ao conteúdo de entrega. Existem outros tipos de perfis no banco de dados. Esses perfis foram projetados para diferentes usos. Por exemplo, perfis iniciais são feitos para testar suas entregas antes que sejam enviadas ao público-alvo final.

Para preencher o Adobe Campaign com dados de perfil, você pode:

* [importe arquivos de dados](../start/import.md) de uma fonte de dados externa, como um sistema CRM, ou um arquivo simples
* [criar formulários web](../dev/webapps.md) para permitir que os clientes insiram suas próprias informações e criem seus próprios perfis
* [mapear para um banco de dados externo](../connect/fda.md) onde os perfis estão armazenados
* insira os perfis manualmente no Console do cliente, conforme abaixo:

![](assets/create-profile.png)

Após a importação, você pode criar públicos-alvo para enviar suas mensagens. Saiba como criar públicos [nesta seção](create-audiences.md).