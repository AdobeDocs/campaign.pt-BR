---
title: Pastas e visualizações
description: Saiba como gerenciar pastas e visualizações no Campaign Explorer
feature: Audiences, Profiles, Application Settings
role: Data Engineer
level: Beginner
exl-id: 762dcacc-4aeb-4990-af01-7f793bd69170
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 7%

---

# Gerenciar pastas e visualizações {#folders-and-views}

As pastas de campanha são nós na árvore do explorador. Com base em seu tipo, eles contêm determinados tipos de dados.

Uma exibição é uma pasta específica que não contém dados, mas exibe dados fisicamente armazenados em outras pastas do mesmo tipo. Por exemplo, se você transformar uma pasta de delivery em uma visualização, essa pasta mostrará todos os deliveries. Esses dados podem ser filtrados.


>[!NOTE]
>Para distinguir visualizações de pastas padrão, seu nome é exibido em azul claro em vez de preto.

Observe que é possível atribuir permissões a pastas para restringir o acesso a determinados dados. [Saiba mais](#restrict-access-to-a-folder)

## Práticas recomendadas para trabalhar com pastas

* **Usar pastas incorporadas** para facilitar o uso, a manutenção e a solução de problemas do aplicativo para todas as pessoas envolvidas no projeto. Evite criar estruturas de pastas personalizadas para recipients, listas, deliveries etc., mas use as pastas padrão, como **Administração**, **Perfis e metas**, **Gerenciamento de campanhas**.

* **Criar subpastas**, por exemplo, salve os workflows técnicos na pasta interna : **[!UICONTROL Administration > Production > Technical Workflows]** e criar subpastas por tipo de fluxo de trabalho.

* **Definir e aplicar uma convenção de nomenclatura**, por exemplo, é possível nomear os workflows em ordem alfabética, para que eles apareçam classificados na ordem de execução, como:

   A1 - destinatários da importação, começa às 10:00; A2 - importar tíquetes, começa às 11:00.

## Criar uma pasta{#create-a-folder}

Para criar uma pasta, clique com o botão direito do mouse em uma pasta existente e use o menu contextual.

Para criar o mesmo tipo de pasta que a selecionada, escolha a primeira opção no menu contextual. Por exemplo, em uma pasta Recipients , selecione **[!UICONTROL Create a new 'Recipients' folder]**.

![](assets/create-recipient-folder.png)

Você pode arrastar e soltar a nova pasta para organizar a árvore do explorador do Campaign conforme necessário.

Para criar outro tipo de pasta, clique com o botão direito do mouse em uma pasta existente e selecione **[!UICONTROL Add new folder]**. É possível criar todos os tipos de pastas, dependendo dos dados a serem armazenados.

![](assets/add-new-folder.png)

>[!CAUTION]
>Essas alterações se aplicam a todos os usuários do Campaign.

## Transformar uma pasta numa vista{#turn-a-folder-to-a-view}

Uma exibição é uma pasta específica que não contém dados, mas exibe dados fisicamente armazenados em outras pastas do mesmo tipo.

Você pode transformar qualquer pasta em uma visualização, mas a pasta deve estar vazia. Todos os dados armazenados na pasta são excluídos à medida que você a transforma em uma visualização.

>[!CAUTION]
>
>Uma exibição exibe dados e fornece acesso a eles, mesmo que os dados não sejam armazenados fisicamente na pasta de exibição. Para ter acesso ao conteúdo, o operador deve ter as permissões apropriadas nas pastas de origem, pelo menos acesso de Leitura.
>
>Para conceder acesso a uma visualização sem conceder acesso à pasta de origem, não conceda acesso de leitura ao nó pai da pasta de origem.

No exemplo abaixo, criaremos uma nova pasta para exibir somente deliveries dos EUA, com base em seu nome interno.

1. Crie um **[!UICONTROL Deliveries]** pasta e nomeie-a **Deliveries dos EUA**.
1. Clique com o botão direito do mouse nessa pasta e selecione **[!UICONTROL Properties...]**.
1. Na guia **[!UICONTROL Restriction]**, selecione **[!UICONTROL This folder is a view]**. Todos os deliveries no banco de dados serão exibidos.

   ![](assets/this-folder-is-a-view.png)

1. Defina os critérios de filtro no editor de query na seção central da janela: somente os deliveries correspondentes ao filtro são exibidos na pasta .

   ![](assets/filter-view.png)

   >[!NOTE]
   >
   >Saiba como criar consultas no [esta página](create-filters.md#advanced-filters)


>[!CAUTION]
>
>Ao gerenciar [mensagens transacionais](../send/transactional.md) eventos, a variável **[!UICONTROL Real time events]** ou **[!UICONTROL Batch events]** As pastas não devem ser definidas como exibições nas instâncias de execução, pois isso pode levar a problemas de permissão.

## Organize suas pastas{#organize-your-folders}

Por padrão, uma nova pasta é adicionada na parte superior da hierarquia.

Navegue pelo **Subpastas** de uma pasta para organizar suas subpastas.

Você pode mover as pastas com as setas à direita ou selecionar a opção **[!UICONTROL Sort the sub-folders in alphabetical order]** para classificá-los automaticamente.

![](assets/sort-folders.png)


## Filtrar dados em uma pasta{#filter-data-in-a-folder}

Para filtrar os dados armazenados em uma pasta, acesse as propriedades da pasta e selecione a guia Restriction .

Por exemplo, a pasta abaixo conterá somente contatos com um endereço de email e cuja origem não está marcada como &quot;Externo&quot; ou está vazia.

![](assets/add-a-filter-to-a-folder.png)


## Restringir acesso a uma pasta{#restrict-access-to-a-folder}

Use permissões em pastas para organizar e controlar o acesso aos dados do Campaign.

Para editar permissões em uma pasta específica do Campaign, siga as etapas abaixo:

1. Clique com o botão direito do mouse na pasta e selecione **[!UICONTROL Properties...]**.
1. Navegue até o **[!UICONTROL Security]** para visualizar as autorizações nessa pasta.

   ![](assets/folder-permissions.png)

* Para **autorizar um grupo ou um operador**, clique no botão **[!UICONTROL Add]** e selecione o grupo ou operador para atribuir autorizações para essa pasta.
* Para **proibir um grupo ou operador**, clique em **[!UICONTROL Delete]** e selecione o grupo ou operador para remover a autorização para essa pasta.
* Para **selecione os direitos atribuídos a um grupo ou a um operador**, selecione o grupo ou operador, selecione os direitos de acesso que deseja conceder e desmarque os outros.

### Propagar permissões {#propagate-permissions}

Para propagar autorizações e direitos de acesso, selecione o **[!UICONTROL Propagate]** nas propriedades da pasta.

As autorizações definidas nessa janela serão aplicadas a todas as subpastas do nó atual. É sempre possível sobrecarregar essas autorizações para cada uma das subpastas.

>[!NOTE]
>
>Desmarcando o **[!UICONTROL Propagate]** A opção para uma pasta não a limpa para as subpastas: você deve limpá-la explicitamente para cada uma das subpastas.

### Conceder acesso a todos os operadores {#grant-access-to-all-operators}

No **[!UICONTROL Security]** selecione a guia **[!UICONTROL System folder]** para permitir acesso a todos os operadores, independentemente de suas permissões.

Se essa opção estiver desmarcada, você deverá adicionar explicitamente o operador (ou seu grupo) de volta à lista de autorizações para que ele tenha acesso.
