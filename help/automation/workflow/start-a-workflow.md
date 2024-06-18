---
product: campaign
title: Iniciar um fluxo de trabalho
description: Saiba como iniciar um fluxo de trabalho e descubra a barra de ferramentas de ações e o menu de clique com o botão direito do mouse do fluxo de trabalho
feature: Workflows
level: Beginner
role: User, Admin
exl-id: 6d9789e3-d721-4ffd-b3fb-a0c522ab1c0a
source-git-commit: ab6c16af7652f2e8dbfa5c899c2152cefb7fc7c6
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 88%

---

# Iniciar, pausar, parar um fluxo de trabalho {#starting-a-workflow}

Um workflow é sempre iniciado manualmente. Ao ser iniciado, ele pode permanecer inativo dependendo das informações especificadas por meio de um scheduler (consulte [Scheduler](scheduler.md)) ou de um agendamento de atividade. 

Ações relacionadas à execução do fluxo de trabalho de direcionamento (iniciar, parar, pausar etc.) são processos **assíncronos**: a ordem é registrada e entrará em vigor assim que o servidor estiver disponível para aplicá-la.

A barra de ferramentas permite iniciar e controlar a execução do workflow.

A lista de opções disponíveis no menu **[!UICONTROL Actions]** e no menu de contexto estão detalhadas abaixo.

>[!IMPORTANT]
>
>Lembre-se que, quando um operador executa uma ação em um workflow (iniciar, parar, pausar, etc.), a ação não é imediatamente executada, mas colocada em uma fila para ser processada pelo módulo de workflow.

## Barra de ferramentas Ações {#actions-toolbar}

A variável **[!UICONTROL Actions]** O botão da barra de ferramentas permite acessar opções de execução adicionais em workflows selecionados. Você também pode usar o menu **[!UICONTROL File > Actions]** ou clicar com o botão direito do mouse em um fluxo de trabalho e selecionar **[!UICONTROL Actions]**.

![](assets/purge_historique.png)

* **[!UICONTROL Start]**

  Essa ação permite iniciar a execução de um workflow: um workflow **Concluído**, **Em edição** ou **Pausado** altera o status para **Iniciado**. Em seguida, o motor de workflow manipula a execução desse workflow. Se o workflow tiver sido pausado, ele será retomado, caso contrário, o workflow será iniciado desde o início e as atividades iniciais serão ativadas.

  Iniciar é um processo assíncrono: a solicitação é salva e processada o mais rápido possível por um servidor de workflow.

* **[!UICONTROL Pause]**

  Esta ação define o status do workflow como **Pausado**. Nenhuma atividade é ativada até que o workflow seja retomado. No entanto, as operações em andamento não são interrompidas.

* **[!UICONTROL Stop]**

  Esta ação interrompe um workflow sendo executado no momento. O status da instância é definido como **Concluído**. Se possível, as operações em andamento são interrompidas. Importações e queries SQL são canceladas imediatamente.

  >[!IMPORTANT]
  >
  >A interrupção de um fluxo de trabalho é um processo assíncrono: a solicitação é registrada e, em seguida, o servidor ou servidores de fluxo de trabalho cancelam as operações em andamento. A interrupção de uma instância de fluxo de trabalho pode demorar, especialmente se o fluxo de trabalho estiver em execução em vários servidores, em que cada um deles deve assumir o controle para cancelar as tarefas em andamento. Para evitar problemas, aguarde a conclusão da operação de interrupção e não execute várias solicitações de interrupção no mesmo fluxo de trabalho.

* **[!UICONTROL Unconditional stop]**

  Essa opção altera o status do fluxo de trabalho para **[!UICONTROL Finished]**. Essa ação só deve ser usada como último recurso se o processo de interrupção normal falhar após alguns minutos. Use apenas a interrupção incondicional se tiver certeza de que não há tarefas de workflow em andamento.

  >[!CAUTION]
  >
  >Essa opção destina-se somente aos usuários avançados.

* **[!UICONTROL Restart]**

  Essa ação interrompe e depois retoma o workflow. Na maioria dos casos, é possível reiniciar mais rápido. Também é útil automatizar a reinicialização quando a interrupção leva um determinado tempo: isso ocorre porque o comando &#39;Parar&#39; não está disponível quando o workflow está sendo interrompido.

  Observe que **Restart** A ação não limpa as variáveis de instância do fluxo de trabalho em comparação com **Execução**, **Parar**, e **Início** ações (a limpeza das variáveis de instância ocorre na ação Start ). Ao reiniciar um workflow, as variáveis de instância ainda estão disponíveis para uso com valores preservados. Para limpá-los, você pode:
   * Executar **Parar** e **Início** ações.
   * Adicione o código javascript abaixo no final da execução do workflow:

     ```
     var wkf = xtk.workflow.load(instance.id)
     wkf.variables='<variables/>'
     wkf.save()
     ```

