---
title: Gerenciar enumerações
description: Saiba como trabalhar com enumerações
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: a1f479538a2d93a2ec13e35cb6813e09c8c4a5f8
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 24%

---

# Trabalhar com enumerações {#enumerations}

Uma enumeração (também chamada de lista discriminada) é uma lista predefinida de valores que você pode usar para preencher determinados campos. Enumerações ajudam a padronizar valores de campo, tornando a entrada de dados mais consistente e simplificando consultas.

Quando definidos, os valores são exibidos em uma lista suspensa. Um valor pode ser selecionado diretamente ou inserido usando a entrada preditiva, que sugere e conclui entradas correspondentes. Alguns campos incluem enumerações predefinidas e enumerações adicionais podem ser criadas, se necessário.

![](assets/enum_values.png)


## Tipos de enumerações {#types-of-enum}

Enumerações são armazenadas na pasta **[!UICONTROL Administration > Platform > Enumerations]** do explorador.

![Enumerações de acesso](../config/assets/enumerations-menu.png)


Uma enumeração pode ser: **Aberta**, **Sistema**, **Emoticon** ou **Fechada**.

* Uma lista discriminada **Aberta** permite que os usuários adicionem novos valores diretamente nos campos com base nessa lista discriminada.
* Uma enumeração **Closed** tem uma lista fixa de valores que só podem ser modificados na pasta **[!UICONTROL Administration > Platform > Enumerations]** do explorador.
* Uma lista discriminada **Emoticon** é usada para atualizar a lista de emoticons. Saiba mais
* Uma enumeração **System** está associada a campos do sistema e vem com um nome Interno.

Para as enumerações **Abertas** e **Fechadas**, opções específicas estão disponíveis:

* **Enumeração simples** é o tipo padrão padrão.
* A enumeração **Limpeza de alias** é usada para harmonizar os valores de enumeração armazenados no banco de dados. [Saiba mais](#alias-cleansing)
* **Reservado para compartimentalização** é uma opção que permite vincular valores de cubo a esta enumeração. [Saiba mais](../reporting/gs-cubes.md)


## Limpeza de alias {#alias-cleansing}

Em campos de enumeração, um valor pode ser selecionado na lista suspensa ou inserido manualmente se não estiver disponível na lista. Valores personalizados podem ser adicionados à enumeração quando a opção **[!UICONTROL Open]** está habilitada. Esses valores podem ser padronizados posteriormente por meio da limpeza de alias, que substitui automaticamente as variações pelo termo correto (por exemplo, converter `Adob` em `Adobe`).


>[!CAUTION]
>
>A limpeza de dados é uma operação crítica que afeta os valores do banco de dados. O Adobe Campaign realiza atualizações de dados em massa, que podem resultar na exclusão de determinados valores. Esta operação destina-se somente a usuários especializados.

Habilite a opção **[!UICONTROL Alias cleansing]** para usar recursos de limpeza de dados para uma enumeração. Quando essa opção é selecionada, a guia **[!UICONTROL Alias]** é exibida na parte inferior da janela.

Quando um usuário insere um valor que não existe em uma lista discriminada Alias cleansing, ele é adicionado à lista **Valores**. Você pode [criar aliases desses valores](#convert-to-alias) ou [criar novos aliases do zero](#create-alias).

### Criar um alias{#create-alias}

Para criar um alias, siga estas etapas:

1. Clique no botão **[!UICONTROL Add]** da guia **[!UICONTROL Alias]**.
1. Insira o alias que você deseja converter e selecione o valor a ser aplicado na lista suspensa.

   ![Criar um novo alias](assets/new-alias.png)

1. Clique em **[!UICONTROL Ok]** e confirme.

1. Salve as alterações. A substituição de valores é executada pelo fluxo de trabalho **Limpeza de alias**, que é executado todas as noites. Consulte [Executar limpeza de dados](#running-data-cleansing).

Para todos os campos baseados nesta enumeração, quando um usuário insere o valor **Adobe** em um campo &quot;empresa&quot; (no Console do Cliente do Adobe Campaign, em um formulário web), ele é substituído automaticamente pelo valor **Adobe**.

### Converter um valor incorreto em um alias{#convert-to-alias}

Você também pode converter um valor de enumeração existente em um alias. Para fazer isso:

1. Na lista de valores de uma enumeração, clique com o botão direito do mouse e procure **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![Converter um valor em um alias](assets/convert-into-aliases.png)

1. Selecione os valores a serem convertidos em aliases e clique em **[!UICONTROL Next]**.
1. Clique em **[!UICONTROL Start]** para executar a conversão.

   Quando a execução for concluída, os aliases serão adicionados à lista, na guia **Alias**. Você pode associar um valor correto para substituir entradas incorretas. Para fazer isso:

1. Selecione um valor a ser limpo.
1. Clique no botão **Detail...**.
1. Selecione o novo valor na lista suspensa.

   ![Criar um novo alias](assets/define-new-alias.png)


>[!NOTE]
>
>Você pode rastrear as ocorrências de um alias na coluna **[!UICONTROL Hits]** na subguia **[!UICONTROL Alias]**. Ele pode exibir o número de vezes que esse valor foi inserido.  [Saiba mais](#calculate-entry-occurrences).

### Executar limpeza de dados {#running-data-cleansing}

A limpeza de dados é realizada pelo fluxo de trabalho técnico **[!UICONTROL Alias cleansing]**. É executado diariamente por padrão.

A limpeza também pode ser acionada por meio do link **[!UICONTROL Cleanse values...]**.

O link **[!UICONTROL Advanced parameters...]** permite definir a data a partir da qual os valores coletados são considerados.

Clique no botão **[!UICONTROL Start]** para executar a limpeza de dados.

### Monitorar ocorrências {#calculate-entry-occurrences}

A subguia **[!UICONTROL Alias]** de uma enumeração pode exibir o número de ocorrências de um alias entre todos os valores inseridos. Essas informações são uma estimativa e serão exibidas na coluna **[!UICONTROL Hits]**.

>[!CAUTION]
>
>O cálculo das ocorrências de entrada de alias pode demorar muito.
>

Você pode executar o cálculo de ocorrências manualmente pelo link **[!UICONTROL Cleanse values...]**. Para fazer isso, clique no link **[!UICONTROL Advanced parameters...]** e selecione a(s) opção(ões).

* **[!UICONTROL Update the number of alias hits]**: permite atualizar as ocorrências já calculadas, com base na data inserida.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: permite que você execute o cálculo em toda a plataforma do Adobe Campaign.

Você também pode criar um fluxo de trabalho dedicado para que o cálculo seja executado automaticamente em determinado período, uma vez por semana por exemplo.

Para fazer isso, crie uma cópia do fluxo de trabalho **[!UICONTROL Alias cleansing]**, altere o scheduler e use as seguintes configurações na atividade **[!UICONTROL Enumeration value cleansing]**:

* **-updateHits** para atualizar o número de ocorrências de alias,
* **-updateHits:full** para recalcular todas as ocorrências de alias.
