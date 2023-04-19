---
title: Configurações da interface do Campaign
description: Saiba como personalizar as configurações da interface do Campaign
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 0b4483e0f16f14582a1a4bc28b0e1ff719823ef3
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 33%

---

# Configurações da interface do usuário do Campaign {#ui-settings}

## Enumerações {#enumerations}

Uma enumeração (também conhecida como &quot;lista discriminada&quot;) é uma lista de valores sugeridos pelo sistema para preencher campos. Use enumerações para padronizar os valores desses campos, ajudar com a entrada de dados ou usar em queries.

A lista de valores aparece como uma lista suspensa na qual você pode selecionar o valor a ser inserido no campo. A lista suspensa também permite entrada preditiva: insira as primeiras letras e o aplicativo preenche o restante.

Os valores desse tipo de campo são definidos e a administração geral desses campos (adição/exclusão de um valor) é realizada por meio do nó **[!UICONTROL Administration > Platform > Enumerations]** da árvore.

![Enumerações de acesso](assets/enumerations-menu.png)

### Tipos de enumerações {#types-of-enum}

As enumerações são armazenadas na variável **[!UICONTROL Administration > Platform > Enumerations]** pasta do explorador.

Eles podem ser: Abrir, Sistema, Emoticon ou Fechado.

* Um **Abrir** permite que os usuários adicionem novos valores diretamente nos campos com base nessa enumeração.
* A **Fechado** a enumeração tem uma lista fixa de valores que só podem ser modificados do **[!UICONTROL Administration > Platform > Enumerations]** pasta do explorador.
* Um **Emoticon** é usada para atualizar a lista de emoticons. Saiba mais
* A **Sistema** A enumeração está associada aos campos do sistema e vem com um nome Interno.

Para **Abrir** e **Fechado** enumerações, opções específicas estão disponíveis:

* **Enumeração simples** é o tipo padrão.
* **Limpeza de alias** é usada para harmonizar os valores de enumeração armazenados no banco de dados. [Saiba mais](#alias-cleansing)
* **Reservado para compartimentalização** é uma opção que permite vincular valores de cubo a essa enumeração. [Saiba mais](../reporting/gs-cubes.md)


### Limpeza de alias {#alias-cleansing}

Nos campos de enumeração, é possível selecionar um valor ou inserir um valor personalizado que não está disponível na lista suspensa. Os valores personalizados podem ser adicionados aos valores de enumerações existentes, como um novo - nesse caso, o valor **[!UICONTROL Open]** deve ser selecionada. Esses valores personalizados podem ser limpos usando recursos de limpeza de alias. Por exemplo, se um usuário digitar `Adob` em vez de `Adobe`, o processo de limpeza de alias pode substituí-lo automaticamente pelo termo correto.

>[!CAUTION]
>
>Limpeza de dados é um processo crítico que afeta os dados no banco de dados. O Adobe Campaign realiza atualizações de dados em massa, que podem levar à exclusão de alguns valores. Portanto, essa operação é reservada para usuários especialistas.

Ative o **[!UICONTROL Alias cleansing]** para usar recursos de limpeza de dados para uma enumeração. Quando essa opção é selecionada, a guia **[!UICONTROL Alias]** é exibida na parte inferior da janela.

Quando um usuário insere um valor que não existe em uma enumeração Alias cleansing, ele é adicionado ao **Valores** lista. Você pode [criar aliases a partir destes valores](#convert-to-alias)ou [criar novos aliases do zero](#create-alias).

#### Criar um alias{#create-alias}

Para criar um alias, siga estas etapas:

1. Clique em **[!UICONTROL Add]** botão do **[!UICONTROL Alias]** guia .
1. Insira o alias que você deseja converter e selecione o valor a ser aplicado na lista suspensa.

   ![Criar um novo alias](assets/new-alias.png)

1. Clique em **[!UICONTROL Ok]** e confirme.

1. Salve as alterações. A substituição de valores é realizada pela função **Limpeza de alias** fluxo de trabalho que é executado todas as noites. Consulte [Executar limpeza de dados](#running-data-cleansing).

Para todos os campos com base nessa enumeração, quando um usuário insere o valor **Adobe** em um campo &quot;empresa&quot; (no console Adobe Campaign, em um formulário web), ele será substituído automaticamente pelo valor **Adobe**.

#### Converter um valor errado em um alias{#convert-to-alias}

Também é possível converter um valor de enumeração existente em um alias. Para executar isso:

1. Na lista de valores de uma enumeração, clique com o botão direito do mouse e procure por **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![Converter um valor em um alias](assets/convert-into-aliases.png)

1. Selecione os valores a serem convertidos em aliases e clique em **[!UICONTROL Next]**.
1. Clique em **[!UICONTROL Start]** para executar a conversão.

   Quando a execução for concluída, os aliases serão adicionados à lista, na **Alias** guia . Você pode associar um valor correto para substituir entradas incorretas. Para executar isso:

1. Selecione um valor para limpar.
1. Clique no botão **Detalhe...** botão.
1. Selecione o novo valor na lista suspensa.

   ![Criar um novo alias](assets/define-new-alias.png)


>[!NOTE]
>
>É possível rastrear as ocorrências de um alias no **[!UICONTROL Hits]** na coluna **[!UICONTROL Alias]** subguia . Ele pode exibir o número de vezes que esse valor foi inserido.  [Saiba mais](#calculate-entry-occurrences).

#### Executar limpeza de dados {#running-data-cleansing}

A limpeza de dados é realizada pelo workflow técnico **[!UICONTROL Alias cleansing]**. É executado diariamente por padrão.

A limpeza também pode ser acionada por meio do **[!UICONTROL Cleanse values...]** link .

O link **[!UICONTROL Advanced parameters...]** permite definir a data a partir da qual os valores coletados são considerados.

Clique no botão **[!UICONTROL Start]** para executar a limpeza de dados.

##### Monitorar ocorrências {#calculate-entry-occurrences}

O **[!UICONTROL Alias]** a subguia de uma enumeração pode exibir o número de ocorrências de um alias entre todos os valores inseridos. Essas informações são uma estimativa e serão exibidas na coluna **[!UICONTROL Hits]**.

>[!CAUTION]
>
>O cálculo das ocorrências de entrada de alias pode demorar muito.

Você pode executar o cálculo de ocorrências manualmente pelo link **[!UICONTROL Cleanse values...]**. Para fazer isso, clique no botão **[!UICONTROL Advanced parameters...]** e selecione as opções.

* **[!UICONTROL Update the number of alias hits]**: permite atualizar as ocorrências já calculadas, com base na data inserida.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: permite que você execute o cálculo em toda a plataforma do Adobe Campaign.

Você também pode criar um workflow dedicado para que o cálculo seja executado automaticamente em determinado período, uma vez por semana por exemplo.

Para fazer isso, crie uma cópia do workflow **[!UICONTROL Alias cleansing]**, altere o scheduler e use as seguintes configurações na atividade **[!UICONTROL Enumeration value cleansing]**:

* **-updateHits** para atualizar o número de ocorrências de alias,
* **-updateHits:full** para recalcular todas as ocorrências de alias.
