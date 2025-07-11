---
product: campaign
title: Propriedades do workflow
description: Saiba mais sobre as propriedades do workflow do Campaign
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 80%

---

# Propriedades do workflow{#workflow-properties}

## Guia Execution {#execution-tab}

A guia **[!UICONTROL Execution]** da janela **[!UICONTROL Properties]** em um workflow está dividida em três seções:

![](assets/wf_execution_tab.png)

### Scheduler {#scheduler}

Esta seção só é exibida nos workflows da campanha.

* **[!UICONTROL Priority]**

  O mecanismo de workflow processa os workflows a serem executados com base no critério de prioridade definido neste campo. Por exemplo, todos os workflows com uma prioridade **[!UICONTROL Average]** serão executados antes daqueles com prioridade **[!UICONTROL Low]**.

* **[!UICONTROL Schedule execution for a time of low activity]**

  Essa opção adia o início do workflow para um período menos ocupado. Alguns workflows podem custar caro em termos de recursos para o motor do banco de dados. Recomendamos o agendamento da execução para uma hora de baixa atividade (à noite, por exemplo). Os períodos de baixa atividade são definidos no workflow técnico em **[!UICONTROL Processes on campaigns]**.

### Execução {#execution}

* **[!UICONTROL Default affinity]**

  Se a sua instalação incluir vários servidores de workflow, utilize este campo para escolher a máquina em que o workflow será executado. Se o valor definido nesse campo não existir em nenhum servidor, o workflow permanecerá pendente.

* **[!UICONTROL History in days]**

  As tabelas de trabalho do banco de dados mantêm um histórico de execuções (tarefas, eventos, log). Aqui você pode definir a quantidade de dias para o arquivamento deste workflow: o processo de limpeza excluirá os arquivos mais antigos uma vez por dia. Se o valor nesse campo for zero, o arquivo nunca será excluído.

* **[!UICONTROL Log SQL queries in the journal]**

  Essa operação é reservada para usuários avançados. Refere-se a workflows que contêm atividades de direcionamento (consulta, união, intersecção, etc.). Quando essa opção é marcada, as queries SQL enviadas ao banco de dados durante a execução do workflow são exibidas na Adobe Campaign: isso significa que você pode analisá-las para otimizar as queries ou diagnosticar problemas.

  Os queries são exibidos em uma guia **[!UICONTROL SQL logs]** adicionada ao workflow (exceto workflows da campanha) e à atividade **[!UICONTROL Properties]** quando a opção está habilitada. A aba **[!UICONTROL Audit]** também inclui queries SQL.

  ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL Execute in the engine]**

  Essa opção só pode ser usada para depuração e nunca em produção. Quando estiver habilitado, o workflow terá prioridade e todos os outros fluxos serão interrompidos até a conclusão deste.

* **[!UICONTROL Enable watchdog supervisor to keep workflow running permanently]**

  Essa opção força os workflows a serem reiniciados automaticamente após um erro. Quando habilitado, a reinicialização verificará o status do workflow a cada 30 segundos e o reiniciará quando necessário. Para ajustar o intervalo de 30 segundos, você pode criar a opção técnica `XtkWorkflow_WatchdogRestartTimerTimeout` e usar um tipo de dados integer para especificar o atraso desejado.

  >[!NOTE]
  >
  >* Esta opção está disponível a partir da v8.6.4.
  >
  >* Esta opção destina-se a usuários avançados e deve ser habilitada somente para **workflows técnicos**.
  >
  >* Esta opção é habilitada por padrão para o contexto disponível de fluxos de trabalho de replicação centralizados de uma [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md). [Saiba mais](../../v8/architecture/replication.md)

### Gerenciamento de erros {#error-management}

* **[!UICONTROL Troubleshooting]**

  Este campo permite a definição das ações a serem tomadas se uma tarefa de workflow tiver erros. Há duas opções possíveis:

   * **[!UICONTROL Stop the process]**: o workflow é pausado automaticamente. O status do workflow muda para **[!UICONTROL Failed]**. Quando o problema for resolvido, reinicie o workflow usando os botões **[!UICONTROL Start]** ou **[!UICONTROL Restart]**.
   * **[!UICONTROL Ignore]**: o status da tarefa que provocou o erro muda para **[!UICONTROL Failed]**, mas o workflow mantém o status de **[!UICONTROL Started]**. Essa configuração é relevante para tarefas recorrentes: se a ramificação incluir um programador, ela iniciará normalmente na próxima vez que o workflow for executado.

* **[!UICONTROL Consecutive errors]**

  Este campo fica disponível quando o valor **[!UICONTROL Ignore]** for selecionado no campo **[!UICONTROL In case of errors]**. Você pode especificar quantos erros podem ser ignorados antes que o processo seja interrompido. Após esse número ser alcançado, o status do workflow será alterado para **[!UICONTROL Failed]**. Se o valor desse campo for 0, o workflow nunca será interrompido independentemente do número de erros.

* **[!UICONTROL Template]**

  Este campo permite que você selecione o template de notificação a ser enviado aos supervisores do workflow quando seu status for alterado para **[!UICONTROL Failed]**.

  Os operadores envolvidos serão notificados por e-mail, se houver um endereço de e-mail em seu perfil. Para definir supervisores de workflow, vá até o campo **[!UICONTROL Supervisor(s)]** das propriedades (guia **[!UICONTROL General]**).

  ![](assets/wf-properties_select-supervisors.png)

  O modelo padrão **[!UICONTROL Notification to a workflow supervisor]** inclui um link para acessar o Console do Cliente do Adobe Campaign pela Web para que o recipient possa trabalhar no problema quando estiver conectado.

  Para criar um template personalizado, vá para **[!UICONTROL Administration>Campaign management>Technical deliveries and templates]**.
