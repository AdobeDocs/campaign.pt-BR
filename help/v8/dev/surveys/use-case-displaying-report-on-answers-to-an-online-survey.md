---
product: campaign
title: 'Caso de uso: exibição do relatório sobre as respostas de uma pesquisa on-line'
description: 'Caso de uso: exibição do relatório sobre as respostas de uma pesquisa on-line'
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 6be12518-86d1-4a13-bbc2-b2ec5141b505
TQID: 'https://experienceleague.adobe.com/8JCloZIvg2WQsoFoEq6zYnDcrUOSBXCXlrkF2hY0xhc'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 66%
---
# Caso de uso: exibição do relatório sobre as respostas de uma pesquisa online{#use-case-displaying-report-on-answers-to-an-online-survey}

>[!AVAILABILITY]
>
>As pesquisas não estão disponíveis para [implantações do FFDA do Campaign](../../architecture/enterprise-deployment.md).



As respostas às pesquisas do Adobe Campaign podem ser coletadas e analisadas usando relatórios dedicados.

No exemplo a seguir, queremos coletar respostas de uma pesquisa online e exibi-las em uma tabela dinâmica.

Siga as etapas abaixo:

1. Criação de um fluxo de trabalho para recuperar as respostas à pesquisa e armazená-las em uma lista.
1. Criação de um cubo usando os dados na lista.
1. Criação de um relatório com a tabela dinâmica e visualização do detalhamento das respostas.

Antes de começar neste caso de uso, é preciso ter acesso a uma pesquisa e um conjunto de respostas para analisar.

>[!NOTE]
>
>Esse caso de uso só poderá ser implementado se tiver adquirido a opção **Survey Manager.** Verifique o contrato de licença.

## Etapa 1 — criação da coleção de dados e do fluxo de trabalho de armazenamento {#step-1---creating-the-data-collection-and-storage-workflow}

Para coletar as respostas da pesquisa, siga as etapas abaixo:

1. Crie um fluxo de trabalho e coloque uma atividade **[!UICONTROL Answers to a survey]**. Para obter mais informações sobre como usar esta atividade, consulte [Como usar os dados coletados](publish-track-and-use-collected-data.md#using-the-collected-data).
1. Edite a atividade e selecione a pesquisa cujas respostas deseja analisar.
1. Habilite a opção **[!UICONTROL Select all the answer data]** para coletar todas as informações.

   ![Atividade de respostas de pesquisa no fluxo de trabalho de Pesquisa Online com uma pesquisa selecionada e a opção Selecionar todos os dados de resposta habilitada.](assets/reporting_usecase_1_01.png)

1. Selecione as colunas a serem extraídas (nesse caso, selecione todos os campos arquivados). Esses são os campos que contêm as respostas.

   ![Selecione a caixa de diálogo de colunas extras para escolher os campos arquivados a serem adicionados às colunas de saída.](assets/reporting_usecase_1_02.png)

1. Depois que a caixa de coleção de resposta estiver configurada, posicione uma atividade do tipo **[!UICONTROL List update]** para salvar os dados.

   ![Fluxo de trabalho com uma atividade de Survey responses vinculada por uma transição Result para uma atividade List update.](assets/reporting_usecase_1_04.png)

   Nesta atividade, especifique a lista que deve ser atualizada e desmarque a opção **[!UICONTROL Purge and re-use the list if it exists (otherwise add to the list)]**: as respostas são adicionadas à tabela existente. Essa opção permitirá fazer referência à lista em um cubo. O esquema vinculado à lista não será recriado em cada atualização, o que garante a integridade do cubo que usa essa lista.

   ![Caixa de diálogo de atualização de lista com a opção Limpar e reutilizar a lista se existir desmarcada para que as respostas sejam adicionadas à lista.](assets/reporting_usecase_1_03.png)

1. Inicie o fluxo de trabalho para confirmar sua configuração.

   ![Diagrama de fluxo de trabalho de pesquisa online com respostas da pesquisa conectadas à atualização da lista, pronto para iniciar.](assets/reporting_usecase_1_05.png)

   A lista especificada é criada e inclui o esquema das respostas da pesquisa.

1. Adicione um programador para automatizar a coleta diária das respostas e a atualização da lista.

   As atividades **[!UICONTROL List update]** e **[!UICONTROL Scheduler]** estão detalhadas em .

## Etapa 2 — criação do cubo, suas medidas e seus indicadores {#step-2---creating-the-cube--its-measures-and-its-indicators}

É possível então criar o cubo e configurar suas medidas: elas serão usados para criar os indicadores que serão mostrados no relatório. Para obter mais informações sobre a criação e configuração de cubos, consulte [Sobre os cubos](https://experienceleague.adobe.com/en/docs/campaign-classic/using/reporting/ac-cubes){target="_blank"}.

Neste exemplo, o cubo se baseia nos dados da lista alimentados pelo fluxo de trabalho criado anteriormente.

![A caixa de diálogo Cubo Responde à Pesquisa Online com a opção Usar uma lista selecionada e a lista REP WEB como lista de fatos.](assets/reporting_usecase_2_01.png)

Defina as dimensões e as medidas a serem exibidas no relatório. Aqui, queremos exibir a data do contrato e o país do entrevistado.

![Guia Dimensões de Cubo com País e Depto., e guia Medidas com contrato Respondido, contrato de 2016 e contrato de 2017.](assets/reporting_usecase_2_02.png)

A guia **[!UICONTROL Preview]** permite controlar a renderização do relatório.

## Etapa 3 — criação do relatório e configuração do layout de dados na tabela {#step-3---creating-the-report-and-configuring-the-data-layout-within-the-table}

Em seguida, é possível criar um relatório com base nesse cubo e processar os dados e informações.

![Criando uma nova página de relatório com o modelo de cubo de Pesquisa Online de Respostas selecionado e o botão Criar.](assets/reporting_usecase_3_01.png)

Adapte as informações a serem exibidas com base nas suas necessidades.

![Tabela de relatório de pesquisa online de contagens de contrato de 2016 e 2017 por país, com a dimensão País nas linhas.](assets/reporting_usecase_3_02.png)
