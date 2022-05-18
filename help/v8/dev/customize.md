---
title: Personalizar sua instância
description: Saiba como personalizar sua instância
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 22%

---

# Personalizar sua instância{#gs-ac-custom}

Saiba como **Personalizar a instância do Campaign**

>[!CAUTION]
>
>A personalização do Adobe Campaign é reservada somente para usuários especialistas.

## Criar novos campos de dados e esquemas

A Adobe Campaign usa os Esquemas de dados para:

* Definir como os objetos de dados no aplicativo estão vinculados às tabelas de banco de dados subjacentes
* Definir links entre os diferentes objetos de dados no aplicativo Campaign
* Definir e descrever os campos individuais incluídos em cada objeto

Por exemplo, para adicionar um campo a uma tabela existente, como a tabela de recipients (nms:recipient), é necessário estender esse schema.

Dois modos de extensão de tabela estão disponíveis:

* Por meio da interface, usando o **Novo campo** assistente

   ![](../assets/do-not-localize/book.png) Saiba como adicionar rapidamente um novo campo no Campaign em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)

* Programaticamente, estendendo o esquema

   ![](../assets/do-not-localize/glass.png) Saiba como estender um esquema existente no [esta seção](../dev/extend-schema.md).


Você também pode criar novas tabelas no banco de dados do Campaign e estender o modelo de dados integrado.

Para adicionar um tipo de dados totalmente novo que não existe pronto para uso no Adobe Campaign (uma tabela de contratos, por exemplo), é possível criar um schema personalizado diretamente. Para obter mais informações, consulte [este exemplo](../dev/create-schema.md#example--creating-a-contract-table).

**Tópicos relacionados**

![](../assets/do-not-localize/book.png) Exemplo de edição de schema em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

![](../assets/do-not-localize/book.png) Caso de uso: vincular um campo a uma tabela de referência existente em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)


## Modificar os formulários de entrada

Os formulários de entrada da campanha podem ser adaptados para se adaptarem à sua implementação. Você pode adicionar ou remover campos de formulário modificando o conteúdo XML.

![](../assets/do-not-localize/glass.png) Saiba como modificar um formulário de entrada existente ou criar um novo formulário em [esta seção](../dev/forms.md).

## Personalizar painéis{#gs-custom-dashboards}

A interface do Adobe Campaign usa muitas aplicações web para acessar, gerenciar e interagir com recipients, deliveries, campanhas, estoques, etc. Elas são vistas na interface do formulário de painéis com apenas uma página.

Os aplicativos web prontos para uso são armazenadas no nó Administration > Configuration > Web applications.

![](../assets/do-not-localize/book.png) Saiba como criar uma página de visão geral no Campaign em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Personalizar listas e criar filtros {#gs-lists-and-filters}

### Acessar dados de painéis

As listas de campanha são fornecidas com filtros predefinidos para facilitar a navegação e a virtualização de dados.

![](../assets/do-not-localize/book.png) Saiba mais sobre as opções de filtragem em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Acessar dados do Explorer

Ao navegar na árvore do Adobe Campaign Explorer, os dados no banco de dados são exibidos em listas. Você pode filtrar essas listas, executar pesquisas, adicionar informações, filtrar e classificar dados.

![](../assets/do-not-localize/book.png) Saiba como configurar listas e salvar uma configuração de lista em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)


É possível aplicar filtros nessas listas para exibir apenas os dados necessários para o operador. Em seguida, as ações podem ser executadas nos dados filtrados. A configuração de filtro permite selecionar dados de uma lista dynamically. Se os dados forem modificados, os dados filtrados serão atualizados.

![](../assets/do-not-localize/book.png) Saiba como filtrar dados no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)
