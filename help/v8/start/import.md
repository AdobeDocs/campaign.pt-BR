---
title: Introdução a perfis
description: Introdução a perfis
feature: Profiles, Data Management
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: ht
source-wordcount: '213'
ht-degree: 100%

---

# Importar dados para o Campaign {#ootb-profiles}

O Campaign ajuda a adicionar contatos ao banco de dados da nuvem. Você pode carregar um arquivo, agendar e automatizar várias atualizações de contato, coletar dados na Web ou inserir informações de perfil diretamente na tabela do destinatário.

Introdução a [públicos-alvo](audiences.md)

Noções básicas do [modelo de dados](../dev/datamodel.md) do Campaign

## Direcionar perfis em um fluxo de trabalho

As importações de perfil são configuradas em modelos dedicados executados por meio de workflows através da atividade **Importar**. Elas podem ser repetidas automaticamente de acordo com uma programação, por exemplo, para automatizar a troca de dados entre vários sistemas de informações. Saiba mais [nesta seção](../../automation/workflow/recurring-import-workflow.md).

![](assets/import-wf.png)


## Executar importações unitárias

Crie e execute um trabalho de importação de dados genérico para carregar contatos no banco de dados na nuvem.

![](assets/new-import.png)

Saiba como executar processos de importação unitária para alimentar seu banco de dados na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=pt-BR){target="_blank"}.

## Coletar perfis por meio de aplicativos da Web

Use o Campaign para criar formulários web e coletar e gerenciar informações de perfil de forma fácil e eficiente. Você pode compartilhar esses formulários no seu site, o que torna mais fácil para seus contatos fornecer suas informações. Suas informações são enviadas ao Campaign para criar seu perfil ou atualizar suas informações se já estiverem presentes no banco de dados.

![](assets/web-form-page.png)

Saiba como criar formulários web na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=pt-BR){target="_blank"}.

**Tópicos relacionados**

* [Criar públicos-alvo](audiences.md)
* [Desduplicar perfis](../../automation/workflow/deduplication-merge.md)
* [Enriquecer dados de perfil](../../automation/workflow/enrich-data.md)
