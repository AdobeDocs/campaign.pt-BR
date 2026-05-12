---
title: Pastas e visualizações
description: Saiba como gerenciar pastas e visualizações no explorador do Campaign
feature: Audiences, Profiles, Application Settings
role: User
level: Beginner, Intermediate
exl-id: 762dcacc-4aeb-4990-af01-7f793bd69170
version: Campaign v8, Campaign Classic v7
TQID: https://experienceleague.adobe.com/JeoAcZo-o2JlrbFAHdwYfOS4Ij-HjZW3x9171G9g5fc
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2: id: b5852c32-876b-41ae-92a7-9f588865ae52id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 695
ht-degree: 5%

---

# Gerenciar pastas e visualizações {#folders-and-views}

As pastas do Campaign são nós na árvore do explorador. Com base no tipo, eles contêm determinados tipos de dados.

Uma exibição é uma pasta específica que não contém dados, mas exibe dados fisicamente armazenados em outras pastas do mesmo tipo. Por exemplo, se você transformar uma pasta de delivery em uma visualização, essa pasta mostrará todos os deliveries. Esses dados podem ser filtrados.


>[!NOTE]
>
>Para distinguir visualizações de pastas padrão, seu nome é exibido em azul claro em vez de preto.

Observe que é possível atribuir permissões a pastas para restringir o acesso a determinados dados. [Saiba mais](#restrict-access-to-a-folder)

## Práticas recomendadas para trabalhar com pastas{#best-practices-folders}

* **Usar pastas integradas** para facilitar o uso, a manutenção e a solução de problemas do aplicativo para todas as pessoas envolvidas no projeto. Evite criar estruturas de pasta personalizadas para destinatários, listas, entregas, etc., mas use as pastas padrão, como **Administração**, **Perfis e Destinos** e **Gerenciamento de campanha**.

* **Criar subpastas**, por exemplo, salve seus fluxos de trabalho técnicos na pasta interna: **[!UICONTROL Administration > Production > Technical Workflows]** e crie subpastas por tipo de fluxo de trabalho.

* **Defina e aplique uma convenção de nomenclatura**. Por exemplo, você pode nomear os fluxos de trabalho em ordem alfabética, para que eles apareçam classificados na ordem de execução, como:

  A1 - importar recipients, começa em 10:00;
A2 - importar tíquetes, começa às 11:00.

## Criar uma pasta{#create-a-folder}

Para criar uma pasta, clique com o botão direito do mouse em uma pasta existente e use o menu contextual.

Para criar o mesmo tipo de pasta que a pasta selecionada, escolha a primeira opção no menu contextual. Por exemplo, em uma pasta Recipients, selecione **[!UICONTROL Create a new 'Recipients' folder]**.

![](assets/create-recipient-folder.png)

Você pode arrastar e soltar a nova pasta para organizar a árvore do explorador do Campaign conforme necessário.

Para criar outro tipo de pasta, clique com o botão direito em uma pasta existente e selecione **[!UICONTROL Add new folder]**. É possível criar todos os tipos de pastas, dependendo dos dados a serem armazenados.

![](assets/add-new-folder.png)

>[!CAUTION]
>
>Essas alterações se aplicam a todos os usuários do Campaign.

## Transformar uma pasta em um modo de exibição{#turn-a-folder-to-a-view}

Uma exibição é uma pasta específica que não contém dados, mas exibe dados fisicamente armazenados em outras pastas do mesmo tipo.

Você pode transformar qualquer pasta em uma visualização, mas a pasta deve estar vazia. Todos os dados armazenados na pasta são excluídos quando você transforma a pasta em uma visualização.

>[!IMPORTANT]
>
>As pastas prontas para uso não devem ser transformadas em uma visualização.


>[!CAUTION]
>
>Uma visualização exibe dados e fornece acesso a eles, mesmo se os dados não estiverem fisicamente armazenados na pasta de visualização. Para ter acesso ao conteúdo, o operador deve ter as permissões apropriadas nas pastas de origem, pelo menos, acesso de Leitura.
>
>Para conceder acesso a uma visualização sem conceder acesso à pasta de origem, não conceda acesso de leitura ao nó pai da pasta de origem.

No exemplo abaixo, criaremos uma nova pasta para exibir apenas deliveries dos EUA, com base no nome interno.

1. Crie uma pasta **[!UICONTROL Deliveries]** e nomeie-a como **Entregas nos EUA**.
1. Clique com o botão direito do mouse nessa pasta e selecione **[!UICONTROL Properties...]**.
1. Na guia **[!UICONTROL Restriction]**, selecione **[!UICONTROL This folder is a view]**. Todas as entregas no banco de dados serão exibidas.

   ![](assets/this-folder-is-a-view.png)

1. Defina os critérios de filtro no editor de query na seção central da janela: somente os deliveries correspondentes ao filtro são exibidos na pasta.

   ![](assets/filter-view.png)

   >[!NOTE]
   >
   >Saiba como criar consultas em [esta página](create-filters.md#advanced-filters)


>[!CAUTION]
>
>Ao gerenciar eventos de [mensagens transacionais](../send/transactional.md), as pastas **[!UICONTROL Real time events]** ou **[!UICONTROL Batch events]** não devem ser definidas como visualizações nas instâncias de execução, pois isso pode causar problemas de permissão.

## Organizar suas pastas{#organize-your-folders}

Por padrão, uma nova pasta é adicionada na parte superior da hierarquia.

Procure a guia **Subpastas** das propriedades de uma pasta para organizar suas subpastas.

Você pode mover as pastas com as setas à direita ou selecionar a opção **[!UICONTROL Sort the sub-folders in alphabetical order]** para classificá-las automaticamente.

![](assets/sort-folders.png)


## Filtrar dados em uma pasta{#filter-data-in-a-folder}

Para filtrar os dados armazenados em uma pasta, acesse as propriedades da pasta e selecione a guia Restriction.

Por exemplo, a pasta abaixo conterá apenas contatos com um endereço de email e cuja origem não esteja sinalizada como &#39;Externa&#39; ou esteja vazia.

![](assets/add-a-filter-to-a-folder.png)


## Restringir o acesso a uma pasta{#restrict-access-to-a-folder}

Use permissões em pastas para organizar e controlar o acesso aos dados do Campaign. Saiba mais sobre permissões em pastas em [esta seção](../start/folder-permissions.md).
