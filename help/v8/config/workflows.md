---
product: Adobe Campaign
title: Introdução à automação de campanha
description: Introdução à automação de campanha
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 19%

---

# Gerenciar e automatizar processos

Configure o Campaign para aproveitar os poderosos recursos de automação de campanha de marketing.

Você pode configurar:

* Workflows
* Campanhas recorrentes
* Ciclo de validação completo
* Alertas
* Envio automático de relatórios
* Eventos acionados

## Projete e use workflows{#gs-ac-wf}

Use os fluxos de trabalho do Adobe Campaign para melhorar a velocidade e a escala de cada aspecto de suas campanhas de marketing, desde a criação de segmentos e a preparação de mensagens até o delivery.

Saiba como criar workflows nesses[casos de uso completos](#end-to-end-uc).

Saiba mais sobre a interface de usuário de workflows e a execução na documentação do Campaign Classic v7:

[!DNL :arrow_upper_right:]  [Introdução a workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Atividades de workflow:
   * [Atividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html) de direcionamento: query, lista de leitura, enriquecimento, união e muito mais
   * [Atividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html) de controle de fluxo: scheduler, bifurcação, alerta, sinal externo e muito mais
   * [Atividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) de ação: deliveries entre canais, código Javascript, atividades CRM, agregação de atualização e muito mais
   * [Atividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) de evento: transferência de arquivos, download da Web e muito mais
      [!DNL :arrow_upper_right:]  [Criar um público-alvo em um workflow de campanha de marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)

      [!DNL :arrow_upper_right:]  [Práticas recomendadas de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
      [!DNL :arrow_upper_right:] [Workflows técnicos incorporados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
      [!DNL :arrow_upper_right:] [Monitorar a execução de workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)


## Configurar campanhas recorrentes

Projete um workflow recorrente e crie uma nova instância de delivery toda vez que o workflow for executado. Por exemplo, se o fluxo de trabalho for projetado para ser executado uma vez por semana, o resultado será 52 deliveries em um ano. Isso também significa que os logs serão separados por cada instância de delivery.

[!DNL :arrow_upper_right:] Saiba como criar uma campanha recorrente na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).


## Aproveitar eventos de acionador

Use as mensagens transacionais do Campaign para automatizar as mensagens geradas a partir de eventos acionados de sistemas de informações. Essas mensagens transacionais podem ser fatura, confirmação de pedido, confirmação de remessa, alteração de senha, notificação de indisponibilidade de produto, extrato de conta ou criação de conta de site, por exemplo. Essas mensagens podem ser enviadas individualmente ou em lote por email, SMS ou notificações por push.

[!DNL :bulb:] Saiba mais sobre os recursos de mensagens transacionais  [nesta seção](../send/transactional.md).

Conecte o Adobe Campaign e o Adobe Analytics para recuperar as ações do usuário e enviar mensagens personalizadas em tempo quase real.

[!DNL :bulb:] Saiba como integrar o Campaign com outras soluções  [nesta seção](../start/connect.md)


## Casos de uso completos do fluxo de trabalho{#end-to-end-uc}

Nesta seção você encontrará vários casos de uso que usam os recursos dos workflows do Campaign. Esses casos de uso são criados no Adobe Campaign Classic v7 e se aplicam ao Adobe Campaign v8.

### Deliveries {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [Teste A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html)

   Saiba como comparar dois conteúdos de delivery de email por meio de um workflow para construção do target. A mensagem e o texto são idênticos nas duas remessas: apenas o layout é alterado. A população direcionada é dividida em três grupos: dois grupos de teste e a população restante. Uma versão diferente do delivery é enviado para cada grupo de teste.

* [Envio de um e-mail de aniversário](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html)

   Este caso de uso apresenta como planejar o envio de um e-mail recorrente para uma lista de recipients no dia de seus aniversários.

* [Carregamento de conteúdo de delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)

   Quando o conteúdo do delivery está disponível em um arquivo HTML localizado em um servidor remoto, é possível carregar facilmente esse conteúdo nos deliveries do Adobe Campaign.

* [Fluxo de trabalho de delivery entre canais](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)

   Saiba como criar um workflow de delivery entre canais. O objetivo é segmentar um público dos recipients do banco de dados em grupos diferentes e enviar um email para o primeiro grupo e um SMS para o outro.

* [Enriquecimento de e-mail com campos de data personalizados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)

   Saiba como enviar um email com campos de dados personalizados para perfis que celebram seus aniversários neste mês. O email incluirá um cupom válido por uma semana antes e depois de seu aniversário.

* [Automação da criação, edição e publicação de conteúdo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html)

   Saiba como automatizar a criação e o delivery de um bloco de conteúdo com o complemento Campaign Content Management.


### Monitoramento {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Enviar um relatório a uma lista](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html)

   Saiba como gerar um relatório mensal integrado de Indicadores de rastreamento em formato PDF e enviá-lo para uma lista de operadores do Campaign.

* [Supervisionar os workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html)

   Saiba como criar um workflow que permite monitorar o status de um conjunto de workflows que são &quot;pausados&quot;, &quot;interrompido&quot; ou &quot;com erros&quot;.

* [Enviar alertas personalizados aos operadores](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html)

   Saiba como enviar um alerta para um operador que conterá o nome dos perfis que abriram um boletim informativo, mas não clicaram no link que ele continha.

### Gerenciamento de dados {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordenar atualizações de dados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html)

   Saiba como verificar se o processo de atualização terminou antes de executar outra operação de atualização. Para fazer isso, vamos configurar uma variável de instância e permitir que o workflow teste, se a instância estiver em execução, decidir se continua ou não a execução do workflow e realizar a atualização.

* [Criar uma lista de resumo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html)

   Saiba como criar um workflow que, após coletar arquivos e após vários enriquecimentos, permite criar uma lista de resumo. O exemplo é baseado em uma lista de contatos que compraram em uma loja.

* [Enriquecer dados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)

   Saiba como enviar deliveries personalizados a perfis que faziam parte da competição mais recente dependendo de sua pontuação.

* [Usar agregações](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html)

   Saiba como identificar os últimos recipients adicionados ao banco de dados.

* [Atualização da lista trimestral usando um query incremental](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html)

   Saiba como usar um query incremental para atualizar automaticamente uma lista de recipients.

* [Configurar um fluxo de trabalho de importação recorrente](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html)

   Saiba como criar um workflow que pode ser reutilizado para importar perfis provenientes de um CRM no banco de dados do Adobe Campaign.

### Direcionamento {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Consultar a tabela de recipients](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html)

   Saiba como recuperar os nomes e e-mails dos recipients cujo domínio de e-mail é &quot;orange.co.uk&quot; e que não estão em Londres.

* [Consultar informações do delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html)

   Saiba como definir consultas nas informações de delivery para recuperar o comportamento do perfil.

* [Calcular agregados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html)

   Saiba como contar o número de perfis que vivem em Londres, de acordo com o sexo.

* [Consultar usando um relacionamento muitos para muitos](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html)

   Saiba como encontrar perfis não contatados nos últimos 7 dias.

* [Chamar uma variável de instância em uma query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example)

   Saiba como usar uma variável de instância para calcular dinamicamente a porcentagem dividida a ser aplicada em uma população.

