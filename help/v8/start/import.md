---
title: Introdução a perfis
description: Introdução a perfis
feature: Profiles
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 780a29dab99ad2bda554134ca95c435b9e76b494
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 100%

---

# Importar dados para o Campaign {#ootb-profiles}

O Campaign ajuda a adicionar contatos ao banco de dados da nuvem. Você pode carregar um arquivo, agendar e automatizar várias atualizações de contato, coletar dados na Web ou inserir informações de perfil diretamente na tabela do recipient.

![](../assets/do-not-localize/glass.png) Introdução aos [públicos](audiences.md)

![](../assets/do-not-localize/glass.png) Entenda o [modelo de dados](../dev/datamodel.md) do Campaign

## Direcionar perfis em um fluxo de trabalho

As importações de perfil são configuradas em modelos dedicados executados por meio de workflows através da atividade **Importar**. Elas podem ser repetidas automaticamente de acordo com uma programação, por exemplo, para automatizar a troca de dados entre vários sistemas de informações. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html?lang=pt-BR){target=&quot;_blank&quot;}.

![](assets/import-wf.png)

Saiba mais na documentação do Campaign Classic v7:

* [Introdução a importações e exportações](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html?lang=pt-BR){target=&quot;_blank&quot;}

* [Práticas recomendadas de importação e exportação](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html?lang=pt-BR){target=&quot;_blank&quot;}

* [Configurar e executar uma importação](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=pt-BR){target=&quot;_blank&quot;}

## Executar importações unitárias

Crie e execute um trabalho de importação de dados genérico para carregar contatos no banco de dados na nuvem.

![](assets/new-import.png)

![](../assets/do-not-localize/book.png) Saiba como executar tarefas de importação unitárias para alimentar seu banco de dados na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=pt-BR){target=&quot;_blank&quot;}.

## Coletar perfis por meio de aplicativos da Web

Use o Campaign para criar formulários web e coletar e gerenciar informações de perfil de forma fácil e eficiente. Você pode compartilhar esses formulários no seu site, o que torna mais fácil para seus contatos fornecer suas informações. Suas informações são enviadas ao Campaign para criar seu perfil ou atualizar suas informações se já estiverem presentes no banco de dados.

![](assets/web-form-page.png)

![](../assets/do-not-localize/book.png) Saiba como criar formulários da Web na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=pt-BR){target=&quot;_blank&quot;}.

**Tópicos relacionados**

* [Criar públicos](audiences.md)
* [Desduplicar perfis](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html?lang=pt-BR){target=&quot;_blank&quot;}
* [Enriquecer dados de perfil](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html?lang=pt-BR){target=&quot;_blank&quot;}
