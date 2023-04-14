---
title: Execução do delivery de mensagens transacionais
description: Saiba mais sobre a execução e o monitoramento da entrega de mensagens transacionais
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 72%

---


# Execução do delivery {#delivery-execution}

Quando o enriquecimento estiver concluído e um template do delivery estiver vinculado ao evento, o delivery será enviado da instância de execução.

>[!NOTE]
>
>As mensagens transacionais são priorizadas em relação a qualquer outro delivery.

Todos os deliveries são agrupados na pasta **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]**.

Por padrão, eles são classificados em subpastas por mês de delivery. Essa classificação pode ser alterada nas propriedades do template de mensagem.

## Monitoramento de mensagens transacionais {#transactional-message-monitoring}

Para monitorar as mensagens transacionais, verifique os [logs do delivery](send.md).

Os deliveries transacionais enviados da instância de execução são sincronizados de volta à instância de controle por meio de um fluxo de trabalho técnico (**[!UICONTROL Message Center execution instance]**) que é executado a cada hora.

>[!NOTE]
>
>Os deliveries acumulam semanalmente os eventos com base na atualização mais recente do evento, e não na data de criação do evento. Portanto, ao extrair logs do delivery de mensagens transacionais da instância de controle, a ID do delivery associada a cada ID de log do delivery pode mudar com o tempo, conforme o log é atualizado (por exemplo, quando uma rejeição de entrada é recebida para o evento).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
