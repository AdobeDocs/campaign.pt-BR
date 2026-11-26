---
product: campaign
title: Monitorar a execução do fluxo de trabalho
description: Monitorar a execução do fluxo de trabalho
feature: Workflows
role: Admin
version: Campaign v8, Campaign Classic v7
exl-id: bc13d706-7888-42eb-9116-5538e68cd515
TQID: 'https://experienceleague.adobe.com/Rk6eyM-0GkwgC4yiewGSiB-6zr3x1ySJI6S72KzHNb0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: cebd7cfa-b9fa-4d9f-a2ab-fce31f32c4a3
    internal-label: Audit trail
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 80%
---
# Monitorar a execução do fluxo de trabalho {#monitoring-workflow-execution}

Esta seção apresenta informações sobre como monitorar a execução de fluxos de trabalho.

Um caso de uso sobre como criar um fluxo de trabalho que permite monitorar o status de um conjunto de fluxos de trabalho &quot;pausados&quot;, &quot;interrompidos&quot; ou &quot;com erros&quot; também está disponível em [Caso de uso: supervisionar seus fluxos de trabalho](workflow-supervision.md#supervising-workflows).

Além disso, os administradores da instância podem usar a **Trilha de auditoria** para verificar as atividades, as últimas modificações feitas e o status dos fluxos de trabalho. Saiba mais sobre a Trilha de auditoria nesta [página](../../v8/reporting/audit-trail.md){target="_blank"}.

## Exibição do progresso {#displaying-progress}

Você pode monitorar a execução ao exibir o progresso usando o ícone apropriado na barra de ferramentas.

O ícone **[!UICONTROL Display progress information]** permite exibir o status e o resultado da atividade na tela de execução.

![Exibir ícone de informações de progressão na barra de ferramentas do fluxo de trabalho](assets/s_user_segmentation_toolbar_progr.png)

Quando essa opção é selecionada, as atividades executadas são exibidas em azul, as atividades pendentes piscam, os avisos são exibidos em laranja e os erros em vermelho. Essa opção também exibe o resultado das atividades na transição de saída, seguido do rótulo do resultado conforme definido nas propriedades da atividade e da duração do processo se ele exceder um segundo

![Diagrama de fluxo de trabalho com contagens de resultados e rótulos exibidos nas transições de saída das atividades](assets/s_user_segmentation_results.png)

## Exibição de logs {#displaying-logs}

O log contém o histórico ou a trilha de auditoria do fluxo de trabalho. Ele registra todas as ações do usuário, todas as operações executadas e erros encontrados. É possível:

* Selecione a guia **[!UICONTROL Tracking]** no detalhe. Esta lista contém todas as mensagens de fluxo de trabalho.

  ![Lista de fluxos de trabalho com a guia Auditoria do fluxo de trabalho selecionado mostrando mensagens no diário](assets/new-workflow-display-log-tab.png)

* Filtrar as mensagens de log por atividade. Para fazer isso, clique em **[!UICONTROL Display the tasks and the log]** na barra de ferramentas acima do diagrama para exibir as guias **[!UICONTROL Log]** e **[!UICONTROL Tasks]** logo abaixo. Selecionar uma atividade para exibir todas as mensagens relacionadas. Esta lista contém todas as mensagens quando nenhuma atividade é selecionada.

  ![Diagrama de fluxo de trabalho com a atividade de Aprovação selecionada e a guia Diário filtrada nessa atividade](assets/new-workflow-display-log-activity.png)

  >[!NOTE]
  >
  >Clicar no plano de fundo do diagrama para anular a seleção de todos os elementos.

* Visualizar apenas as mensagens vinculadas a uma determinada tarefa. Para fazer isso, selecione a guia **[!UICONTROL Tasks]** e selecione uma atividade no diagrama para restringir a lista. Clique duas vezes em uma tarefa para exibir as informações. A última guia na janela contém o log.

  ![Diagrama de fluxo de trabalho com a atividade de Aprovação selecionada e a guia Tarefas listando suas tarefas](assets/new-workflow-display-tasks-activity.png)

  O botão **[!UICONTROL Details...]** permite a exibição de todas as informações adicionais sobre a execução da atividade. Por exemplo, você pode exibir o operador de validação e, quando aplicável, o comentário inserido durante a aprovação.

>[!NOTE]
>
>O log não é removido quando um fluxo de trabalho é reiniciado. Todas as mensagens são mantidas. Se desejar descartar as mensagens de uma execução anterior, você deve limpar o histórico.

O log exibe a lista cronológica de mensagens de execução relacionadas às atividades do fluxo de trabalho de segmentação.

* Log de uma campanha de direcionamento

  Depois da execução da campanha de direcionamento, clique na guia **[!UICONTROL Tracking]** para exibir o rastreamento de execução.

  ![Exibição de auditoria de um fluxo de trabalho listando mensagens no diário com data, nome da atividade e mensagem](assets/s_user_segmentation_journal.png)

  Todas as mensagens da campanha são exibidas: campanhas realizadas, assim como avisos ou erros.

* Log de uma atividade

  Você também pode exibir o log de execução e os detalhes de cada atividade. Há duas maneiras de fazer isso:

  1. Selecione a atividade de target e clique no ícone **[!UICONTROL Display the tasks and the log]**.

     ![Exibir as tarefas e o ícone de log na barra de ferramentas do fluxo de trabalho](assets/s_user_segmentation_show_logs.png)

     A seção abaixo do diagrama exibe duas guias: Log e Tasks.

     As atividades selecionadas no diagrama atuam como filtros na lista de logs e tarefas.

     ![Diagrama de fluxo de trabalho com as guias Diário e Tarefas abaixo dele, filtrado na atividade selecionada](assets/s_user_segmentation_logs.png)

  1. Clique com o botão direito do mouse na atividade de target e selecione **[!UICONTROL Display logs]**.

     ![Clique com o botão direito do mouse no menu de uma atividade com a opção Exibir logs realçada](assets/s_user_segmentation_logs_menu.png)

     O log é exibido em uma janela separada.

## Remoção dos logs {#purging-the-logs}

O histórico do fluxo de trabalho não é removido automaticamente: todas as mensagens são mantidas por padrão. O histórico pode ser eliminado por meio do menu **[!UICONTROL File > Actions]** ou clicando no botão **[!UICONTROL Actions]** localizado na barra de ferramentas acima da lista. Selecione **[!UICONTROL Purge history]**. As opções disponíveis no menu **[!UICONTROL Actions]** estão detalhadas na seção [da barra de ferramentas de Ações](start-a-workflow.md)

![Menu de ações da lista de fluxos de trabalho com a opção Limpar histórico realçada](assets/purge_historique.png)

## Esquema de fluxo de trabalho e tabelas de trabalho {#worktables-and-workflow-schema}

O fluxo de trabalho transmite tabelas de trabalho que podem ser manipuladas por determinadas atividades. O Adobe Campaign permite, por meio de atividades de Gestão de Dados, modificar, renomear e enriquecer as colunas das tabelas de trabalho do fluxo de trabalho, por exemplo, para alinhar com a nomenclatura dependendo das necessidades do cliente, para coletar informações adicionais sobre o cobeneficiários de um contrato etc.

Também é possível criar vínculos entre várias dimensões de trabalho e definir alterações de dimensão. Por exemplo, para cada contrato registrado no banco de dados, direcione o titular principal e use dados de cotitular nas informações adicionais.

As tabelas de trabalho do fluxo de trabalho é excluído automaticamente quando o fluxo de trabalho fica passivo. Para manter uma tabela de trabalho, salve-a em uma lista por meio da atividade **[!UICONTROL List update]** (consulte [Atualização da lista](list-update.md)).

## Gestão de erros {#managing-errors}

Quando ocorre um erro, o fluxo de trabalho é pausado e a atividade está sendo executada quando a ocorrência do erro pisca em vermelho. Na visão geral do fluxo de trabalho, na guia **[!UICONTROL Monitoring]** - no link **[!UICONTROL Workflows]**, você pode exibir workflows apenas com erros, conforme mostrado abaixo.

![Guia Monitoramento, página Fluxos de trabalho com a lista suspensa de status e a opção Falha selecionada](assets/wf-global-view_filter_only_errors.png)

No Adobe Campaign Explorer, a lista de fluxos de trabalho exibe uma coluna **[!UICONTROL Failed]** por padrão.

![Lista de fluxos de trabalho no Explorer com a coluna Falha destacada](assets/wf-explorer_errors_col.png)

Quando um fluxo de trabalho está com erro, os operadores pertencentes ao grupo de supervisão do fluxo de trabalho são notificados por email, desde que seus endereços de email estejam listados em seus perfis. Esse grupo é selecionado no campo **[!UICONTROL Supervisor(s)]** das propriedades do fluxo de trabalho.

![Propriedades do fluxo de trabalho, guia Geral, com a lista de campos Supervisor(es) e os supervisores de fluxo de trabalho selecionados](assets/wf-properties_select-supervisors.png)

O conteúdo da notificação é configurado no template padrão **[!UICONTROL Workflow manager notification]** : Este modelo é selecionado na guia **[!UICONTROL Execution]** das propriedades do fluxo de trabalho. A notificação mostra o nome do fluxo de trabalho com erro e a tarefa relacionada.

Exemplo de notificação:

![Email de notificação de erro informando que o fluxo de trabalho foi interrompido, com um link de clique aqui para os detalhes do fluxo de trabalho](assets/wf-notification_error-msg.png)

O link permite acessar o Console do cliente do Adobe Campaign no modo da Web e trabalhar no workflow com erro após fazer logon.

![Página do console da Web mostrando The workflow failed, com os botões Start the workflow e Stop](assets/wf-notification_error-console.png)

Você pode configurar o fluxo de trabalho para que ele não pause e continue a execução em caso de erros. Para fazer isso, edite as **[!UICONTROL Properties]** do fluxo de trabalho e, na seção **[!UICONTROL Error management]**, selecione a opção **[!UICONTROL Ignore]** no campo **[!UICONTROL In case of error]**. Você pode então especificar o número de erros consecutivos que podem ser ignorados antes que o processo seja pausado.

Nesse caso, a tarefa com erro é anulada. Esse modo é particularmente adequado para fluxos de trabalho projetados para tentar novamente a campanha mais tarde (ações periódicas).

![Propriedades do fluxo de trabalho, guia Execução, seção Gerenciamento de erros com Caso de erro definido como Ignorar](assets/wf_edit_properties_for_error_mgt.png)

>[!NOTE]
>
>Você pode aplicar essa configuração individualmente para cada atividade. Para fazer isso, edite as propriedades da atividade e selecione o modo de gerenciamento de erro na guia **[!UICONTROL Advanced]**.

## Processamento de erros {#processing-errors}

Com relação às atividades, a opção **[!UICONTROL Process errors]** exibe uma transição específica que é habilitada ao gerar um erro. Nesse caso, o fluxo de trabalho não entra no modo de erro e a execução continua.

Os erros considerados são erros do sistema de arquivos (o arquivo não pôde ser movido, o diretório não pôde ser acessado etc.).

Essa opção não processa erros relacionados à configuração de atividade, ou seja, valores inválidos. Erros relacionados à configuração com falha não permitirão essa transição (o diretório não existe, etc.).

Se um fluxo de trabalho está pausado (manualmente ou automaticamente após um erro), o botão **[!UICONTROL Start]** reinicia-o a partir de onde parou. A atividade incorreta (ou atividade pausada) será executada novamente. As atividades anteriores não são executadas novamente.

Para executar novamente todas as atividades do fluxo de trabalho, use o botão **[!UICONTROL Restart]**.

Se você modificar atividades já executadas, as alterações não serão consideradas quando a execução do fluxo de trabalho for reiniciada.

Se você modificar atividades não executadas, elas serão consideradas quando a execução do fluxo de trabalho for reiniciada.

Se você modificar atividades em pausa, as alterações não serão consideradas corretamente quando o fluxo de trabalho for reiniciado.

Se possível, recomendamos reiniciar completamente o fluxo de trabalho após realizar as modificações.

## Supervisão de instância {#instance-supervision}

A página **[!UICONTROL Instance supervision]** permite visualizar a atividade do servidor do Adobe Campaign e exibir a lista de fluxos de trabalho e entregas com erros.

Para acessar essa página, acesse a guia **[!UICONTROL Monitoring]** e clique no link **[!UICONTROL General view]**.

![Página de instância de monitoramento com a lista de processos e os painéis Fluxos de Trabalho e Entregas](assets/wf-monitoring_from-homepage.png)

Para exibir todos os fluxos de trabalho, clique no link **[!UICONTROL Workflows]**. Use a lista suspensa para exibir os fluxos de trabalho na plataforma com base em seu estado.

![Página Fluxos de Trabalho da guia Monitoramento com a lista suspensa estado e Falha selecionada](assets/wf-monitoring_edit-wf.png)

Clique no link em um fluxo de trabalho com erros para abri-lo e visualizar seu log.

![Fluxo de trabalho com falha aberto na lista, mostrando seu diagrama com a atividade com falha e sua mensagem de diário](assets/wf-monitoring_edit-task-wf.png)

## Evitar várias execuções simultâneas {#preventing-simultaneous-multiple-executions}

Um único fluxo de trabalho pode ter várias execuções ativas ao mesmo tempo. Isso deve ser evitado em alguns casos.

Por exemplo, você pode ter um scheduler acionando a execução do fluxo de trabalho a cada hora, mas, às vezes, a execução do fluxo de trabalho inteiro demora mais de uma hora. Talvez você queira ignorar a execução se o fluxo de trabalho já estiver em execução.

Se você tiver uma atividade de sinal no início do fluxo de trabalho, talvez queira ignorar o sinal se o fluxo de trabalho estiver em execução.

O princípio geral é o seguinte:

![Princípio de bloqueio: se o bloqueio estiver definido, ignore; caso contrário, coloque o bloqueio, execute etapas protegidas e libere o bloqueio](assets/workflow-reentrancy-protection-principle.png)

A solução é usar uma variável de instância. As variáveis de instância são compartilhadas por todas as execuções paralelas dos fluxos de trabalho.

Um exemplo de fluxo de trabalho de teste simples:

![Fluxo de trabalho com um Scheduler, uma atividade Test chamada continue, uma atividade Wait e duas atividades End](assets/wkf_simultaneous_execution1.png)

O **[!UICONTROL Scheduler]** está acionando um evento a cada minuto. A seguinte atividade **[!UICONTROL Test]** vai testar a variável da instância **isRunning** para decidir se continua ou não a execução:

![Testar a atividade com a condição sim !instance.vars.isRunning e a ramificação padrão rotulada como não](assets/wkf_simultaneous_execution2.png)

>[!NOTE]
>
>**isRunning** é um nome da variável escolhido para este exemplo. Essa não é uma variável interna.

A atividade imediatamente após o **[!UICONTROL Test]** na ramificação **yes** deve definir a variável da instância no seu **Initialization script**:

```
instance.vars.isRunning = true
```

A última atividade na ramificação **sim** deve reverter a variável para falso em seu **script de Inicialização**:

```
instance.vars.isRunning = false
```

Observe que:

* Você pode verificar o valor atual da variável da instância por meio da guia **Variáveis** nas **Propriedades** do fluxo de trabalho.
* As variáveis de instância são redefinidas quando você reinicia um fluxo de trabalho.
* Em JavaScript, um valor indefinido é falso em um teste, permitindo testar a variável da instância mesmo antes de ter inicializado.
* Você pode monitorar as atividades que não são processadas devido a este mecanismo ao adicionar uma instrução de log ao script de inicialização do final &quot;nenhum&quot;.

  ```
  logInfo("Workflow already running, parallel execution not allowed.");
  ```

Nesta seção é apresentado um caso de uso: [Coordenação de atualizações de dados](coordinate-data-updates.md).

## Manutenção do banco de dados {#database-maintenance}

Os fluxos de trabalho usam muitas tabelas de trabalho que consomem espaço e acabam reduzindo o desempenho da plataforma inteira se não houver manutenção.

O fluxo de trabalho de **limpeza do banco de dados** pode ser acessado por meio do nó **Administração > Produção > Fluxos de trabalho técnicos**, permite excluir dados obsoletos para evitar o crescimento exponencial do banco de dados. O fluxo de trabalho é acionado automaticamente sem a intervenção do usuário.

Você também pode criar fluxos de trabalho técnicos específicos para limpar o consumo de espaço desnecessário de dados. Consulte e esta [seção](#purging-the-logs).

## Manuseio de fluxos de trabalho pausados {#handling-of-paused-workflows}

Por padrão, se um fluxo de trabalho estiver pausado, suas tabelas de trabalho nunca serão apagadas. A partir do build 8880, os fluxos de trabalho pausados por muito tempo são interrompidos automaticamente e suas tabelas de trabalho são removidas. Esse comportamento é acionado da seguinte maneira:

* Os fluxos de trabalho pausados por mais de sete dias aparecem como um aviso no painel de monitoramento (e na API de monitoramento) e uma notificação é enviada ao grupo supervisor.
* O mesmo acontece toda semana, quando o fluxo de trabalho técnico **[!UICONTROL cleanupPausedWorkflows]** é acionado. Para obter mais informações sobre o fluxo de trabalho, consulte [esta seção](delivery.md).
* Após quatro notificações (ou seja, um mês no estado pausado por padrão), o fluxo de trabalho é interrompido incondicionalmente. Um log aparece no fluxo de trabalho após sua interrupção. As tabelas são removidas na próxima execução **[!UICONTROL cleanup]** do fluxo de trabalho

Esses períodos podem ser configurados por meio da opção NmsServer_PausedWorkflowPeriod.

Os supervisores de fluxo de trabalho são notificados. O criador e o último usuário que modificou o fluxo de trabalho também são notificados. Os administradores não recebem as notificações.

## Filtragem de fluxos de trabalho de acordo com seu status {#filtering-workflows-status}

A interface do Campaign Classic permite monitorar o status de execução de todos os fluxos de trabalho na instância usando **visualizações** predefinidas. Para acessar essas exibições, abra o nó **[!UICONTROL Administration]** / **[!UICONTROL Audit]** / **[!UICONTROL Workflows Status]**.

As seguintes visualizações estão disponíveis:

* **[!UICONTROL Running]**: lista todos os fluxos de trabalho em execução.
* **[!UICONTROL Paused]**: lista todos os fluxos de trabalho pausados.
* **[!UICONTROL Failed]**: lista todos os fluxos de trabalho com falha.
* ** ).

![Árvore do Explorer, Administração > Auditoria > Nó Status de Fluxos de Trabalho com as exibições Em Execução, Início Pendente, Pausado e Falha](assets/workflow-monitoring-views.png)

Por padrão, essas exibições estão acessíveis na pasta **[!UICONTROL Audit]**. No entanto, é possível recriá-los no local de escolha na árvore de pastas. Dessa forma, eles estarão disponíveis para usuários padrão sem nenhum direito administrativo.

Para fazer isso:

1. Clique com o botão direito do mouse na pasta onde deseja adicionar a exibição.
1. Em **[!UICONTROL Add new folder]** / **[!UICONTROL Administration]**, selecione a exibição que deseja adicionar.
1. Após adicionar a pasta à árvore, certifique-se de configurá-la como uma visualização, para que ela exiba todos os fluxos de trabalho, seja qual for a pasta de origem. Para obter mais informações sobre como configurar exibições, consulte [Transformar uma pasta em exibição](../../v8/audiences/folders-and-views.md#turn-a-folder-to-a-view).

Além dessas exibições, é possível configurar as pastas de filtros que permitem filtrar a lista de fluxos de trabalho de acordo com o status de execução. Para isso:

1. Acesse uma pasta do tipo fluxo de trabalho e selecione o menu **[!UICONTROL Filters]** / **[!UICONTROL Advanced filter]**.
1. Configure o filtro para que o campo **[!UICONTROL @status]** do fluxo de trabalho seja igual ao estado escolhido.
1. Salve e nomeie o filtro. Assim ele estará disponível diretamente na lista de filtros.

![Caixa de diálogo de filtro avançado com a condição Real status (@status) igual a Suspenso e o ícone salvar realçado](assets/workflow-monitoring-filter.png)

Para obter mais informações, consulte esta seção.
