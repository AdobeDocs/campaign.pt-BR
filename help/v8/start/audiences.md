---
product: Adobe Campaign
title: Introdução a públicos
description: Introdução a públicos
feature: Públicos
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 34%

---

# Introdução a públicos{#gs-ac-audiences}

## Trabalhar com perfis{#gs-ac-profiles}

Perfis são contatos armazenados no banco de dados do Campaign, incluindo clientes, assinantes e prospetos. Há vários mecanismos possíveis para obter perfis e criar esse banco de dados: coleta online via formulários Web, importação manual ou automática de arquivos de texto, replicação com bancos de dados corporativos ou outros sistemas de informações. Com o Adobe Campaign, você pode incorporar o histórico de marketing, informações de compras, preferências, dados de CRM e quaisquer dados de PI relevantes em uma exibição consolidada para analisar e tomar decisões. Os perfis contêm todas as informações necessárias para direcionamento, qualificação e rastreamento de indivíduos.

Um perfil é um registro na tabela **nmsRecipient** ou uma tabela externa que armazena todos os atributos do perfil, como nome, sobrenome, endereço de email, uma ID de cookie, ID do cliente, identificador móvel ou outras informações relevantes para um canal específico. Outras tabelas vinculadas à tabela de recipients contêm dados relacionados ao perfil, por exemplo, a tabela de logs do delivery que contém registros de todos os deliveries enviados aos recipients. Saiba mais sobre perfis integrados e tabelas de destinatários em [esta seção](../dev/datamodel.md#ootb-profiles).

No Adobe Campaign, **recipients** são os perfis padrão direcionados para enviar deliveries (emails, SMS, etc.). Os dados do recipient armazenados no banco de dados permitem filtrar o target que receberá qualquer delivery e adicionar dados de personalização ao conteúdo de delivery. Existem outros tipos de perfis no banco de dados. Esses perfis foram projetados para diferentes usos. Por exemplo, perfis iniciais são feitos para testar seus deliveries antes que sejam enviados ao público-alvo final.

Os perfis podem ser agrupados em listas ou coletados consultando o banco de dados.


Para preencher o Campaign com dados de perfil, é possível:

* [importar ](import.md) arquivos de dados de uma fonte externa de dados, como um sistema CRM
* [criar ](../dev/webapps.md) formulários da Web para permitir que os clientes insiram suas próprias informações e criem seu próprio perfil
* [mapear para um ](../connect/fda.md) banco de dados externo, onde os perfis são armazenados
* insira perfis manualmente usando o console do cliente, conforme abaixo:

![](assets/create-profile.png)


↗️ Saiba como gerenciar perfis na [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html){target=&quot;_blank&quot;}.


## Privacidade e consentimento

O Adobe Campaign é uma ferramenta poderosa para coletar e processar um grande volume de dados, incluindo informações pessoais e dados confidenciais. O Adobe Campaign permite coletar dados, inclusive informações pessoais e confidenciais. Portanto, é essencial que você receba e monitore o consentimento de seus recipients.

↗️ Saiba como gerenciar privacidade e consentimento na [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target=&quot;_blank&quot;}.

## Criar listas

Uma lista é um conjunto estático de perfis que pode ser direcionada em ações de delivery ou atualizada durante as operações de importação ou durante a execução de workflows. Por exemplo, uma população extraída do banco de dados por uma consulta pode fornecer uma lista.

↗️ Saiba como criar e gerenciar listas na [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html){target=&quot;_blank&quot;}.

## Consultar o banco de dados

Use a atividade **Query** em um workflow para consultar seu banco de dados, segmentar dados e criar públicos complexos.

↗️ Saiba mais sobre consultas do Campaign na [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html){target=&quot;_blank&quot;}.

↗️ Todas as atividades de direcionamento são listadas na [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target=&quot;_blank&quot;}.

## Criar um público-alvo em um fluxo de trabalho

O direcionamento pode ser criado por meio de uma combinação de consultas em uma sequência gráfica em um workflow. Você pode criar públicos-alvo que serão direcionados de acordo com suas necessidades. Para exibir o editor de workflow, clique na guia **[!UICONTROL Targeting and workflows]** no painel de campanha.

↗️ Saiba como criar um público-alvo em um fluxo de trabalho da campanha na [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}.


## Perfis ativos{#active-profiles}

De acordo com seu contrato, cada uma das instâncias do Campaign é provisionada com uma quantidade específica de perfis ativos que são contados para fins de faturamento. Consulte seu contrato mais recente para obter uma referência sobre o número de perfis ativos adquiridos.

**** Perfil significa um registro de informações (por exemplo: um registro na tabela  [Recipient ](../dev/datamodel.md) ou uma tabela externa contendo uma ID de cookie, ID do cliente, identificador móvel ou outras informações relevantes para um canal específico) representando um cliente final, um prospecto ou um cliente potencial. Os perfis são considerados ativos se tiverem sido direcionados ou comunicados nos últimos 12 meses por meio de qualquer canal.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

↗️ For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**Tópicos relacionados** na documentação do Campaign Classic v7:

↗️ [Projete e execute um workflow específico da campanha](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html){target=&quot;_blank&quot;}

↗️ [Saiba como selecionar o público de uma campanha](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html){target=&quot;_blank&quot;}

↗️ [Introdução a workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html){target=&quot;_blank&quot;}
