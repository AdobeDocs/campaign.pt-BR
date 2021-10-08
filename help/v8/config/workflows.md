---
title: Gerenciar e automatizar processos com fluxos de trabalho do Adobe Campaign
description: Introdução a workflows
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 780a29dab99ad2bda554134ca95c435b9e76b494
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 23%

---

# Gerenciar e automatizar processos

Configure o Campaign para aproveitar os poderosos recursos de automação de campanha de marketing.

Você pode configurar:

* Fluxos de trabalho
* Campanhas recorrentes
* Ciclo de validação completo
* Alertas
* Envio automático de relatórios
* Eventos acionados

## Projetar e usar workflows{#gs-ac-wf}

Use os fluxos de trabalho do Adobe Campaign para melhorar a velocidade e a escala de cada aspecto de suas campanhas de marketing, desde a criação de segmentos e a preparação de mensagens até o delivery.

Saiba como criar workflows nesses [casos de uso completos](#end-to-end-uc).

Saiba mais sobre a interface de usuário de workflows e a execução na documentação do Campaign Classic v7:

* [Introdução a workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

* [Práticas recomendadas do workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html){target=&quot;_blank&quot;}

* [Workflows técnicos incorporados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;}

* [Monitorar a execução de workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html){target=&quot;_blank&quot;}

* [Criar um público-alvo em um workflow de campanha de marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}

## Atividades de workflow {#wf-activities}

![](../assets/do-not-localize/book.png) Saiba mais sobre a documentação disponível das atividades de workflow do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-activities.html){target=&quot;_blank&quot;}

As atividades do workflow são agrupadas por categoria. As quatro categorias de atividades estão disponíveis:

* [Atividades de direcionamento](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target=&quot;_blank&quot;}: Consulta, lista de leitura, Enriquecimento, União e muito mais
* [Atividades de controle de fluxo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html){target=&quot;_blank&quot;}: Scheduler, Bifurcar, Alerta, Sinal externo e muito mais
* [Atividades de ação](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target=&quot;_blank&quot;}: Deliveries entre canais, código Javascript, atividades CRM, Atualizar agregação e muito mais
* [Atividades de evento](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target=&quot;_blank&quot;}: Transferência de arquivos, download da Web e muito mais

### Alterar atividade da fonte de dados {#change-data-source-activity}

A atividade **[!UICONTROL Change data source]** permite alterar a fonte de dados de um workflow **[!UICONTROL Working table]**. Isso oferece mais flexibilidade para gerenciar dados em diferentes fontes de dados, como FDA, FFDA e o banco de dados local.

O **[!UICONTROL Working table]** permite que o workflow do Adobe Campaign manipule dados e compartilhe dados com as atividades do workflow.
Por padrão, a **[!UICONTROL Working table]** é criada no mesmo banco de dados da fonte de dados que consultamos.

Por exemplo, ao consultar a tabela **[!UICONTROL Profiles]**, armazenada no banco de dados em nuvem, você criará um **[!UICONTROL Working table]** no mesmo banco de dados em nuvem.
Para alterar isso, você pode adicionar a atividade **[!UICONTROL Change Data Source]** e escolher uma fonte de dados diferente para sua **[!UICONTROL Working table]**.

Observe que, ao usar a atividade **[!UICONTROL Change Data Source]**, será necessário alternar de volta para o banco de dados em nuvem para continuar a execução do workflow.

Para usar a atividade **[!UICONTROL Change Data Source]**:

1. Criar um workflow.

1. Consulte seus recipients alvos com uma atividade de **[!UICONTROL Query]**.

   Para obter mais informações sobre a atividade **[!UICONTROL Query]**, consulte a página [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) na documentação do Campaign Classic V7.

1. Na guia **[!UICONTROL Targeting]** , adicione uma atividade **[!UICONTROL Change data source]** e clique duas vezes nela para selecionar **[!UICONTROL Default data source]**.

   A tabela de trabalho, que contém o resultado do query, é então movida para o banco de dados PostgreSQL padrão.

1. Na guia **[!UICONTROL Actions]**, arraste e solte uma atividade **[!UICONTROL JavaScript code]** para executar operações unitárias na tabela de trabalho.

   Para obter mais informações sobre a atividade **[!UICONTROL JavaScript code]**, consulte a página [JavaScript code e Advanced JavaScript code](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/sql-code-and-javascript-code.html#javascript-code) na documentação do Campaign Classic V7.

1. Adicione outra atividade **[!UICONTROL Change data source]** para alternar de volta para o banco de dados em nuvem.

   Clique duas vezes na atividade e selecione **[!UICONTROL Active FDA external account]**. Em seguida, selecione a conta externa  correspondente.

1. Agora, você pode iniciar o seu workflow.

## Configurar campanhas recorrentes

Projete um workflow recorrente e crie uma nova instância de delivery toda vez que o workflow for executado. Por exemplo, se o fluxo de trabalho for projetado para ser executado uma vez por semana, o resultado será 52 deliveries em um ano. Isso também significa que os logs serão separados por cada instância de delivery.

![](../assets/do-not-localize/book.png) Saiba como criar uma campanha recorrente na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns){target=&quot;_blank&quot;}


## Aproveitar eventos de acionador

Use as mensagens transacionais do Campaign para automatizar as mensagens geradas a partir de eventos acionados de sistemas de informações. Essas mensagens transacionais podem ser fatura, confirmação de pedido, confirmação de remessa, alteração de senha, notificação de indisponibilidade de produto, extrato de conta ou criação de conta de site, por exemplo. Essas mensagens podem ser enviadas individualmente ou em lote por email, SMS ou notificações por push.

![](../assets/do-not-localize/glass.png) Saiba mais sobre os recursos de mensagens transacionais  [nesta seção](../send/transactional.md).

Conecte o Adobe Campaign e o Adobe Analytics para recuperar as ações do usuário e enviar mensagens personalizadas em tempo quase real.

![](../assets/do-not-localize/glass.png) Saiba como integrar o Campaign com outras soluções  [nesta seção](../start/connect.md)


## Casos de uso completos do fluxo de trabalho{#end-to-end-uc}

Nesta seção você encontrará vários casos de uso que usam os recursos dos workflows do Campaign. Esses casos de uso são criados no Adobe Campaign Classic v7 e se aplicam ao Adobe Campaign v8.

### Entregas {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [Teste A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target=&quot;_blank&quot;}

   Saiba como comparar dois conteúdos de delivery de email por meio de um workflow para construção do target. A mensagem e o texto são idênticos nas duas remessas: apenas o layout é alterado. A população direcionada é dividida em três grupos: dois grupos de teste e a população restante. Uma versão diferente do delivery é enviado para cada grupo de teste.

* [Envio de um email de aniversário](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html){target=&quot;_blank&quot;}

   Este caso de uso apresenta como planejar o envio de um e-mail recorrente para uma lista de recipients no dia de seus aniversários.

* [Carregando conteúdo de delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html){target=&quot;_blank&quot;} Quando o conteúdo de delivery está disponível em um arquivo HTML localizado em um servidor remoto, é possível carregar facilmente esse conteúdo nos deliveries do Adobe Campaign.

* [Workflow de delivery entre canais](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html){target=&quot;_blank&quot;}

   Saiba como criar um workflow de delivery entre canais. O objetivo é segmentar um público dos recipients do banco de dados em grupos diferentes e enviar um email para o primeiro grupo e um SMS para o outro.

* [Enriquecimento de email com campos de data personalizados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html){target=&quot;_blank&quot;}

   Saiba como enviar um email com campos de dados personalizados para perfis que celebram seus aniversários neste mês. O email incluirá um cupom válido por uma semana antes e depois de seu aniversário.

* [Automatização da criação, edição e publicação de conteúdo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target=&quot;_blank&quot;}

   Saiba como automatizar a criação e o delivery de um bloco de conteúdo com o complemento Campaign Content Management.


### Monitoramento {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Enviar um relatório para uma lista](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html){target=&quot;_blank&quot;}

   Saiba como gerar um relatório mensal integrado de Indicadores de rastreamento no formato PDF e enviá-lo para uma lista de operadores do Campaign.

* [Supervisar seus workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html){target=&quot;_blank&quot;}

   Saiba como criar um workflow que permite monitorar o status de um conjunto de workflows que são &quot;pausados&quot;, &quot;interrompido&quot; ou &quot;com erros&quot;.

* [Enviar alertas personalizados para operadores](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html){target=&quot;_blank&quot;}

   Saiba como enviar um alerta para um operador que conterá o nome dos perfis que abriram um boletim informativo, mas não clicaram no link que ele continha.

### Gerenciamento de dados {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordenar atualizações de dados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html){target=&quot;_blank&quot;}

   Saiba como verificar se o processo de atualização terminou antes de executar outra operação de atualização. Para fazer isso, vamos configurar uma variável de instância e permitir que o workflow teste, se a instância estiver em execução, decidir se continua ou não a execução do workflow e realizar a atualização.

* [Criar uma lista de resumo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html){target=&quot;_blank&quot;}

   Saiba como criar um workflow que, após coletar arquivos e após vários enriquecimentos, permite criar uma lista de resumo. O exemplo é baseado em uma lista de contatos que compraram em uma loja.

* [Enriquecer dados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html){target=&quot;_blank&quot;}

   Saiba como enviar deliveries personalizados a perfis que faziam parte da competição mais recente dependendo de sua pontuação.

* [Use agregações](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html){target=&quot;_blank&quot;}

   Saiba como identificar os últimos recipients adicionados ao banco de dados.

* [Atualização da lista trimestral usando um query incremental](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html){target=&quot;_blank&quot;}

   Saiba como usar um query incremental para atualizar automaticamente uma lista de recipients.

* [Configurar um fluxo de trabalho de importação recorrente](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html){target=&quot;_blank&quot;}

   Saiba como criar um workflow que pode ser reutilizado para importar perfis provenientes de um CRM no banco de dados do Adobe Campaign.

### Direcionamento {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Consulte a tabela de recipients](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html){target=&quot;_blank&quot;}

   Saiba como recuperar os nomes e e-mails dos recipients cujo domínio de e-mail é &quot;orange.co.uk&quot; e que não estão em Londres.

* [Informações de entrega de query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html){target=&quot;_blank&quot;}

   Saiba como definir consultas nas informações de delivery para recuperar o comportamento do perfil.

* [Calcular agregações](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html){target=&quot;_blank&quot;}

   Saiba como contar o número de perfis que vivem em Londres, de acordo com o sexo.

* [Consulta usando uma relação muitos para muitos](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html){target=&quot;_blank&quot;}

   Saiba como encontrar perfis não contatados nos últimos 7 dias.

* [Chame uma variável de instância em uma query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example){target=&quot;_blank&quot;}

   Saiba como usar uma variável de instância para calcular dinamicamente a porcentagem dividida a ser aplicada em uma população.

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

