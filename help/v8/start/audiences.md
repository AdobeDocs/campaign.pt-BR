---
solution: Campaign
product: Adobe Campaign
title: Introdução a públicos
description: Introdução a públicos
feature: Públicos
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
translation-type: tm+mt
source-git-commit: eb47761f20c02474bb971ab992cf1ea5098bb350
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 40%

---

# Introdução a públicos-alvo{#gs-ac-audiences}

Os perfis podem ser agrupados em listas ou coletados consultando o banco de dados.

## Trabalhar com perfis{#gs-ac-profiles}

Os perfis são centralizados no banco de dados da nuvem. Há vários mecanismos possíveis para obter perfis e criar esse banco de dados: coleta online via formulários Web, importação manual ou automática de arquivos de texto, replicação com bancos de dados corporativos ou outros sistemas de informações. Com o Adobe Campaign, você pode incorporar o histórico de marketing, informações de compras, preferências, dados de CRM e quaisquer dados de PI relevantes em uma exibição consolidada para analisar e tomar decisões.

&quot;**Perfil**&quot; significa um registro de informações que representa um cliente, um prospecto, um assinante de boletim informativo, etc.
Um registro na tabela **nmsRecipient** ou em uma tabela externa contém uma ID de cookie, ID do cliente, identificador móvel ou outras informações relevantes para um canal específico. Saiba mais sobre perfis integrados e tabelas de destinatários em [esta seção](../dev/datamodel.md#ootb-profiles).

No Adobe Campaign, os recipients são os perfis padrão direcionados para envio de deliveries (emails, SMS etc.). Os dados do recipient armazenados no banco de dados permitem filtrar o target que receberá qualquer delivery e adicionar dados de personalização ao conteúdo de delivery. Existem outros tipos de perfis no banco de dados. Esses perfis foram projetados para diferentes usos. Por exemplo, perfis iniciais são feitos para testar seus deliveries antes que sejam enviados ao público-alvo final.

:seta_forward: [Entender o que é um perfil no vídeo](https://video.tv.adobe.com/v/35611?quality=12)

:seta_upper_right: Saiba como gerenciar perfis em [este guia](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html{{){:target=&quot;_blank&quot;}.

## Privacidade e consentimento

O Adobe Campaign é uma ferramenta poderosa para coletar e processar quantidades extremamente grandes de dados, incluindo informações pessoais e dados confidenciais. O Adobe Campaign permite coletar dados, inclusive informações pessoais e confidenciais. Portanto, é essencial que você receba e monitore o consentimento de seus recipients.

:seta_upper_right: Saiba como gerenciar privacidade e consentimento em [este guia](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html).


## Criar listas

Uma lista é um conjunto estático de perfis que pode ser direcionada em ações de delivery ou atualizada durante as operações de importação ou durante a execução de workflows. Por exemplo, uma população extraída do banco de dados por uma consulta pode fornecer uma lista.

:seta_upper_right: Saiba como criar e gerenciar listas em [esta seção](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html).

## Consultar o banco de dados

Use a atividade **Query** em um workflow para consultar seu banco de dados, segmentar dados e criar públicos complexos.

:seta_upper_right: Saiba mais sobre consultas do Campaign em [este guia](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html).

:seta_upper_right: Todas as atividades de direcionamento estão listadas em [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)

## Criar um público-alvo em um fluxo de trabalho

O direcionamento pode ser criado por meio de uma combinação de consultas em uma sequência gráfica em um workflow. Você pode criar públicos-alvo que serão direcionados de acordo com suas necessidades. Para exibir o editor de workflow, clique na guia **[!UICONTROL Targeting and workflows]** no painel de campanha.

:seta_upper_right: Saiba como criar um público em um workflow de campanha em [this page]https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)


## Perfis ativos{#active-profiles}

De acordo com seu contrato, cada uma das instâncias do Campaign é provisionada com uma quantidade específica de perfis ativos que são contados para fins de faturamento. Consulte seu contrato mais recente para obter uma referência sobre o número de perfis ativos adquiridos.

&quot;Perfil&quot; significa um registro de informações (por exemplo: um registro na tabela [Recipient](../dev/datamodel.md) ou uma tabela externa contendo uma ID de cookie, ID do cliente, identificador móvel ou outras informações relevantes para um canal específico) representando um cliente final, um prospecto ou um cliente potencial. Os perfis são considerados ativos se tiverem sido direcionados ou comunicados nos últimos 12 meses por meio de qualquer canal.

Você pode monitorar o número de perfis ativos usados em suas instâncias diretamente do Painel de controle do Campaign.

:seta_upper_right: Para obter mais informações, consulte a [documentação do Painel de controle](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=pt-BR).


**Tópicos relacionados**

:seta_upper_right: [Projete e execute um workflow específico da campanha](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:seta_upper_right: [Saiba como selecionar o público de uma campanha](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

:seta_upper_right: [Introdução a workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
