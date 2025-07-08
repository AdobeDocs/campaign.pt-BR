---
product: campaign
title: Monitorar a capacidade de entrega no Adobe Campaign
description: Saiba mais sobre as ferramentas e as diretrizes sobre o monitoramento da capacidade de entrega no Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 66%

---

# Monitorar a capacidade de entrega{#monitoring-deliverability}

Abaixo você encontrará detalhes sobre as diferentes ferramentas de monitoramento fornecidas pelo Adobe Campaign, bem como algumas diretrizes adicionais sobre como aproveitar os recursos oferecidos pelo Adobe Campaign para monitorar a capacidade de entrega da sua plataforma.

## Ferramentas de monitoramento {#monitoring-tools}

O Adobe Campaign oferece acesso a todas as ferramentas de entrega listadas abaixo.

* O [relatório de renderização da Caixa de Entrada](inbox-rendering.md) permite que você visualize suas mensagens nos principais clientes de email para verificar o conteúdo e a reputação.

* O relatório **[!UICONTROL Delivery throughput]** fornece uma visão geral de todo o rendimento da plataforma em um determinado período. Para obter mais informações, consulte [esta seção](../reporting/global-reports.md#delivery-throughput).
* Cada entrega gera um relatório de estatísticas de transmissão para os diferentes provedores de serviço da Internet (ISPs). Ele mostra algumas métricas de qualidade e reputação dos dados que podem afetar a capacidade de entrega, incluindo os seguintes números:
   * **[!UICONTROL Hard bounces]** indica a qualidade dos dados. Esse número deve ser inferior a 2%.
   * **[!UICONTROL Soft bounces]** indica a reputação. Este número não deve ser superior a 10% para qualquer ISP.

  <!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

* Em geral, o [painel de entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"} oferece acesso:
   * ao resumo de delivery, que mostra os detalhes do envio e o número de mensagens a enviar, processadas e enviadas com êxito;
   * aos logs do delivery e o histórico, que mostram qual público-alvo foi excluído e o porquê;
   * aos logs de rastreamento, que mostram informações de rastreamento, como aberturas e cliques.

## Diretrizes de monitoramento {#monitoring-guidelines}

Estas são algumas diretrizes adicionais sobre o monitoramento da capacidade de entrega:

* Verifique regularmente a [taxa de transferência da entrega](../reporting/global-reports.md#delivery-throughput) de toda a plataforma para verificar se ela é consistente com a configuração original.
* Verifique se as [tentativas](delivery-failures.md#retries) estão configuradas corretamente (30 minutos para o período de nova tentativa e mais de 20 tentativas) nos templates da entrega.
* Verifique regularmente se a caixa de [rejeição](delivery-failures.md#bounce-mail-qualification) está acessível e se a conta não está prestes a expirar.
* Verifique a taxa de transferência de cada entrega, que pode ser acessada no [painel de entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"}, para verificar se ela é consistente com a validade do conteúdo da entrega (por exemplo, &quot;vendas rápidas&quot; devem ser entregues em minutos, não em dias). O é uma ferramenta essencial para monitorar suas entregas e possíveis problemas durante o envio de mensagens.
* Ao usar as [ondas](configure-and-send.md#sending-using-multiple-waves), verifique se cada onda tem tempo suficiente para terminar antes que a próxima seja acionada.
* Verifique se o número de erros e as novas [quarentenas](quarantines.md) estão consistentes com outras entregas.
* Consulte detalhadamente os [logs da entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#delivery-logs-and-history){target="_blank"} para verificar o tipo de erro destacado (lista de bloqueios, problemas de DNS, regras anti-spam, etc.).
