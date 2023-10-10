---
product: campaign
title: Scheduler
description: Saiba mais sobre a atividade de workflow do Scheduler
feature: Workflows
role: User
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 100%

---

# Scheduler {#scheduler}



O **Scheduler** é uma tarefa persistente que ativa a transição nos momentos especificados por seu cronograma.

A atividade **[!UICONTROL Scheduler]** deve ser considerada como um início agendado. As regras de posicionamento de atividades no gráfico são iguais para a atividade **[!UICONTROL Start]**. Esta atividade não deve ter uma transição de entrada.

## Práticas recomendadas {#best-practices}

* É recomendável não agendar um workflow para execução por mais de 15 minutos, pois pode atrapalhar o desempenho geral do sistema e criar bloqueios no banco de dados.

* Nunca use mais de uma atividade **[!UICONTROL Scheduler]** por ramificação em um workflow. Consulte [Uso de atividades](workflow-best-practices.md#using-activities).

* O uso de uma atividade do scheduler pode gerar várias execuções ao mesmo tempo de um workflow em andamento. Por exemplo, você pode ter um scheduler acionando a execução do workflow a cada hora, mas, às vezes, a execução do workflow inteiro demora mais de uma hora.

  Talvez você queira ignorar a execução se o workflow já estiver em execução. Para obter mais informações sobre como evitar execuções simultâneas de um workflow, consulte [esta página](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions).

* Observe que a transição pode ser ativada várias horas depois caso o workflow esteja executando uma tarefa de longo prazo, como uma importação, ou se o módulo wfserver for interrompido por um momento. Nesse caso, pode ser necessário restringir a execução da tarefa ativada pelo scheduler para um determinado intervalo de tempo.

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
