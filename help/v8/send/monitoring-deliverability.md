---
product: campaign
title: Monitorar a capacidade de entrega no Adobe Campaign
description: Saiba mais sobre as ferramentas e as diretrizes sobre o monitoramento da capacidade de entrega no Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 3dd4f6041ef193a0d7ea74a0b2c06183861c2797
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 55%

---

# Monitorar a capacidade de entrega{#monitoring-deliverability}

Abaixo você encontrará detalhes sobre as diferentes ferramentas de monitoramento fornecidas pelo Adobe Campaign, bem como algumas diretrizes adicionais sobre como aproveitar os recursos oferecidos pelo Adobe Campaign para monitorar a capacidade de entrega da sua plataforma.

## Ferramentas de monitoramento {#monitoring-tools}

O Adobe Campaign oferece acesso às ferramentas de entrega listadas abaixo.

### Renderização da caixa de entrada {#inbox-rendering-tool}

O [relatório de renderização da Caixa de Entrada](inbox-rendering.md) permite que você visualize suas mensagens nos principais clientes de email para verificar o conteúdo e a reputação.

### Taxa de transferência de entrega {#throughput-reports}

O relatório **[!UICONTROL Delivery throughput]** fornece uma visão geral de todo o rendimento da plataforma em um determinado período. Para obter mais informações, consulte [esta seção](../reporting/global-reports.md#delivery-throughput).

### Estatísticas de transmissão {#broadcast-statistics}

Cada entrega gera um relatório de estatísticas de transmissão para os diferentes provedores de serviço da Internet (ISPs). Ele mostra algumas métricas de qualidade e reputação dos dados que podem afetar a capacidade de entrega, incluindo os seguintes números:

**[!UICONTROL Hard bounces]** indica a qualidade dos dados. Esse número deve ser inferior a 2%.

**[!UICONTROL Soft bounces]** indica a reputação. Este número não deve ser superior a 10% para qualquer ISP.

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### Painel de entrega {#delivery-dashboard-monitoring}

Em geral, o [painel de entrega](delivery-dashboard.md) oferece acesso:

O resumo de delivery, que mostra os detalhes do envio e o número de mensagens a enviar, processadas e enviadas com êxito.

Os logs do delivery e o histórico, que mostram qual público-alvo foi excluído e o porquê.

Os logs de rastreamento, que mostram informações de rastreamento, como aberturas e cliques.

### Teste do SpamAssassin {#spam-testing}

Use o [SpamAssassin](spamassassin.md) para testar seu conteúdo de email e marcá-lo para determinar se uma mensagem corre o risco de ser considerada spam pelas ferramentas antisspam usadas no recebimento.

### Painel de controle {#control-panel-monitoring}

>[!NOTE]
>
>O Painel de controle do Campaign está disponível para usuários do Campaign v8 Managed Cloud Services. Saiba mais sobre o [Painel de controle](../config/self-service.md).

O [Painel de Controle](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR){target="_blank"} do Campaign fornece recursos de monitoramento para a capacidade de entrega, incluindo gerenciamento de subdomínio e certificado, monitoramento de perfis ativos, além de métricas de taxa de transferência e latência de entrega.

## Diretrizes de monitoramento {#monitoring-guidelines}

Estas são algumas diretrizes adicionais sobre o monitoramento da capacidade de entrega:

### Monitoramento da taxa de transferência da plataforma

Verifique regularmente a [taxa de transferência da entrega](../reporting/global-reports.md#delivery-throughput) de toda a plataforma para verificar se ela é consistente com a configuração original.

### Tentar novamente a configuração

Verifique se as [tentativas](delivery-failures.md#retries) estão configuradas corretamente (30 minutos para o período de nova tentativa e mais de 20 tentativas) nos modelos da entrega.

### Verificação de caixa de correio de devolução

Verifique regularmente se a caixa de [rejeição](delivery-failures.md#bounce-mail-qualification) está acessível e se a conta não está prestes a expirar.

### Verificações de desempenho da entrega

Verifique a taxa de transferência de cada delivery, que pode ser acessada no [painel de delivery](delivery-dashboard.md), para garantir que ela seja consistente com a validade do conteúdo do delivery (por exemplo, &quot;vendas rápidas&quot; devem ser entregues em minutos, não em dias).

### Validação do tempo de onda

Ao usar as [ondas](configure-and-send.md#sending-using-multiple-waves), verifique se cada onda tem tempo suficiente para terminar antes que a próxima seja acionada.

### Monitoramento de quarentena

Verifique se o número de erros e as novas [quarentenas](quarantines.md) estão consistentes com outras entregas.

### Análise do log de entrega

Consulte detalhadamente os [logs da entrega](delivery-dashboard.md#delivery-logs-and-history) para verificar o tipo de erro destacado (lista de bloqueios, problemas de DNS, regras anti-spam, etc.).

## Tópicos relacionados

O [Manual de práticas recomendadas de entrega do Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR){target="_blank"} fornece orientação abrangente sobre a estratégia, a definição, as métricas e as práticas recomendadas de entrega.

[O que é a capacidade de entrega](about-deliverability.md) apresenta os principais conceitos de capacidade de entrega e como melhorar sua taxa de capacidade de entrega no Campaign.

[Falhas e rejeições de entrega](delivery-failures.md) descreve os diferentes tipos de falhas de entrega, como o Campaign as trata e inclui orientação para a solução de problemas comuns.

[Gerenciamento de quarentena](quarantines.md) explica como o Campaign gerencia endereços em quarentena para proteger sua reputação de envio.

[Controlar conteúdo da mensagem](control-message-content.md) fornece orientação sobre como garantir que o conteúdo seja otimizado para entrega.
