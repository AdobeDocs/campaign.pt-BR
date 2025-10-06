---
title: Configurações da interface do Campaign
description: Saiba como personalizar as configurações da interface do Campaign
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: 2898fe400e9bf53fc2fe8fde26ccc61ec43bc69e
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 47%

---

# Configurações da interface do usuário do Campaign {#ui-settings}

## Unidades padrão {#default-units}

No Adobe Campaign, para campos que expressam uma duração (por exemplo, período de validade dos recursos, prazo de aprovação para uma tarefa, etc.), os valores podem ser expressos nas seguintes **unidades**:

* **[!UICONTROL s]** para segundos
* **[!UICONTROL mn]** para minutos
* **[!UICONTROL h]** para horas
* **[!UICONTROL d]** para dias

## Personalizar o explorador do Campaign{#customize-explorer}

Você pode adicionar pastas ao explorador do Campaign, criar visualizações e atribuir permissões.

Saiba como gerenciar pastas e modos de exibição em [esta página](../audiences/folders-and-views.md)

## Gerenciar e personalizar listas {#customize-lists}

No Console do cliente do Campaign, os dados são exibidos em listas. Você pode adaptar essas listas às suas necessidades. Por exemplo, é possível adicionar colunas, filtrar dados, contar registros, salvar e compartilhar suas configurações.

Além disso, é possível criar e salvar filtros.  Saiba mais sobre filtros em [esta página](../audiences/create-filters.md).

### Número de registros {#number-of-records}

Por padrão, o Adobe Campaign carrega os 200 primeiros registros de uma lista. Isso significa que a exibição não mostra necessariamente todos os registros da tabela que você está visualizando. Você pode executar uma contagem do número de registros na lista e carregar mais registros.

Na parte inferior direita da tela da lista, um **contador** mostra quantos registros foram carregados e o número total de registros no banco de dados (após a aplicação de filtros):

![Exibir o número total de registros em uma lista](assets/number-of-records.png)

Se aparecer um ponto de interrogação em vez do número à direita, como `240/?`, clique no contador para iniciar o cálculo.

Para carregar e exibir registros adicionais, clique em **[!UICONTROL Continue loading]**. Por padrão, 200 registros são carregados. Para alterar o número padrão de registros a serem carregados, use o ícone **[!UICONTROL Configure list]** no canto inferior direito da lista. Na janela de configuração da lista, clique em **[!UICONTROL Advanced parameters]** (canto inferior esquerdo) e altere o número de linhas que serão recuperadas.

Para carregar todos os registros, clique com o botão direito do mouse na lista e selecione **[!UICONTROL Load all]**.

>[!CAUTION]
>
>Quando uma lista contém um alto volume de registros, o carregamento completo pode levar algum tempo.
>

### Adicionar e remover colunas {#add-columns}

Para cada lista, a configuração de coluna interna pode ser adaptada para exibir mais informações ou ocultar colunas não usadas.

Quando os dados estiverem visíveis nos detalhes de um registro, clique com o botão direito do mouse no campo e selecione **[!UICONTROL Add in the list]**.

![Adicionar um campo à lista](assets/add-in-the-list.png)

A coluna é adicionada à direita das colunas existentes.

![Adicionar uma coluna de campo](assets/add-a-column.png)

Você também pode usar a tela de configuração da lista para adicionar e remover colunas:

1. Em uma lista de registros, clique no ícone **[!UICONTROL Configure list]** na seção inferior direita.
1. Clique duas vezes nos campos a serem adicionados na lista **[!UICONTROL Available fields]**: eles são adicionados à lista **[!UICONTROL Output columns]**.

   ![Tela de configuração da lista](assets/list-config-screen.png)


   >[!NOTE]
   >
   >Por padrão, campos avançados não são exibidos. Para exibi-los, clique no ícone **Exibir campos avançados**, na seção inferior direita da lista de campos disponíveis.
   >
   >Os campos são identificados por ícones específicos: SQL fields, linked tables, calculated fields, etc. Para cada campo selecionado, a descrição é exibida abaixo da lista de campos disponíveis.
   >

1. Use as setas para cima/para baixo para modificar a **ordem de exibição**.

1. Clique em **[!UICONTROL OK]** para confirmar a configuração e exibir o resultado.

Se precisar remover uma coluna, selecione-a e clique no ícone **Lixeira**.

