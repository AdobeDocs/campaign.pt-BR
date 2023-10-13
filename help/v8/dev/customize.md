---
title: Personalizar sua instância
description: Saiba como personalizar sua instância
feature: Configuration, Application Settings
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 22%

---

# Personalizar sua instância {#gs-ac-custom}

Saiba como **Personalizar a instância do Campaign**.

>[!CAUTION]
>
>A personalização do Adobe Campaign é reservada somente para usuários especialistas.

## Criar novos campos de dados e esquemas

A Adobe Campaign usa esquemas de dados para:

* Definir como os objetos de dados no aplicativo estão vinculados às tabelas de banco de dados subjacentes
* Definir links entre os diferentes objetos de dados no aplicativo Campaign
* Definir e descrever os campos individuais incluídos em cada objeto

Por exemplo, para adicionar um campo a uma tabela existente, como a tabela do recipient (nms:recipient), é necessário estender esse esquema.

Dois modos de extensão de tabela estão disponíveis:

* Por meio da interface, usando o **Novo campo** assistente

  Saiba como adicionar rapidamente um novo campo no Campaign no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html#configuring-campaign-classic){target="_blank"}

* Programaticamente, estendendo o schema. Saiba como estender um esquema existente no [nesta seção](../dev/extend-schema.md).

Você também pode criar novas tabelas no banco de dados do Campaign e estender o modelo de dados integrado.

Para adicionar um tipo de dados totalmente novo que não existe pronto para uso no Adobe Campaign (uma tabela de contratos, por exemplo), você pode criar um esquema personalizado diretamente. Para obter mais informações, consulte [este exemplo](../dev/create-schema.md#example--creating-a-contract-table).

**Tópicos relacionados**

![](../assets/do-not-localize/book.png) Exemplo de edição de esquema em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#configuring-campaign-classic){target="_blank"}

![](../assets/do-not-localize/book.png) Caso de uso: vincular um campo a uma tabela de referência existente no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#uc-link){target="_blank"}


## Modificar os formulários de entrada

Os formulários de entrada do Campaign podem ser adaptados para se adaptarem à sua implementação. É possível adicionar ou remover campos de formulário modificando o conteúdo XML.

Saiba como modificar um formulário de entrada existente ou criar um novo formulário no [nesta seção](../dev/forms.md).

## Personalizar painéis{#gs-custom-dashboards}

A interface do Adobe Campaign usa muitas aplicações web para acessar, gerenciar e interagir com recipients, deliveries, campanhas, estoques, etc. Elas são vistas na interface do formulário de painéis com apenas uma página.

Os aplicativos web integrados são armazenados no **Administração > Configuração > Aplicações web** pasta do Explorer.

Saiba como criar uma página de visão geral no Campaign em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html#creating-a-single-page-web-application){target="_blank"}


## Personalizar listas e criar filtros {#gs-lists-and-filters}

As listas de campanha vêm com filtros predefinidos para facilitar a navegação e a visualização de dados.

Ao navegar na árvore do Adobe Campaign Explorer, os dados contidos no banco de dados são exibidos em listas. Você pode filtrar essas listas, executar pesquisas, adicionar informações, filtrar e classificar dados.

Saiba como configurar listas e salvar uma configuração de lista no [esta página](../start/campaign-ui.md).

Aplique filtros nessas listas para exibir apenas os dados necessários ao operador. Em seguida, as ações podem ser executadas nos dados filtrados. A configuração de filtro permite selecionar dados de uma lista dynamically. Se os dados forem modificados, os dados filtrados serão atualizados.

Saiba mais sobre as opções de filtragem em [esta página](../audiences/create-filters.md).
