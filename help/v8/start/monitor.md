---
title: Visão geral do monitoramento de campanha
description: Saiba como monitorar deliveries, workflows e a instância do Campaign
feature: Monitoring
role: User
level: Beginner
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 3%

---

# Visão geral do monitoramento de campanha {#monitor-campaign}

A Adobe Campaign oferece um conjunto abrangente de recursos para monitorar seus processos, deliveries e ambientes, a fim de garantir o desempenho ideal e solucionar problemas de forma proativa.

>[!NOTE]
>
>Como administrador do Campaign, você também pode usar o [Painel de Controle do Campaign](#control-panel) para monitorar suas instâncias, gerenciar o desempenho e definir configurações com recursos de autoatendimento.

## Monitore seus deliveries {#monitor-deliveries}

O monitoramento de deliveries, após serem enviados, é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes. Após enviar um delivery, você poderá monitorar seu status e rastrear as métricas principais no painel do delivery. O painel fornece acesso a logs do delivery, logs de exclusão, logs de rastreamento e outros recursos de monitoramento para ajudar você a analisar o desempenho do delivery em todos os canais.

**Entregas de email** - Monitore o status da entrega de email, rastreie as métricas principais e acesse os logs detalhados. Saiba mais sobre o [monitoramento de entregas na interface do usuário do Campaign](../send/delivery-dashboard.md), [status de entrega](../send/delivery-statuses.md) e [monitoramento de entrega de email](../send/send.md#email-monitoring).

**Entregas de SMS** - Rastreie o status da entrega de SMS e monitore as métricas principais no painel de entrega de SMS. Saiba mais sobre o [monitoramento de SMS](../send/sms/sms-monitor.md).

**Notificações por push** - Monitore entregas de notificações por push para garantir que elas cheguem aos usuários do aplicativo móvel de maneira eficaz. Saiba mais sobre o [monitoramento de notificação por push](../send/push.md#push-test).

**Mensagens transacionais** - Para mensagens acionadas por eventos, monitore o status do processamento do evento, a execução da mensagem e o status da entrega. Saiba mais sobre [monitoramento de mensagens transacionais](../send/delivery-execution.md#monitor-messages).

**Falhas de entrega** - Entender por que uma entrega falhou é essencial para manter um banco de dados limpo e garantir boas taxas de entrega. As falhas de delivery são classificadas em rejeições permanentes, rejeições temporárias e mensagens ignoradas. Saiba mais sobre [falhas de entrega e quarentenas](../send/delivery-failures.md).

## Monitorar a capacidade de entrega {#monitor-deliverability}

A monitoração da capacidade de entrega ajuda a garantir que as mensagens cheguem às caixas de entrada dos destinatários e evite filtros de spam. O Adobe Campaign fornece várias ferramentas integradas para monitorar e melhorar a capacidade de entrega, incluindo relatórios de entrega, renderização da caixa de entrada, testes do SpamAssassin e estatísticas de transmissão. Seguir as práticas recomendadas de capacidade de entrega, como manter uma lista de email limpa, monitorar a reputação do remetente e autenticar domínios de envio, é essencial para manter boas taxas de capacidade de entrega.

Saiba mais sobre as [ferramentas de monitoramento da capacidade de entrega](../send/monitoring-deliverability.md) e as [práticas recomendadas de capacidade de entrega](../send/about-deliverability.md).

## Monitorar fluxos de trabalho {#monitor-workflows}

Os workflows são essenciais para automatizar suas campanhas de marketing e o processamento de dados. O monitoramento da execução do fluxo de trabalho ajuda a:

* Garantir que os fluxos de trabalho sejam concluídos com êxito
* Identificar e solucionar erros
* Otimizar o desempenho do fluxo de trabalho

### Recursos de monitoramento de fluxo de trabalho {#workflow-monitoring}

**Monitorar os seguintes elementos de fluxo de trabalho:**

**Status de execução do fluxo de trabalho** - Rastreie se os fluxos de trabalho estão em execução, pausados, com falha ou concluídos. [Saiba mais sobre a execução do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=pt-BR){target="_blank"}

**Logs de execução de atividade** - Acesse logs detalhados para cada atividade de fluxo de trabalho para solucionar problemas e otimizar o desempenho.

**Workflow heatmap** - Visualize os padrões de execução do fluxo de trabalho, identifique gargalos e monitore fluxos de trabalho simultâneos. O Workflow HeatMap está disponível para administradores do Campaign. [Saiba mais sobre o mapa de calor do fluxo de trabalho](https://experienceleague.adobe.com/pt-br/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}

**Histórico do fluxo de trabalho** - Rastreie todas as execuções e modificações do fluxo de trabalho ao longo do tempo para entender o comportamento e o desempenho do fluxo de trabalho.

## Monitorar sua instância {#monitor-instance}

O monitoramento de instâncias ajuda a garantir a integridade e o desempenho do ambiente do Adobe Campaign.

### Trilha de auditoria {#audit-trail}

A interface de autoatendimento da trilha de auditoria permite monitorar alterações feitas na instância do Adobe Campaign. A trilha de auditoria captura em tempo real uma lista abrangente de ações e eventos que ocorrem na sua instância.

**Usar trilha de auditoria para:**

* **Rastrear alterações em componentes**: Monitore o que aconteceu com seus fluxos de trabalho, esquemas, opções e outros componentes
* **Identifique quem fez as alterações**: veja quem atualizou um elemento específico pela última vez e quando
* **Entender as ações do usuário**: revise o que os usuários fizeram na instância para solução de problemas ou auditoria
* **Manter conformidade**: controle todas as alterações de configuração para fins de conformidade e segurança

A Trilha de auditoria pode ser acessada por meio do console do cliente do Campaign e fornece informações detalhadas sobre as ações executadas pelos usuários.

Saiba mais sobre [Trilha de auditoria](../reporting/audit-trail.md)

### Monitoramento de desempenho {#performance-monitoring}

O Campaign v8 fornece vários recursos de monitoramento para rastrear o desempenho da sua instância e garantir a operação ideal:

**Monitoramento de banco de dados** - Monitore o uso e a capacidade do banco de dados por meio do Painel de Controle para garantir desempenho e gerenciamento de armazenamento ideais. [Saiba mais sobre o monitoramento de banco de dados](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html?lang=pt-BR){target="_blank"}

**Monitoramento de perfis ativos** - Rastreie o uso do perfil ativo em relação aos limites contratuais para manter a conformidade e otimizar a alocação de recursos. [Saiba mais sobre perfis ativos](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=pt-BR){target="_blank"}

**Monitoramento do fluxo de trabalho** - Monitore o status de execução do fluxo de trabalho para identificar fluxos de trabalho de longa duração e garantir que todos os fluxos de trabalho técnicos estejam sendo executados corretamente. [Saiba mais sobre fluxos de trabalho técnicos](#technical-workflows)

**Taxa de transferência e latência de entrega** - Rastrear a taxa de transferência de entrega (mensagens enviadas por hora) e a latência de comunicações transacionais por meio do Painel de Controle. [Saiba mais sobre o monitoramento de taxa de transferência](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html?lang=pt-BR){target="_blank"}

>[!NOTE]
>
>Para o Campaign v8 Managed Cloud Services, a infraestrutura do servidor (CPU, memória, disco) é monitorada e gerenciada pela Adobe.

### Fluxos de trabalho técnicos {#technical-workflows}

Os workflows técnicos são processos essenciais executados em segundo plano para manter a instância do Campaign.

**Monitorar se os fluxos de trabalho técnicos são:**

* Execução programada
* Concluindo com êxito sem erros
* Processamento correto de dados

**Principais fluxos de trabalho técnicos a serem monitorados:**

| Fluxo de trabalho | Finalidade |
|----------|---------|
| **Rastreamento** | Processa dados de rastreamento de deliveries de email |
| **Limpeza** | Remove dados e logs antigos para manter o desempenho do banco de dados |
| **Atualização de entregabilidade** | Atualiza as regras de capacidade de entrega e os padrões de filtro de spam |
| **Limpeza do banco de dados** | Limpa logs de entrega e rastreamento antigos |

Saiba mais sobre [workflows técnicos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=pt-BR){target="_blank"}

### Painel de controle do Campaign {#control-panel}

O Painel de controle do Campaign fornece aos administradores recursos de autoatendimento para monitorar e gerenciar instâncias do Campaign.

| Tipo de monitoramento | Capacidades |
|-----------------|--------------|
| **Desempenho** | Rastrear o uso do perfil ativo, monitorar o uso e a capacidade do banco de dados, exibir o status de execução do fluxo de trabalho, monitorar a taxa de transferência e a latência da entrega |
| **Infraestrutura** | Monitorar a capacidade de armazenamento SFTP, rastrear a configuração de subdomínio, monitorar a expiração do certificado SSL, gerenciar a lista de permissões de IP |
| **Instância** | Exibir a versão de compilação e os pacotes instalados, monitorar a configuração do sistema, gerenciar domínios externos autorizados |

Saiba mais sobre o [Painel de Controle](../config/self-service.md) e o [monitoramento do desempenho do Painel de Controle](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=pt-BR){target="_blank"}

>[!NOTE]
>
>Para o Campaign v8 Managed Cloud Services, a Adobe monitora e gerencia a infraestrutura do servidor, o sistema operacional e a camada de aplicativos. Você pode usar os recursos de monitoramento descritos nesta página e no Painel de controle do Campaign para monitorar o desempenho da instância, os workflows e os deliveries.

## Rastreamento e relatórios {#tracking-reporting}

### Rastreamento de mensagens {#message-tracking}

Acompanhe o comportamento do recipient e meça a eficácia de suas campanhas:

* **Aberturas**: rastrear quando os destinatários abrem seus emails
* **Cliques**: monitorar em quais links os destinatários clicam
* **Cancelamentos de assinatura**: rastrear solicitações de recusa
* **Exibições da mirror page**: veja quantos destinatários visualizam seu email em um navegador

Saiba mais sobre o [rastreamento de mensagens](../send/tracking.md)

### Relatórios de entrega {#delivery-reports}

O Adobe Campaign fornece um conjunto abrangente de relatórios para analisar o desempenho do delivery:

* **Resumo da entrega**: visão geral de envios, entregas e falhas
* **Indicadores de rastreamento**: aberturas, cliques e taxas de click-through
* **Fluxos de clique e URLs**: links mais populares em suas entregas
* **Hot clicks**: representação visual de onde os recipients clicaram no seu email

Saiba mais sobre [relatórios de entrega](../reporting/delivery-reports.md)

### Relatórios globais {#global-reports}

Acesse relatórios globais para analisar o desempenho em todas as campanhas e deliveries:

* **Taxa de transferência de entrega**: mensagens enviadas ao longo do tempo
* **Não entregues e rejeitados**: análise de entregas com falha
* **Atividades do usuário**: aberturas, cliques e cancelamentos de assinatura em todas as campanhas

Saiba mais sobre [relatórios globais](../reporting/global-reports.md)

## Tópicos relacionados {#related-topics}

* [Práticas recomendadas de entrega](delivery-best-practices.md)
* [Gerenciamento de quarentena](../send/quarantines.md)
* [Configurar e enviar deliveries](../send/configure-and-send.md)
* [Introdução aos relatórios](../reporting/gs-reporting.md)