Você pode usar o ícone **[!UICONTROL Distribution of values]** para exibir a repartição de valores para o campo selecionado na pasta atual.

![](assets/value-distribution.png)


### Criar uma nova coluna {#create-a-new-column}

É possível criar novas colunas para exibir campos adicionais na lista.

Para criar uma coluna, siga estas etapas:

1. Em uma lista de registros, clique no ícone **[!UICONTROL Configure list]** na seção inferior direita.
1. Clique no ícone **[!UICONTROL Add]** para exibir um novo campo na lista.
1. Configure o campo a ser adicionado na coluna.


### Exibir dados em subpastas {#display-sub-folders-records}

As listas podem exibir:

* Todos os registros contidos na pasta selecionada (padrão)
* Todos os registros contidos na pasta selecionada e em suas subpastas

Para alternar de um modo de exibição para outro, clique em **[!UICONTROL Display sub-levels]** na barra de ferramentas do Campaign.

### Salvar uma configuração de lista {#saving-a-list-configuration}

As configurações de lista são definidas localmente para cada usuário. Quando o cache local é limpo, as configurações locais são desabilitadas.

Por padrão, a configuração de parâmetros se aplica a todas as listas com o tipo de pasta correspondente. Quando você modifica como a lista de destinatários é exibida de uma pasta, essa configuração é aplicada a todas as outras pastas do destinatário.

É possível salvar mais de uma configuração a ser aplicada a pastas diferentes do mesmo tipo. A configuração é salva com as propriedades da pasta contendo os dados e pode ser aplicada novamente.

Para salvar uma configuração de lista de modo que ela possa ser reutilizada, siga as etapas abaixo:

1. No Explorer, clique com o botão direito do mouse na pasta que contém os dados exibidos.
1. Selecione **[!UICONTROL Properties]**.
1. Clique em **[!UICONTROL Advanced settings]** e especifique um nome no campo **[!UICONTROL Configuration]**.
1. Clique em **[!UICONTROL OK]** e em **[!UICONTROL Save]**.

É possível aplicar essa configuração a qualquer outra pasta do mesmo tipo. Saiba mais sobre pastas em [esta página](../audiences/folders-and-views.md).

### Exportar uma lista {#exporting-a-list}

Para exportar dados de uma lista, você deve usar um assistente de exportação. Para acessá-lo, selecione os elementos a serem exportados da lista, clique com o botão direito do mouse e selecione **[!UICONTROL Export...]**.

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>Os elementos de uma lista não devem ser exportados usando a função Copiar/Colar.

### Classificar uma lista {#sorting-a-list}

As listas podem conter uma grande quantidade de dados. Você pode classificar esses dados ou aplicar filtros simples ou avançados. A classificação permite exibir dados em ordem crescente ou decrescente. Os filtros permitem definir e combinar critérios para exibir apenas os dados selecionados.

Clique no cabeçalho da coluna para aplicar uma classificação crescente ou decrescente ou para cancelar a classificação de dados. O status da classificação ativa e a ordem de classificação são indicados por uma seta azul antes do rótulo da coluna. Um traço vermelho antes do rótulo da coluna significa que a classificação é aplicada aos dados indexados do banco de dados. Esse método é usado para otimizar tarefas de classificação.

Você também pode configurar a classificação ou combinar critérios de classificação. Para fazer isso, siga as etapas abaixo:

1. **[!UICONTROL Configure list]** abaixo e à direita da lista.
1. Na janela de configuração da lista, clique na guia **[!UICONTROL Sorting]**.
1. Selecione os campos a serem classificados e a direção da classificação (crescente ou decrescente).
1. A prioridade é definida pela ordem das colunas de classificação. Para alterar a prioridade, use os ícones apropriados para alterar a ordem das colunas.

   A prioridade de classificação não afeta a exibição das colunas na lista.

1. Clique em **[!UICONTROL Ok]** para confirmar essa configuração e exibir o resultado na lista.


## Recursos adicionais

* **[Comece com a interface do usuário do Campaign](../start/campaign-ui.md)** - Descubra como acessar e navegar pela interface do Adobe Campaign.
* **[Trabalhar com Listas discriminadas](../config/enumerations.md)** - Padronizar valores de campo com listas suspensas predefinidas para uma entrada de dados mais rápida e consistente.
