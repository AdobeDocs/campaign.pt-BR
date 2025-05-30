---
title: Enviar e monitorar mensagens transacionais
description: Saiba como enviar e monitorar mensagens transacionais
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 54%

---

# Enviar e monitorar mensagens transacionais {#delivery-execution}

## Enviar mensagens{#send-transactional-msg}

Quando o enriquecimento estiver concluído e um template do delivery estiver vinculado ao evento, o delivery será enviado da instância de execução.

>[!NOTE]
>
>As mensagens transacionais são priorizadas sobre qualquer outro delivery.

Todas as entregas são agrupadas na pasta **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]**.

Por padrão, elas são classificadas em subpastas por mês de entrega. Isso pode ser alterado nas propriedades do template de mensagem.

## Monitorar mensagens {#monitor-transactional-msg}

Para monitorar as mensagens transacionais, verifique os [logs da entrega](send.md).

As entregas transacionais enviadas da instância de execução são sincronizadas de volta à instância de controle por meio de um fluxo de trabalho técnico (**[!UICONTROL Message Center execution instance]**) que é executado a cada hora.

>[!NOTE]
>
>As entregas acumulam semanalmente os eventos com base na atualização mais recente do evento, e não na data de criação do evento. Portanto, ao extrair logs da entrega de mensagens transacionais da instância de controle, a ID da entrega associada a cada ID de log da entrega pode mudar com o tempo, conforme o log é atualizado (por exemplo, quando uma rejeição de entrada é recebida para o evento).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## Relatórios{#reporting-transactional-msg}

O Adobe Campaign oferece vários relatórios que permitem controlar a atividade e suavizar a execução das instâncias de execução.

É possível acessar esses relatórios do Message Center na guia **[!UICONTROL Reports]**&#x200B;**da instância de controle**.

![](assets/mc-reports.png)

### Histórico de eventos do Centro de mensagens {#history-events}

O relatório **[!UICONTROL Message Center event history]** exibe uma visão geral da atividade do módulo do Centro de Mensagens, ou seja, o número de eventos processados e entregues como mensagens transacionais.

Quando o relatório é aberto, as informações exibidas por padrão coincidem com a taxa de mensagens transacionais enviadas com êxito. Para exibir mais níveis, abra os vários nós e coloque o cursor no nível apropriado para selecioná-lo.

Você pode exibir os dados específicos para cada tipo de evento, por período de tempo. A coluna **[!UICONTROL Events]** corresponde ao número de eventos recebidos por instância de controle. O número de eventos transformados em mensagens transacionais personalizadas é detalhado na coluna **[!UICONTROL Sent]**.


### Tempo de processamento do Centro de mensagens {#processing-time}

O relatório **[!UICONTROL Message Center processing time]** exibe os principais indicadores relacionados à fila em tempo real. Este relatório também pode ser acessado através da guia **[!UICONTROL Monitoring]** na instância de controle.

![](assets/mc-processing-time-report.png)

Você pode exibir estatísticas globais ou aquelas relativas a uma instância de execução específica. Você também pode filtrar os dados por canal e por um período específico.

Os indicadores exibidos na seção **[!UICONTROL Indicators over the period]** são calculados sobre o período selecionado:

* **[!UICONTROL Average queuing time]**: o tempo médio que processou eventos com êxito no Centro de Mensagens. Somente o tempo de processamento é levado em conta.
* **[!UICONTROL Average message sending time (s)]**: o tempo médio que processou eventos com êxito no Centro de Mensagens. Somente o tempo de entrega mta é levado em conta.
* **[!UICONTROL Average processing time (s)]**: o tempo médio que processou eventos com êxito no Centro de Mensagens. O cálculo leva em conta o tempo do processamento e o tempo de envio mta.
* **[!UICONTROL Maximum number of queued events]**: número máximo de eventos presentes na fila do Centro de Mensagens em um determinado momento.
* **[!UICONTROL Minimum number of queued events]**: número mínimo de eventos presentes na fila do Centro de Mensagens em um determinado momento.
* **[!UICONTROL Average number of queued events]**: número médio de eventos presentes na fila do Centro de Mensagens em um determinado momento.

>[!NOTE]
>
>Os limites de indicador de aviso (laranja) e de alerta (vermelho) podem ser configurados no assistente de implantação do Adobe Campaign. Consulte [Monitorar limites](#thresholds).



### Nível de serviço do Centro de mensagens {#service-level}

O relatório **[!UICONTROL Message Center service level]** exibe as estatísticas de entrega relacionadas às mensagens transacionais, bem como o detalhamento de erros. Você pode clicar em um tipo de erro para exibir os detalhes.

Este relatório também pode ser acessado através da guia **[!UICONTROL Monitoring]** na instância de controle.

Você pode exibir estatísticas globais ou aquelas relativas a uma instância de execução específica. Você também pode filtrar os dados por canal e por um período específico.

Os indicadores exibidos na seção **[!UICONTROL Indicators over the period]** são calculados sobre o período selecionado:

* **[!UICONTROL Incoming (throughput event/h)]**: número médio de horas de eventos inseridos na fila do Centro de Mensagens.
* **[!UICONTROL Incoming (event vol)]**: número de eventos inseridos na fila do Centro de Mensagens.
* **[!UICONTROL Outgoing (throughput msg/h)]**: número médio de horas de eventos de saída bem-sucedidos do Centro de Mensagens (enviados por uma entrega).
* **[!UICONTROL Outgoing (msg vol)]**: número de eventos de saída bem-sucedidos do Centro de Mensagens (enviados por uma entrega).
* **[!UICONTROL Average sending time (seconds)]**: tempo médio gasto no Centro de Mensagens para eventos processados com êxito. O cálculo leva em conta o tempo do processamento e o tempo de envio mta.
* **[!UICONTROL Error rate]**: número de eventos com erros comparados ao número de eventos que entraram na fila do Centro de Mensagens. Os erros a seguir são levados em conta: erro de roteamento, evento expirado (evento que está na fila por muito tempo), erro de entrega, ignorado pela entrega (quarentena, etc.).

>[!NOTE]
>
>Os limites de indicador de aviso (laranja) e de alerta (vermelho) podem ser configurados no assistente de implantação do Adobe Campaign. Consulte [Monitorar limites](#thresholds).

### Monitorar limites {#thresholds}

Você pode configurar os limites de aviso (laranja) e de alerta (vermelho) dos indicadores que aparecem nos relatórios de **nível de serviço do Centro de Mensagens** e **tempo de processamento do Centro de Mensagens**.

Para fazer isso, siga as etapas abaixo:

1. Abra o assistente de implantação na **instância de execução** e navegue até a página **[!UICONTROL Message Center]**.
1. Use as setas para modificar os limites.

   ![](assets/mc-thresholds.png)
