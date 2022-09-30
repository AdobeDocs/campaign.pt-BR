---
title: Trabalhar com públicos no Campaign
description: Trabalhar com públicos no Campaign
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 29%

---

# Trabalhar com públicos no Campaign{#gs-ac-audiences}

Os perfis são contatos armazenados no banco de dados do Campaign.

No Adobe Campaign, **recipients** são os perfis padrão direcionados para envio de deliveries (emails, SMS, etc.). Os dados do recipient armazenados no banco de dados permitem filtrar o target que receberá qualquer delivery e adicionar dados de personalização ao conteúdo de delivery. Existem outros tipos de perfis no banco de dados. Esses perfis foram projetados para diferentes usos. Por exemplo, perfis iniciais são feitos para testar seus deliveries antes que sejam enviados ao público-alvo final.

Saiba como importar, atualizar e gerenciar perfis e públicos [nesta seção](../audiences/gs-audiences.md).

## Criar listas{#create-lists}

Uma lista é um conjunto estático de contatos que pode ser direcionado em ações de delivery ou atualizado durante uma importação ou outra ação de workflow. Por exemplo, uma população extraída do banco de dados por um query pode ser armazenada como uma lista.

![](../assets/do-not-localize/glass.png) Saiba como criar e gerenciar listas no [esta página](../audiences/create-audiences.md).

## Filtrar o banco de dados{#filter-the-database}

A configuração de filtro permite selecionar dados de uma lista **[!UICONTROL dynamically]**: quando os dados são modificados, os dados filtrados são atualizados. Você pode criar seus próprios filtros ou usar os filtros incorporados para definir um público-alvo.

![](../assets/do-not-localize/glass.png) Saiba como criar e gerenciar filtros no [esta página](../audiences/create-filters.md).

## Criar um público-alvo em um fluxo de trabalho

O direcionamento pode ser criado por meio de uma combinação de consultas em uma sequência gráfica em um workflow. Você pode criar públicos-alvo que serão direcionados de acordo com suas necessidades. Para exibir o editor de workflow, clique na guia **[!UICONTROL Targeting and workflows]** no painel de campanha.

Saiba como criar um público-alvo em um fluxo de trabalho da campanha no [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=pt-BR)


## Perfis ativos{#active-profiles}

De acordo com seu contrato, cada uma das instâncias do Campaign é provisionada com um número específico de perfis ativos que são contados para fins de faturamento. Consulte seu contrato mais recente para obter uma referência sobre o número de perfis ativos adquiridos.

**Perfil** um registro de informações (por exemplo: um registro no [Tabela de recipients](../dev/datamodel.md) ou uma tabela externa contendo uma ID de cookie, ID do cliente, identificador móvel ou outras informações relevantes para um canal específico) representando um cliente final, um prospecto ou um cliente potencial. Os perfis são considerados ativos se tiverem sido direcionados ou comunicados nos últimos 12 meses por meio de qualquer canal.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

## Privacidade e consentimento{#privacy-and-consent}

O Adobe Campaign é uma ferramenta poderosa para coletar e processar um grande volume de dados, incluindo informações pessoais e dados confidenciais. O Adobe Campaign permite coletar dados, inclusive informações pessoais e confidenciais. Portanto, é essencial que você receba e monitore o consentimento de seus recipients.

![](../assets/do-not-localize/book.png) Saiba como gerenciar a privacidade e o consentimento no [Documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=pt-BR){target=&quot;_blank&quot;}.

**Tópicos relacionados**

* [Projete e execute um workflow específico da campanha](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html)

* [Saiba como selecionar o público de uma campanha](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)

* [Introdução a workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)
