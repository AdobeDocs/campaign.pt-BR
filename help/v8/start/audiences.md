---
title: Trabalhar com públicos no Campaign
description: Trabalhar com públicos no Campaign
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 99cb937a475997aae714a67b1f9f91c6bae932f4
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 48%

---

# Trabalhar com públicos no Campaign{#gs-ac-audiences}

Perfis são contatos armazenados no banco de dados do Campaign.

No Adobe Campaign, **recipients** são os perfis padrão direcionados para envio de deliveries (emails, SMS etc.). Os dados do destinatário armazenados no banco de dados permitem filtrar o público-alvo que receberá qualquer entrega e adicionar dados de personalização ao conteúdo de entrega. Existem outros tipos de perfis no banco de dados. Esses perfis foram projetados para diferentes usos. Por exemplo, perfis iniciais são feitos para testar suas entregas antes que sejam enviadas ao público-alvo final.

Saiba como importar, atualizar e gerenciar perfis e públicos [nesta seção](../audiences/gs-audiences.md).

## Criar listas{#create-lists}

Uma lista é um conjunto estático de contatos que pode ser direcionado em ações de entrega ou atualizado durante uma importação ou outra ação de fluxo de trabalho. Por exemplo, uma população extraída do banco de dados por meio de uma consulta pode ser armazenada como uma lista.

Saiba como criar e gerenciar listas no [esta página](../audiences/create-audiences.md).

## Filtrar o banco de dados{#filter-the-database}

A configuração de filtro permite selecionar dados de uma lista **[!UICONTROL dynamically]**: quando os dados são modificados, os dados filtrados são atualizados. Você pode criar seus próprios filtros ou usar os filtros integrados para definir um público-alvo.

Saiba como criar e gerenciar filtros no [esta página](../audiences/create-filters.md).

## Criar um público-alvo em um fluxo de trabalho

O direcionamento pode ser criado por meio de uma combinação de queries em uma sequência gráfica em um workflow. Você pode criar públicos-alvo que serão direcionados de acordo com suas necessidades. Para exibir o editor de workflow, clique na guia **[!UICONTROL Targeting and workflows]** no painel de campanha.

Saiba como criar um público-alvo em um fluxo de trabalho de campanha no [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=pt-BR){target="_blank"}.


## Perfis ativos {#active-profiles}


Um perfil ativo é aquele com o qual o cliente tentou se comunicar nos últimos 12 meses por meio de qualquer canal.

De acordo com seu contrato, cada uma das instâncias do Campaign é provisionada com uma quantidade específica de perfis ativos que são contados para fins de faturamento. Consulte seu contrato mais recente para obter uma referência sobre o número de perfis ativos adquiridos. Saiba mais em [Descrição do produto Adobe Campaign](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Também é possível monitorar o número de perfis ativos em sua instância diretamente do Painel de controle do Campaign. Para obter mais informações, consulte a [documentação do Painel de controle](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=pt-BR){target="_blank"}.


As seguintes medidas de proteção e limitações se aplicam:

* Um perfil que foi direcionado em várias entregas é contado apenas uma vez.
* Perfis direcionados no contexto de Marketing social em X (Twitter) não são considerados como perfis ativos.
* A contagem se baseia na chave primária do destinatário. Como consequência, se um perfil estiver presente em duas tabelas de destinatários diferentes, ele poderá ser contado duas vezes como um perfil ativo.


## Privacidade e consentimento{#privacy-and-consent}

O Adobe Campaign é uma ferramenta poderosa para coletar e processar grandes volumes de dados, incluindo informações pessoais e dados confidenciais. O Adobe Campaign permite coletar dados, inclusive informações pessoais e confidenciais. Portanto, é essencial que você receba e monitore o consentimento de seus destinatários.

Saiba como gerenciar a privacidade e o consentimento no [Documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=pt-BR){target="_blank"}.

**Tópicos relacionados**

* [Projetar e executar um fluxo de trabalho específico da campanha](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html){target="_blank"}

* [Saiba como selecionar o público de uma campanha](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=pt-BR){target="_blank"}

* [Introdução a workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=pt-BR){target="_blank"}