* **[!UICONTROL Purge history]**

  Essa ação permite limpar o histórico do workflow. Para obter mais informações, consulte [Limpeza de logs](monitor-workflow-execution.md#purging-the-logs).

* **[!UICONTROL Start in simulation mode]**

  Essa opção permite iniciar o fluxo de trabalho no modo de simulação em vez do modo real. Isso significa que ao habilitar esse modo, somente as atividades que não afetam o banco de dados ou o sistema de arquivos serão executadas (por exemplo, **[!UICONTROL Query]**, **[!UICONTROL Union]**, **[!UICONTROL Intersection]**, etc.). Atividades que têm impacto (por exemplo, **[!UICONTROL Export]**, **[!UICONTROL Import]**, etc.) assim como as posteriores (na mesma ramificação) não são executadas.

* **[!UICONTROL Execute pending tasks now]**

  Essa ação permite iniciar todas as tarefas pendentes assim que possível. Para iniciar uma tarefa específica, clique com o botão direito do mouse na atividade e selecione **[!UICONTROL Execute pending task(s) now]**.


* **[!UICONTROL Save as template]**

  Essa ação cria um novo modelo de fluxo de trabalho com base no fluxo de trabalho selecionado. Você precisa especificar a pasta onde ele será salvo (no campo **[!UICONTROL Folder]**).


## Práticas recomendadas de execução de workflows {#workflow-execution-best-practices}

Melhore a estabilidade da instância implementando as seguintes práticas recomendadas:

* **É recomendável não agendar um fluxo de trabalho para execução por mais de 15 minutos**, pois isso pode atrapalhar o desempenho geral do sistema e criar bloqueios no banco de dados.

* **Evite deixar os fluxos de trabalho no estado pausado.** Se criar um fluxo de trabalho temporário, certifique-se de que ele será concluído corretamente e não permanecerá no estado **[!UICONTROL paused]**. Se estiver pausado, isso significa que é preciso manter as tabelas temporárias e, portanto, aumentar o tamanho do banco de dados. Atribua supervisores de workflow nas propriedades do workflow para enviar um alerta quando um workflow falhar ou for pausado pelo sistema.

  Para evitar workflows no estado pausado:

   * Verifique seus workflows regularmente para garantir que não haja erros inesperados.
   * Mantenha seus workflows o mais simples possível, por exemplo, dividindo grandes workflows em vários workflows diferentes. É possível usar as atividades **[!UICONTROL External signal]** para acionar a execução com base na execução de outros fluxos de trabalho.
   * Evite desabilitar atividades com fluxos nos fluxos de trabalho, deixando threads abertos e levando a muitas tabelas temporárias que podem consumir muito espaço. Não mantenha as atividades nos estados **[!UICONTROL Do not enable]** ou **[!UICONTROL Enable but do not execute]** em seus fluxos de trabalho.

* **Interromper fluxos de trabalho não utilizados**. Os fluxos de trabalho que continuam em execução mantêm conexões com o banco de dados.

* **Use a interrupção incondicional apenas nos casos mais raros**. Não utilize esta ação regularmente. Não executar um encerramento limpo nas conexões geradas pelos workflows com o banco de dados afeta o desempenho.

* **Não execute várias solicitações de interrupção no mesmo fluxo de trabalho**. A interrupção de um workflow é um processo assíncrono: a solicitação é registrada e, em seguida, o servidor ou servidores de workflow cancelam as operações em andamento. A interrupção de uma instância de fluxo de trabalho pode demorar, especialmente se o fluxo de trabalho estiver em execução em vários servidores, em que cada um deles deve assumir o controle para cancelar as tarefas em andamento. Para evitar problemas, aguarde a conclusão da operação de interrupção e evite interromper um fluxo de trabalho várias vezes.

## Menu de contexto {#right-click-menu}

Quando uma ou mais atividades de workflow forem selecionadas, você pode clicar com o botão direito do mouse para agir em sua seleção.

![](assets/contextual_menu.png)

As seguintes opções estão disponíveis no menu de contexto:

**[!UICONTROL Open]**: esta opção permite acessar as propriedades da atividade.

**[!UICONTROL Display logs:]** essa opção permite exibir o log de execução da tarefa para a atividade selecionada. Consulte [Exibir logs](monitor-workflow-execution.md#displaying-logs).

**[!UICONTROL Execute pending task(s) now:]** essa ação permite iniciar tarefas pendentes assim que possível.

**[!UICONTROL Workflow restart from a task:]** essa opção permite reiniciar o fluxo de trabalho usando os resultados armazenados anteriormente para essa atividade.

**[!UICONTROL Cut/Copy/Paste/Delete:]** essas opções permitem recortar, copiar, colar e excluir atividades.

**[!UICONTROL Copy as bitmap:]** essa opção permite capturar a tela de todas as atividades.

**[!UICONTROL Normal execution / Enable but do not execute / Do not enable:]** essas opções também estão disponíveis na guia **[!UICONTROL Advanced]** das propriedades da atividade. Maiores detalhes em [Execution](advanced-parameters.md#execution).

**[!UICONTROL Save / Cancel:]** permite salvar ou cancelar as alterações feitas em um fluxo de trabalho.

>[!NOTE]
>
>Você pode selecionar um grupo de atividades e aplicar um desses comandos a eles.

