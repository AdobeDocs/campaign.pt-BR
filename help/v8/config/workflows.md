---
title: Gerenciar e automatizar processos com fluxos de trabalho do Adobe Campaign
description: Introdução a workflows
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 21%

---

# Introdução a workflows{#gs-with-workflows}

Configure o Campaign para aproveitar os poderosos recursos de automação de campanha de marketing.

Você pode configurar:

* Fluxos de trabalho
* Campanhas recorrentes
* Ciclo de validação completo
* Alertas
* Envio automático de relatório
* Eventos acionados

## Projetar e usar fluxos de trabalho {#gs-ac-wf}

Use os workflows do Adobe Campaign para melhorar a velocidade e a escala de cada aspecto de suas campanhas de marketing, desde a criação de segmentos e a preparação de mensagens até a entrega.

Saiba como projetar workflows nesses [Casos de uso completos](#end-to-end-uc).

Saiba mais sobre a interface e a execução do usuário de workflows nestas páginas:

* [Introdução a workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=pt-BR)

* [Práticas recomendadas para fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html)

* [Fluxos de trabalho técnicos integrados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html)

* [Monitorar a execução de workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html)

* [Criar uma audiência em um fluxo de trabalho de campanha de marketing](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=pt-BR)

## Atividades de fluxos de trabalho {#wf-activities}

Saiba mais sobre as atividades de workflow disponíveis em [nesta seção](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=pt-BR)

As atividades do workflow são agrupadas por categoria. As quatro categorias de atividade estão disponíveis:

* [Atividades de direcionamento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html): Query, Lista de leitura, Enriquecimento, União e muito mais
* [Atividades de controle de fluxo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html): Scheduler, Fork, Alert, External signal e muito mais
* [Atividades de ação](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html): deliveries entre canais, código Javascript, atividades CRM, Atualização de agregação e muito mais
* [Atividades de evento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html): transferência de arquivos, download da Web e muito mais

### Alterar atividade da fonte de dados {#change-data-source-activity}

A atividade **[!UICONTROL Change data source]** permite alterar a fonte de dados de um workflow **[!UICONTROL Working table]**. Isso oferece mais flexibilidade para gerenciar dados em diferentes fontes de dados, como FDA, FFDA e o banco de dados local.

A variável **[!UICONTROL Working table]** O permite que o workflow do Adobe Campaign manipule dados e compartilhe dados com as atividades do workflow.
Por padrão, a **[!UICONTROL Working table]** é criada no mesmo banco de dados da fonte de dados que consultamos.

Por exemplo, ao consultar a tabela **[!UICONTROL Profiles]**, armazenada no banco de dados em nuvem, você criará um **[!UICONTROL Working table]** no mesmo banco de dados em nuvem.
Para alterar isso, você pode adicionar a atividade **[!UICONTROL Change Data Source]** e escolher uma fonte de dados diferente para sua **[!UICONTROL Working table]**.

Observe que, ao usar a atividade **[!UICONTROL Change Data Source]**, será necessário alternar de volta para o banco de dados em nuvem para continuar a execução do workflow.

Para usar a atividade **[!UICONTROL Change Data Source]**:

1. Criar um workflow.

1. Consulte seus destinatários alvos com uma atividade de **[!UICONTROL Query]**.

   Para obter mais informações sobre o **[!UICONTROL Query]** atividade, consulte [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).

1. No **[!UICONTROL Targeting]** , adicionar um **[!UICONTROL Change data source]** atividade e clique duas vezes nela para selecionar **[!UICONTROL Default data source]**.

   A tabela de trabalho, que contém o resultado do query, é então movida para o banco de dados PostgreSQL padrão.

1. Na guia **[!UICONTROL Actions]**, arraste e solte uma atividade **[!UICONTROL JavaScript code]** para executar operações unitárias na tabela de trabalho.

   Para obter mais informações sobre o **[!UICONTROL JavaScript code]** atividade, consulte [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html).

1. Adicione outra atividade **[!UICONTROL Change data source]** para alternar de volta para o banco de dados em nuvem.

   Clique duas vezes na atividade e selecione **[!UICONTROL Active FDA external account]** em seguida, a conta externa correspondente.

1. Agora, você pode iniciar o seu workflow.

## Gerenciar depósitos virtuais {#warehouse}

Após criar o workflow, você poderá acessar opções adicionais com o **[!UICONTROL Properties]** para obter mais configurações.

Saiba mais sobre **Propriedades do fluxo de trabalho** in [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html).

No **[!UICONTROL Execution]** do fluxo de trabalho **[!UICONTROL Properties]**, é possível vincular o workflow a depósitos diferentes e otimizar o gerenciamento da carga de trabalho. Para obter mais informações sobre **Warehouses**, consulte o [Documentação do Snowflake](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}.

![](assets/warehouse.png)

Dependendo da finalidade do workflow, você pode escolher entre os três depósitos a seguir no **[!UICONTROL Warehouse]** lista suspensa:

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**: definido por padrão ao criar um novo fluxo de trabalho.

* **[!UICONTROL Import / Export]**: deve ser definido com workflows de importação ou exportação para otimizar o desempenho de suas atividades.

* **[!UICONTROL Campaign Burst]**: deve ser definido com workflows de campanha ou deliveries para otimizar o tempo de processamento de seus deliveries.

>[!NOTE]
>
>A variável **[!UICONTROL System]** o depósito está definido somente para fluxos de trabalho internos.

## Configurar campanhas recorrentes

Crie um fluxo de trabalho recorrente e crie uma nova instância de delivery sempre que o fluxo de trabalho for executado. Por exemplo, se o fluxo de trabalho for projetado para ser executado uma vez por semana, o resultado será 52 deliveries em um ano. Isso também significa que os logs serão separados por cada instância do delivery.

Saiba como criar uma campanha recorrente no [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=pt-BR)


## Aproveitar eventos de acionador

Usar mensagens transacionais do Campaign para automatizar mensagens geradas por eventos acionados de sistemas de informações. Essas mensagens transacionais podem ser fatura, confirmação de pedido, confirmação de remessa, alteração de senha, notificação de indisponibilidade de produto, extrato de conta ou criação de conta de site, por exemplo. Essas mensagens podem ser enviadas individualmente ou em lote por email, SMS ou notificações por push.

Saiba mais sobre os recursos de mensagens transacionais no no [nesta seção](../send/transactional.md).

Conecte o Adobe Campaign e o Adobe Analytics para recuperar ações do usuário e enviar mensagens personalizadas quase em tempo real.

Saiba como integrar o Campaign a outras soluções na [nesta seção](../start/connect.md)


## Casos de uso completos de fluxos de trabalho{#end-to-end-uc}

Nesta seção você encontrará vários casos de uso que usam os recursos dos workflows do Campaign.

### Entregas {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [Enviar email de aniversário](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=pt-BR)

  Este caso de uso apresenta como planejar o envio de um e-mail recorrente para uma lista de destinatários no dia de seus aniversários.

* [Carregar conteúdo de delivery](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html)
Quando o conteúdo do delivery estiver disponível em um arquivo HTML localizado em um servidor remoto, é possível carregá-lo facilmente nos deliveries do Adobe Campaign.

* [Fluxo de trabalho de entrega entre canais](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)
Saiba como criar um fluxo de trabalho de delivery entre canais. O objetivo é segmentar um público dos recipients do banco de dados em diferentes grupos e enviar um email para o primeiro grupo e um SMS para o outro.

* [Enriquecimento de e-mail com campos de data personalizados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)
Saiba como enviar um email com campos de dados personalizados para perfis que celebram seus aniversários neste mês. O e-mail incluirá um cupom válido por uma semana antes e depois de seu aniversário.

E estas páginas na documentação do Campaign v7:

* [Automatizar a criação, edição e publicação de conteúdo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target="_blank"}
Saiba como automatizar a criação e o delivery de um bloco de conteúdo com o complemento de gerenciamento de conteúdo do Campaign.

* [Teste A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target="_blank"}
Saiba como comparar dois conteúdos de delivery de email por meio de um workflow para construção do target. A mensagem e o texto são idênticos nos dois deliveries: somente o layout é alterado. A população direcionada é dividida em três grupos: dois grupos de teste e a população restante. Uma versão diferente da entrega é enviada para cada grupo de teste.

### Monitoramento {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Enviar um relatório a uma lista](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html)
Saiba como gerar um relatório mensal integrado de Indicadores de rastreamento no formato PDF e enviá-lo para uma lista de operadores do Campaign.

* [Supervisionar os workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html)
Saiba como criar um fluxo de trabalho que permita monitorar o status de um conjunto de fluxos de trabalho &quot;pausados&quot;, &quot;interrompidos&quot; ou &quot;com erros&quot;.

* [Enviar alertas personalizados aos operadores](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html)
Saiba como enviar um alerta para um operador que conterá os nomes dos perfis que abriram um boletim informativo, mas não clicaram no link que ele continha.

### Gerenciamento de dados {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordenar atualizações de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html)
Saiba como verificar se o processo de atualização terminou antes de executar outra operação de atualização. Para fazer isso, vamos configurar uma variável de instância e permitir que o workflow teste, se a instância estiver em execução, decidir se continua a execução do workflow e executar a atualização.

* [Criar uma lista de resumo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html)
Saiba como criar um fluxo de trabalho que, após coletar arquivos e seguir vários enriquecimentos, permite criar uma lista de resumo. O exemplo é baseado em uma lista de contatos que compraram em uma loja.

* [Enriquecer dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html?lang=pt-BR)
Saiba como enviar deliveries personalizados para perfis que participaram da competição mais recente, dependendo de sua pontuação.

* [Usar agregados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html)
Saiba como identificar os últimos destinatários adicionados ao banco de dados.

* [Atualização da lista trimestral usando um query incremental](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html)
Saiba como usar um query incremental para atualizar automaticamente uma lista de recipients.

* [Configurar um fluxo de trabalho de importação recorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html)
Saiba como projetar um fluxo de trabalho que possa ser reutilizado para importar perfis provenientes de um CRM no banco de dados do Adobe Campaign.

### Direcionamento {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Consultar a tabela de destinatários](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html)
Saiba como recuperar os nomes e emails de recipients cujo domínio de email é &quot;orange.co.uk&quot; e que não vivem em Londres.

* [Consultar informações do delivery](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html)
Saiba como definir consultas sobre informações de entrega para recuperar o comportamento do perfil.

* [Calcular agregados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html)
Saiba como contar o número de perfis que vivem em Londres, de acordo com o gênero.

* [Consultar usando um relacionamento muitos para muitos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html)
Saiba como encontrar perfis não contatados nos últimos sete dias.

* [Chamar uma variável de instância em uma query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html)
Saiba como usar uma variável de instância para calcular dinamicamente a porcentagem dividida que será aplicada em uma população.

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

