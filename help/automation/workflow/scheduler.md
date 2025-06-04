---
product: campaign
title: 'Scheduler '
description: Saiba mais sobre a atividade de workflow do Scheduler
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 42%

---

# Scheduler {#scheduler}



O **Scheduler** é uma tarefa persistente que ativa a transição nos momentos especificados por seu cronograma.

A atividade **[!UICONTROL Scheduler]** deve ser considerada como um início agendado. As regras de posicionamento de atividades no gráfico são iguais para a atividade **[!UICONTROL Start]**. Esta atividade não deve ter uma transição de entrada.

## Práticas recomendadas {#best-practices}

**Reiniciar o fluxo de trabalho depois de alterar o tempo do agendador** - Ao alterar o tempo agendado da atividade **[!UICONTROL Scheduler]**, é importante reiniciar o fluxo de trabalho. Isso garante que o workflow seja executado nos horários atualizados. Sem reiniciar, o workflow continuará a ser executado de acordo com o agendamento antigo.

**Limitar frequência do Agendador** - Evite agendar fluxos de trabalho para execução com mais frequência do que a cada 15 minutos. Executá-los com mais frequência pode prejudicar o desempenho do sistema e resultar em congestionamento do banco de dados.

**Usar um Agendador por ramificação** - Cada ramificação do fluxo de trabalho deve ter apenas uma atividade **[!UICONTROL Scheduler]**. Para obter mais informações sobre as práticas recomendadas para o uso de atividades em fluxos de trabalho, consulte a [página de práticas recomendadas de fluxo de trabalho](workflow-best-practices.md#using-activities).

**Impedir execuções simultâneas de fluxo de trabalho** - Se um fluxo de trabalho for acionado por um agendador, lembre-se de que várias instâncias do fluxo de trabalho podem estar em execução ao mesmo tempo. Por exemplo, se um scheduler aciona o workflow a cada hora, mas a execução do workflow leva mais de uma hora, você pode acabar com execuções sobrepostas. Para evitar isso, considere configurar verificações para evitar várias execuções simultâneas. [Saiba como evitar várias execuções simultâneas de fluxo de trabalho](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions).

**Conta para transições atrasadas** - As transições acionadas pelo agendador poderão ser atrasadas se o fluxo de trabalho estiver executando tarefas de longa duração (como importações) ou se o módulo wfserver tiver sido interrompido temporariamente. Para atenuar isso, restrinja os tempos de ativação do scheduler para garantir que as tarefas sejam executadas dentro de uma janela de tempo definida.

## Configuração de atividade do Scheduler {#configuring-scheduler-activity}

O scheduler define o agendamento de ativação da transição. Para configurá-lo, clique duas vezes no objeto gráfico e clique em **[!UICONTROL Change...]**

![](assets/s_user_segmentation_scheduler.png)

Um assistente permite definir a frequência e o período de validade da atividade. As etapas de configuração são as seguintes:

1. Selecione a frequência de ativação e clique em **[!UICONTROL Next]**.

   ![](assets/s_user_segmentation_scheduler2.png)

1. Forneça os dias e horas de ativação. Os parâmetros desta etapa dependem da frequência selecionada na etapa anterior. Se optar iniciar a atividade várias vezes por dia, as opções de configuração serão as seguintes:

   ![](assets/s_user_segmentation_scheduler3.png)

1. Defina o período de validade do agendamento ou especifique quantas vezes será executado.

   ![](assets/s_user_segmentation_scheduler4.png)

1. Verifique a configuração e clique em **[!UICONTROL Finish]** para salvar.

   ![](assets/s_user_segmentation_scheduler5.png)
