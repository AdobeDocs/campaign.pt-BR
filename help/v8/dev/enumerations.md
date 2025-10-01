---
title: Gerenciar enumerações
description: Saiba como trabalhar com enumerações
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: 428de72e0459b95a6db0b06ec8541d0475b72fdd
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 51%

---

# Gerenciar enumerações {#manage-enumerations}

Uma enumeração (também chamada de lista discriminada) é uma lista predefinida de valores que você pode usar para preencher determinados campos. Enumerações ajudam a padronizar valores de campo, tornando a entrada de dados mais consistente e simplificando consultas.

Quando disponíveis, os valores são exibidos em uma lista suspensa. Você pode selecionar um valor diretamente ou começar a digitar — a entrada preditiva sugere valores correspondentes e os completa automaticamente.

![](assets/enum_values.png)

Alguns campos do console são configurados com enumerações. Se uma enumeração estiver **aberta**, você também poderá adicionar novos valores diretamente no campo.

## Listas discriminadas de acesso

Os valores usados nesses campos são gerenciados centralmente. Você pode adicioná-los, editá-los, atualizá-los ou excluí-los da árvore do Explorer em **Administração** `>` **Plataforma** `>` **Enumerações**.

* A seção superior oferece uma lista de campos para os quais uma enumeração foi definida.
* A seção inferior lista os valores disponíveis.

Quando uma enumeração é **[!UICONTROL Open]**, os usuários podem inserir um novo valor diretamente no campo correspondente na interface do usuário.

Quando uma enumeração é **[!UICONTROL Closed]**, novos valores só podem ser adicionados do menu **Enumeration**.

## Adicionar um novo valor

Para criar um novo valor de enumeração, clique no botão **[!UICONTROL Add]**.

![](assets/enumeration_screen.png)

Insira o rótulo do valor.


## Limpeza de alias {#alias-cleansing}

Nos campos de enumeração, é possível inserir valores diferentes dos valores de enumeração. Eles podem ser armazenados como são ou serem limpos.

>[!CAUTION]
>
>Limpeza de dados é um processo crítico que afeta os dados no banco de dados. O Adobe Campaign realiza atualizações de dados em massa, que podem levar à exclusão de alguns valores. Portanto, essa operação é reservada para usuários especialistas.

O valor inserido é então:

* Adicionado aos valores da lista discriminada: nesse caso, a opção **[!UICONTROL Open]** deve ser selecionada,
* ou automaticamente substituído pelo seu alias correspondente: nesse caso, este caso deve ser definido na guia **[!UICONTROL Alias]** da lista discriminada,
* ou armazenado na lista de aliases: um alias será atribuído a ele posteriormente.

### Criar um alias {#creating-an-alias}

A opção **[!UICONTROL Alias cleansing]** possibilita o uso de aliases para a lista discriminada selecionada. Quando essa opção é selecionada, a guia **[!UICONTROL Alias]** é exibida na parte inferior da janela.

Para criar um alias, siga estas etapas:

1. Navegue até a lista discriminada para atualizar o ant e clique em **[!UICONTROL Add]**.

   ![](assets/enumeration_alias_create.png)

1. Insira o alias que você deseja converter e o valor a ser aplicado e clique em **[!UICONTROL Ok]**.

1. Verifique os parâmetros antes de confirmar essa operação.

>[!CAUTION]
>
>Depois que essa etapa for confirmada, os valores anteriores talvez não sejam recuperados: eles são substituídos.

Assim, quando um usuário insere o valor **NEILSEN** em um campo &quot;company&quot; (no console do Adobe Campaign ou em um formulário), ele é automaticamente substituído pelo valor **NIELSEN Ltd**. O valor é substituído pelo fluxo de trabalho **Limpeza de alias**. Consulte [Executar limpeza de dados](#running-data-cleansing).

![](assets/enumeration_alias_use.png)

### Converter valores em aliases {#values-into-aliases}

Você pode converter valores existentes em aliases. Para fazer isso, siga estas etapas:

1. Clique com o botão direito na lista de valores e escolha **[!UICONTROL Convert values into aliases...]**.

1. Escolha os valores para converter e clique em **[!UICONTROL Next]**.

1. Clique em **[!UICONTROL Start]** para executar a conversão.

Quando a execução for concluída, o alias será adicionado à lista de aliases.

### Recuperar ocorrências de alias {#alias-hits}

Quando os usuários inserem valores que não estão incluídos na enumeração, eles são armazenados na guia **[!UICONTROL Alias]**.

O fluxo de trabalho técnico **Limpeza de alias** recupera esses valores todas as noites para atualizar a enumeração. Consulte [Executar limpeza de dados](#running-data-cleansing)

Se necessário, a coluna **[!UICONTROL Hits]** pode exibir o número de vezes que esse valor foi inserido. No entanto, o cálculo desse valor pode demorar e consumir memória. Para obter mais informações, consulte [Calcular ocorrências de entrada](#calculating-entry-occurrences).

### Executar limpeza de dados {#run-data-cleansing}

A limpeza de dados é realizada pelo fluxo de trabalho técnico **[!UICONTROL Alias cleansing]**. As configurações definidas para enumerações são aplicadas durante a execução. Consulte [Fluxo de trabalho de limpeza de alias](#alias-cleansing-workflow).

A limpeza pode ser acionada por meio do link **[!UICONTROL Cleanse values...]**.

O link **[!UICONTROL Advanced parameters...]** permite definir a data a partir da qual os valores coletados são considerados.

Clique no botão **[!UICONTROL Start]** para executar a limpeza de dados.

### Calcular ocorrências de entrada {#entry-occurrences}

A subguia **[!UICONTROL Alias]** de uma lista discriminada pode exibir o número de ocorrências de um alias entre todos os valores inseridos. Essas informações são uma estimativa e serão exibidas na coluna **[!UICONTROL Hits]**.

>[!CAUTION]
>
>O cálculo das ocorrências de entrada de alias pode demorar muito. É por isso que o usuário deve ter cuidado ao usar essa função.

Você pode executar o cálculo de ocorrências manualmente pelo link **[!UICONTROL Cleanse values...]**. Para fazer isso, clique no link **[!UICONTROL Advanced parameters...]** e selecione as opções desejadas.

* **[!UICONTROL Update the number of alias hits]**: permite atualizar as ocorrências já calculadas, com base na data inserida.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: permite que você execute o cálculo em toda a plataforma do Adobe Campaign.

Você também pode criar um fluxo de trabalho dedicado para que o cálculo seja executado automaticamente em determinado período, uma vez por semana por exemplo.

Para fazer isso, crie uma cópia do fluxo de trabalho **[!UICONTROL Alias cleansing]**, altere o scheduler e use as seguintes configurações na atividade **[!UICONTROL Enumeration value cleansing]**:

* **-updateHits** para atualizar o número de ocorrências de alias,
* **-updateHits:full** para recalcular todas as ocorrências de alias.

### Fluxo de trabalho de limpeza de alias {#alias-cleansing-workflow}

O fluxo de trabalho **Limpeza de alias** executa a limpeza do valor de enumerações. É executado diariamente por padrão.

É acessado pelo nó **[!UICONTROL Administration > Production > Technical workflows]**.


