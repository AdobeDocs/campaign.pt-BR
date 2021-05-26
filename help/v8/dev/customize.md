---
solution: Campaign v8
product: Adobe Campaign
title: Personalize sua instância
description: Saiba como personalizar sua instância
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 21%

---

# Personalize sua instância{#gs-ac-custom}

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

* Por meio da interface, usando o assistente **New field**

   [!DNL :arrow_upper_right:] Saiba como adicionar rapidamente um novo campo na documentação do Campaign no  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)

* Programaticamente, estendendo o esquema

   [!DNL :bulb:] Saiba como estender um schema existente  [nesta seção](../dev/extend-schema.md).


Você também pode criar novas tabelas no banco de dados do Campaign e estender o modelo de dados integrado.

Para adicionar um tipo de dados totalmente novo que não existe pronto para uso no Adobe Campaign (uma tabela de contratos, por exemplo), é possível criar um schema personalizado diretamente. Para obter mais informações, consulte [este exemplo](../dev/create-schema.md#example--creating-a-contract-table).

**Tópicos relacionados**

[!DNL :arrow_upper_right:] Exemplo de edição de schema na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

[!DNL :arrow_upper_right:] Caso de uso: vincular um campo a uma tabela de referência existente na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)


## Modificar os formulários de entrada

Os formulários de entrada da campanha podem ser adaptados para se adaptarem à sua implementação. Você pode adicionar ou remover campos de formulário modificando o conteúdo XML.

[!DNL :bulb:] Saiba como modificar um formulário de entrada existente ou criar um novo formulário  [nesta seção](../dev/forms.md).

## Personalizar painéis{#gs-custom-dashboards}

A interface do Adobe Campaign usa muitas aplicações web para acessar, gerenciar e interagir com recipients, deliveries, campanhas, estoques, etc. Elas são vistas na interface do formulário de painéis com apenas uma página.

Os aplicativos web prontos para uso são armazenadas no nó Administration > Configuration > Web applications.

[!DNL :arrow_upper_right:] Saiba como criar uma página de visão geral no Campaign na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Personalizar listas e criar filtros {#gs-lists-and-filters}

### Acessar dados de painéis

As listas de campanha são fornecidas com filtros predefinidos para facilitar a navegação e a virtualização de dados.

[!DNL :arrow_upper_right:] Saiba mais sobre as opções de filtragem na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Acessar dados do Explorer

Ao navegar na árvore do Adobe Campaign Explorer, os dados no banco de dados são exibidos em listas. Você pode filtrar essas listas, executar pesquisas, adicionar informações, filtrar e classificar dados.

[!DNL :arrow_upper_right:] Saiba como configurar listas e salvar uma configuração de lista na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)


É possível aplicar filtros nessas listas para exibir apenas os dados necessários para o operador. Em seguida, as ações podem ser executadas nos dados filtrados. A configuração de filtro permite selecionar dados de uma lista dynamically. Se os dados forem modificados, os dados filtrados serão atualizados.

[!DNL :arrow_upper_right:] Saiba como filtrar dados na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)
