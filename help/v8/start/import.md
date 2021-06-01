---
product: Adobe Campaign
title: Introdução a perfis
description: Introdução a perfis
feature: Perfis
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 59%

---

# Importar dados para o Campaign {#ootb-profiles}

O Campaign ajuda a adicionar contatos ao banco de dados da nuvem. Você pode carregar um arquivo, agendar e automatizar várias atualizações de contato, coletar dados na Web ou inserir informações de perfil diretamente na tabela do recipient.

[!DNL :bulb:] Introdução a  [](audiences.md)
[!DNL :bulb:] públicosEntender o  [datamodel do Campaign](../dev/datamodel.md)

## Direcionar perfis em um fluxo de trabalho

As importações de perfil são configuradas em modelos dedicados executados por meio de workflows através da atividade **Importar**. Elas podem ser repetidas automaticamente de acordo com uma programação, por exemplo, para automatizar a troca de dados entre vários sistemas de informações. Saiba mais em [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html?lang=pt-BR).

![](assets/import-wf.png)

Saiba mais na documentação do Campaign Classic v7:

[!DNL :arrow_upper_right:] [Introdução a importações e exportações](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html?lang=pt-BR)

[!DNL :arrow_upper_right:] [Práticas recomendadas de importação e exportação](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html?lang=pt-BR)

[!DNL :arrow_upper_right:] [Configurar e executar uma importação](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=pt-BR)

## Executar importações unitárias

Crie e execute um trabalho de importação de dados genérico para carregar contatos no banco de dados na nuvem.

![](assets/new-import.png)

[!DNL :arrow_upper_right:] Saiba como executar tarefas de importação unitárias para alimentar seu banco de dados na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=pt-BR).

## Coletar perfis por meio de aplicativos da Web

Use o Campaign para criar formulários web e coletar e gerenciar informações de perfil de forma fácil e eficiente. Você pode compartilhar esses formulários no seu site, o que facilita que seus contatos forneçam suas informações. Suas informações são enviadas ao Campaign para criar seu perfil ou atualizar suas informações se já estiverem presentes no banco de dados.

![](assets/web-form-page.png)

[!DNL :arrow_upper_right:] Saiba como criar formulários web na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html).

**Tópicos relacionados**

* [Criar públicos](audiences.md)
* [Desduplicar perfis](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html?lang=pt-BR)
* [Enriquecer dados de perfil](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html?lang=pt-BR)
