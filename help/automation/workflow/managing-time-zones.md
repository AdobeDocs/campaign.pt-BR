---
product: campaign
title: Gerenciar fusos horários
description: Gerenciar fusos horários
feature: Workflows, Configuration
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: 04b7638d-55dd-4317-b605-5d618ef014ba
TQID: https://experienceleague.adobe.com/M8aAiSm2KJdcKX0VuqX4NCIecbOm6u6B7xCvgs4bW-c
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 100%

---

# Gerenciar fusos horários{#managing-time-zones}

O Adobe Campaign permite a gestão do intervalo entre vários países relacionados à mesma instância. A configuração aplicada é aplicada durante a criação da instância.

Em um fluxo de trabalho, é possível adaptar os agendamentos de execução de atividades e vincular um fuso horário específico a uma atividade ou ao fluxo de trabalho inteiro. Essa configuração é útil ao importar o arquivo ou dentro da estrutura de agendamento de entrega.

## Agendamento de execução {#execution-scheduling}

É possível agendar a execução das tarefas usando o scheduler (consulte [Scheduler](scheduler.md)). Também é possível usar as opções de agendamento disponíveis nas atividades que oferecem essa funcionalidade. Essas atividades oferecem uma guia **[!UICONTROL Schedule]**: **[!UICONTROL File collector]**, **[!UICONTROL File transfer]**, **[!UICONTROL Web download]**, **[!UICONTROL Email reception]** &amp; **[!UICONTROL SMS]**, etc.

Para todas as tarefas agendadas, ou seja, todas as atividades com opções de agendamento, é possível selecionar o fuso horário a ser aplicado. O fuso horário é selecionado por meio da guia **[!UICONTROL Advanced]** da atividade relacionada:

![](assets/wf-timezone-in-a-box.png)

Os valores possíveis são:

* Fuso horário do servidor

  Usa o fuso horário do servidor de aplicativos Adobe Campaign.

* Fuso horário do usuário

  Usa o fuso horário do operador do Adobe Campaign que executa o fluxo de trabalho.

* Fuso horário do banco de dados

  Usa o fuso horário do servidor de banco de dados usado.

* Fusos horários específicos

  Usa o fuso horário selecionado.

Se o valor **[!UICONTROL By default]** for selecionado, o fuso horário do fluxo de trabalho será aplicado, caso contrário, será usado o do servidor de aplicativos.

## Vincular um fuso horário a uma atividade {#linking-a-time-zone-to-an-activity}

A guia **[!UICONTROL Advanced]** das atividades do fluxo de trabalho permite selecionar o fuso horário. Embora a maior parte do tempo, o fuso horário dos fluxos de trabalho seja suficiente, pode ser necessário sobrescrever ele agora e novamente em uma atividade específica, como importação de dados, para vincular datas aos seus fusos horários corretos.
