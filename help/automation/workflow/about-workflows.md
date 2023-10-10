---
product: campaign
title: Sobre workflows
description: Automatize processos com workflows, gerencie dados e públicos, envie mensagens e muito mais.
feature: Workflows
role: User
exl-id: 297aa4e3-b672-46b5-9016-5accee8568b8
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 96%

---

# Introdução a workflows{#gs-workflows}

## Sobre workflows{#about-workflows}

O Adobe Campaign inclui um módulo de workflow que possibilita orquestrar a gama completa de processos e tarefas através dos módulos diferentes do servidor do aplicativo. Esse ambiente gráfico abrangente permite criar processos, inclusive segmentação, execução de campanha, processamento de arquivos, participação humana, etc. O mecanismo de workflow executa e rastreia esses processos.

Você pode usar um workflow, por exemplo, para baixar um arquivo de um servidor, descompactar e importar registros contidos no banco de dados do Adobe Campaign.

Um workflow também pode envolver um ou mais operadores a serem notificados ou que podem fazer escolhas e aprovar processos. Dessa forma, é possível criar uma ação de delivery, atribuir uma tarefa a um ou mais operadores para trabalhar no conteúdo, especificar alvos e aprovar testes antes de iniciar a delivery.

Os workflows ocorrem em vários contextos e estágios do processo de gestão de campanha.

O Adobe Campaign usa workflows para:

* Criar workflows para construção do target. [Saiba mais](#targeting-workflows)
* Orquestrar campanhas em vários canais. [Saiba mais](#campaign-workflows)
* Execute processos técnicos, como limpeza, coleta de rastreamento de dados, cálculos e muito mais. [Saiba mais](#technical-workflows)

Um fluxo de trabalho é uma definição de processo: o diagrama do fulxo de trabalho, que é uma representação do que deveria acontecer. Um fluxo de trabalho também é uma instância desse processo: uma instância de fluxo de trabalho, que é uma representação do que está realmente acontecendo.

O template de workflow descreve as várias tarefas a serem executadas e como elas são vinculadas. Os templates de tarefa são chamados de atividades e são representados por ícones. Eles são vinculados por transições.

![](assets/example1.png)

## Principais princípios

Cada workflow contém:

* **[!UICONTROL Activities]**

  Uma atividade descreve um template de tarefa. As várias atividades disponíveis são representadas no diagrama por ícones. Cada tipo tem propriedades comuns e específicas. Por exemplo, enquanto todas as atividades têm um nome e rótulo, apenas a atividade **[!UICONTROL Approval]** tem uma atribuição.

  Em um diagrama de workflow, uma determinada atividade pode produzir várias tarefas, principalmente quando houver as ações de loop ou recorrentes (periódicas).

  Todas as atividades do workflow são listadas [nesta seção](activities.md), incluindo casos de uso e exemplos.

* **[!UICONTROL Transitions]**

  As transições permitem vincular atividades e definir sua sequência. Uma transição vincula uma atividade de origem a uma atividade de destino. Há vários tipos de transições, que dependem da atividade de origem. Algumas transições têm parâmetros adicionais, como duração, condição ou filtro.

  Uma transição que não está vinculada a uma atividade de destino fica em laranja e a cabeça da seta é exibida como um diamante.

  >[!NOTE]
  >
  >Um workflow que contém transições não finalizadas ainda pode ser executado: uma mensagem de aviso será gerada e o workflow será pausado quando atingir a transição, mas não gerará um erro. Dessa forma, é possível iniciar um workflow sem que ele seja concluído e adicioná-lo durante o processo.

  Para obter mais informações sobre como criar um workflow, consulte [esta seção](build-a-workflow.md).

* **[!UICONTROL Worktables]**

  O worktable contém todas as informações transportadas pela transição. Cada workflow usa várias tabelas de trabalho. Os dados transmitidos nessas tabelas podem ser acelerados e usados no ciclo de vida do workflow, desde que não sejam apagados. De fato, tabelas desnecessárias são removidas toda vez que o workflow se torna passivo e possivelmente durante a execução dos maiores workflows para evitar sobrecarga no servidor.

  Saiba mais sobre dados e tabelas de workflows [nesta seção](use-workflow-data.md).

## Seções relacionadas

Consulte estas seções para obter orientação e práticas recomendadas para automatizar processos com workflows:

* Saiba mais sobre atividades de workflow [nesta página](use-workflow-data.md).
* Saiba como criar um workflow [nesta seção](build-a-workflow.md).
* Descubra como usar workflows para importar dados no Campaign [nesta seção](campaign-workflows.md)..
* As práticas recomendadas de workflow são detalhadas [nesta página](workflow-best-practices.md).
* Encontre orientações sobre a execução do workflow [nesta seção](start-a-workflow.md).
* Saiba como monitorar workflows [nesta página](monitor-workflow-execution.md).
* Saiba como conceder acesso aos usuários para usar workflows [nesta página](managing-rights.md).
