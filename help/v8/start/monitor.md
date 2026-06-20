---
title: Visão geral do monitoramento de campanha
description: Saiba como monitorar deliveries, workflows e a instância do Campaign
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: e8438b85eec144e83b2660f9d66444c1a01863ab
workflow-type: tm+mt
source-wordcount: 2101
ht-degree: 4%

---

# Visão geral do monitoramento de campanha {#monitor-campaign}

O Adobe Campaign oferece visibilidade em todos os níveis: desde a entrega de uma mensagem individual, o motivo da falha de um fluxo de trabalho até a capacidade restante do banco de dados. Esta página mapeia todos os recursos de monitoramento para que você saiba onde procurar quando algo precisa de atenção. Como administrador do Campaign, você também pode usar o [Painel de Controle do Campaign](#control-panel) para monitorar suas instâncias, gerenciar o desempenho e definir configurações com recursos de autoatendimento.

>[!TIP]
>
>**Não tem certeza de onde começar?**
>
>- Verificação do profissional de marketing em uma campanha → [Monitorar suas entregas](#monitor-deliveries)
>- Solução de problemas de um fluxo de trabalho → [Monitorar fluxos de trabalho](#monitor-workflows)
>- Administração verificando a integridade da instância → [Monitorar sua instância](#monitor-instance)

## Monitore entregas {#monitor-deliveries}

O monitoramento de deliveries, após serem enviados, é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes. Após enviar um delivery, você poderá rastrear seu progresso e diagnosticar problemas no painel de delivery. O painel fornece acesso a logs do delivery, logs de exclusão, logs de rastreamento e outros dados para cada canal usado.

>[!NOTE]
>
>**Novo no Campaign?** O painel de delivery é sua tela principal do dia a dia. Abra qualquer entrega enviada, clique na guia **Logs** e você verá quais destinatários receberam a mensagem, quais foram excluídos e o motivo, e quem clicou ou abriu.

**Entregas de email** — Monitore o status da entrega de email, rastreie as métricas principais e acesse os logs detalhados. Saiba mais sobre o [monitoramento de entregas na interface do usuário do Campaign](../send/delivery-dashboard.md), [status de entrega](../send/delivery-statuses.md) e [monitoramento de entrega de email](../send/send.md#email-monitoring).

**Entregas de SMS** — Rastreie o status da entrega de SMS e monitore as métricas principais no painel de entrega de SMS. Saiba mais sobre o [monitoramento de SMS](../send/sms/sms-monitor.md).

**Notificações por push** — Monitore entregas de notificações por push para garantir que elas cheguem aos usuários do aplicativo móvel de maneira eficaz. Saiba mais sobre o [monitoramento de notificação por push](../send/push.md#push-test).

**Mensagens transacionais** — Para mensagens acionadas por eventos, monitore o status de processamento do evento, a profundidade da fila e os resultados da execução. Saiba mais sobre [monitoramento de mensagens transacionais](../send/delivery-execution.md#monitor-messages).

**Falhas de entrega** — Entender por que uma entrega falhou é essencial para manter um banco de dados limpo e garantir boas taxas de entrega. As falhas de delivery são classificadas em três tipos: entender a diferença ajuda a decidir que ação tomar:

| Tipo de falha | O que significa | O que a campanha faz |
| --- | --- | --- |
| **Rejeição permanente** | O endereço é inválido permanentemente (não existe, domínio desconhecido) | O contato é colocado automaticamente em quarentena — ele não será direcionado em deliveries futuros |
| **Rejeição leve** | Um problema temporário (caixa de correio cheia, servidor temporariamente indisponível) | O Campaign tenta novamente automaticamente por um período configurado |
| **Ignorado** | O endereço já estava em quarentena ou em um incluo na lista de bloqueios antes de enviar | Nenhuma tentativa é feita; contado separadamente das rejeições |

Saiba mais sobre [falhas de entrega e quarentenas](../send/delivery-failures.md).

## Monitorar a capacidade de entrega {#monitor-deliverability}

A capacidade de entrega é a medida do sucesso com que suas mensagens chegam às caixas de entrada dos destinatários, em vez de serem filtradas para spam ou rejeitadas. O Adobe Campaign fornece várias ferramentas integradas para ajudar você a entender e melhorar as taxas de posicionamento da caixa de entrada.

>[!NOTE]
>
>Uma mensagem contada como &quot;entregue&quot; significa que foi aceita pelo servidor de recebimento — ela não garante a inserção da caixa de entrada. O monitoramento da capacidade de entrega informa se a autenticação de domínio de envio, a reputação de IP e o conteúdo de email estão cumprindo os padrões do provedor da caixa de entrada.

O Adobe Campaign fornece as seguintes ferramentas integradas de entrega:

- **Relatórios de entrega** — Relatórios internos que mostram o volume de envio, as taxas de rejeição e as cancelamentos de assinatura ao longo do tempo.
- **Renderização da caixa de entrada** — Visualize como seu email aparece nos principais clientes (Gmail, Outlook, Apple Mail) antes ou depois do envio.
- **Teste do SpamAssassin** — Pontue seu conteúdo de email com as regras comuns de filtro de spam para capturar problemas antes da entrega.
- **Estatísticas de transmissão** — Agregue dados de entrega entre os volumes de envio e a reputação do IP.

Seguir as práticas recomendadas de capacidade de entrega — como manter uma lista de email limpa, monitorar a reputação do remetente e autenticar domínios de envio — é essencial para manter boas taxas de capacidade de entrega.

Saiba mais sobre as [ferramentas de monitoramento da capacidade de entrega](../send/monitoring-deliverability.md) e as [práticas recomendadas de capacidade de entrega](../send/about-deliverability.md).

## Monitorar fluxos de trabalho {#monitor-workflows}

Os workflows são o mecanismo por trás de suas automações de marketing e processamento de dados. A monitoração garante que as atividades programadas sejam concluídas conforme esperado e que os erros sejam capturados antes que afetem os deliveries ou a qualidade dos dados.

>[!TIP]
>
>Se um fluxo de trabalho mostrar um status de **Falha**, abra-o, clique com o botão direito do mouse na atividade vermelha e selecione **Exibir logs**. A mensagem de erro identifica exatamente o que deu errado e em qual registro.

### Recursos de monitoramento de fluxo de trabalho {#workflow-monitoring}

**Monitorar os seguintes elementos de fluxo de trabalho:**

**Status de execução do fluxo de trabalho** — Rastreie se os fluxos de trabalho estão em execução, pausados, com falha ou concluídos. Acesso rápido a workflows paralisados ou de longa duração. [Saiba mais sobre a execução do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=pt-BR){target="_blank"}

**Logs de execução de atividade** — Analise os logs por atividade para entender o que aconteceu em cada etapa — útil para solucionar problemas de transições com falha ou saídas de dados inesperadas.

**Workflow HeatMap** — uma visão geral visual de todos os fluxos de trabalho que estão sendo executados simultaneamente em sua instância. Use-o para identificar períodos de carga máxima, fluxos de trabalho ocasionais que consomem recursos desproporcionados e planejar o agendamento para evitar conflitos de execução. Disponível somente para administradores do Campaign. [Saiba mais sobre o mapa de calor do fluxo de trabalho](https://experienceleague.adobe.com/pt-br/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}

**Histórico do fluxo de trabalho** — Rastreie todas as execuções e modificações do fluxo de trabalho ao longo do tempo para entender o comportamento do fluxo de trabalho e os padrões de desempenho.

## Monitorar sua instância {#monitor-instance}

O monitoramento de instâncias abrange a integridade do ambiente do Campaign — capacidade do banco de dados, uso do perfil, throughput e infraestrutura. Para o Campaign v8 Managed Cloud Services, a Adobe monitora e gerencia a infraestrutura subjacente em seu nome, mas você mantém total visibilidade por meio do console do cliente e do Painel de controle. Saiba mais sobre o [monitoramento gerenciado pela Adobe](#adobe-cloud-monitoring).

### Trilha de auditoria {#audit-trail}

A interface de autoatendimento da trilha de auditoria permite monitorar cada alteração significativa feita na instância do Adobe Campaign. A trilha de auditoria captura em tempo real uma lista abrangente de ações e eventos que ocorrem na sua instância.

**Usar trilha de auditoria para:**

- **Rastrear alterações de componentes** — Monitore o que aconteceu com seus fluxos de trabalho, esquemas, opções e outros componentes
- **Identifique quem fez uma alteração** — Veja qual usuário modificou um elemento pela última vez e em que momento
- **Solução de problemas de comportamento inesperado** — Rastreie através das ações do usuário para descobrir quando e como um problema foi introduzido
- **Conformidade de suporte e auditorias** — mantenha um registro completo e inviolável de todas as alterações de configuração

A Trilha de auditoria pode ser acessada por meio do console do cliente do Campaign e fornece informações detalhadas sobre as ações executadas pelos usuários.

Saiba mais sobre [Trilha de auditoria](../reporting/audit-trail.md)

### Monitoramento de desempenho {#performance-monitoring}

O Campaign v8 fornece vários recursos de monitoramento para rastrear o desempenho da sua instância e garantir a operação ideal:

**Monitoramento de banco de dados** — Monitore o uso e a capacidade do banco de dados por meio do Painel de Controle para garantir desempenho e gerenciamento de armazenamento ideais. [Saiba mais sobre o monitoramento de banco de dados](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**Monitoramento de perfis ativos** — Rastreie o uso do perfil ativo em relação aos limites contratuais para manter a conformidade e otimizar a alocação de recursos. [Saiba mais sobre perfis ativos](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=pt-BR){target="_blank"}

**Monitoramento do fluxo de trabalho** — Monitore o status de execução do fluxo de trabalho para identificar fluxos de trabalho de longa duração e garantir que todos os fluxos de trabalho técnicos estejam sendo executados corretamente. [Saiba mais sobre fluxos de trabalho técnicos](#technical-workflows)

**Taxa de transferência e latência de entrega** — Rastreie a taxa de transferência de entrega (mensagens enviadas por hora) e a latência de comunicações transacionais por meio do Painel de Controle. [Saiba mais sobre o monitoramento de taxa de transferência](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>Para o Campaign v8 Managed Cloud Services, a infraestrutura do servidor (CPU, memória, disco) é monitorada e gerenciada pela Adobe. Os recursos de monitoramento descritos nesta página e no Painel de controle do Campaign são complementares — oferecem visibilidade de seus dados e configuração sem a necessidade de acesso à infraestrutura. Algumas ações realizadas pela Adobe aparecem nos logs do Campaign sob o usuário **campaign-loginmonitor**. Saiba mais sobre o [monitoramento gerenciado pela Adobe](#adobe-cloud-monitoring).

### Monitoramento gerenciado pela Adobe {#adobe-cloud-monitoring}

Os serviços em nuvem da Adobe Campaign oferecem suporte essencial para as necessidades exigentes de entrega da experiência do cliente por meio de infraestruturas em nuvem flexíveis. Isso permite que as organizações iniciem, monitorem e otimizem as experiências do cliente sem gerenciar ou operar a infraestrutura do Campaign.

O Adobe monitora os ambientes do Campaign Cloud Services 24 horas por dia, 7 dias por semana, para detectar problemas técnicos e minimizar interrupções. Ao detectar um problema, o sistema usa mecanismos de reinicialização automática e inicialização automática para tentar corrigir o problema. Se o sistema não corrigir automaticamente, a engenharia do Adobe On-Call intervém com base em runbooks de alerta predefinidos.

>[!TIP]
>
>Você pode assinar alertas de instância em tempo real por meio do [Painel de Controle do Campaign](#control-panel) e receber etapas de correção recomendadas para problemas detectados — por exemplo, certificados SSL próximos à expiração.

**Níveis de monitoramento**

A Adobe monitora seu ambiente em três níveis. Problemas de nível 1 têm o maior impacto e recebem a resposta mais rápida:

| Nível | Grupo | O que você pode experimentar |
| --- | --- | --- |
| **Nível 1: Infraestrutura** | Esgotamento do espaço do banco de dados | Problemas de desempenho, incluindo incapacidade de fazer logon, executar entregas em lote ou executar consultas |
| **Nível 1: Infraestrutura** | Disponibilidade do banco de dados | Usuários e serviços podem não conseguir usar o sistema |
| **Nível 1: Infraestrutura** | Sobrecarga do banco de dados (equilíbrio de intermitência) | Problemas de desempenho, incluindo incapacidade de fazer logon, executar entregas em lote ou executar consultas |
| **Nível 1: Infraestrutura** | Esgotamento da sequência do banco de dados e da ID de transação | Não é possível criar novos workflows, deliveries ou enviar emails em lote |
| **Nível 1: Infraestrutura** | Armazenamento SFTP | Não é possível atualizar ou recuperar dados em servidores SFTP |
| **Camada 2: Plataforma e Web** | Fazer logon | Os usuários podem não conseguir fazer logon; atividades e fluxos de trabalho agendados podem não ser executados |
| **Camada 2: Plataforma e Web** | Bloqueio de API | Usuários ou serviços podem não conseguir autenticar ou executar operações |
| **Camada 2: Plataforma e Web** | Web | Não foi possível criar novas conexões com o Campaign |
| **Camada 2: Plataforma e Web** | Rede de data center | Problemas de desempenho ou indisponibilidade completa para usuários no data center |
| **Nível 3: Software** | Rastreamento de entrega | O processamento de logs de rastreamento não está disponível |
| **Nível 3: Software** | inMail | Nenhum feedback sobre erros e rejeições de deliveries de email |
| **Nível 3: Software** | Status do Centro de mensagens | Não é possível enviar deliveries transacionais |
| **Nível 3: Software** | MTA | Não é possível enviar deliveries de email programados e ad-hoc |
| **Nível 3: Software** | Status do servidor de fluxo de trabalho | Não é possível executar workflows |
| **Nível 3: Software** | Disponibilidade da API da Web | Não é possível processar solicitações HTTP ou executar chamadas de API |
| **Nível 3: Software** | Interações de entrada | Não é possível processar interações de entrada |

>[!NOTE]
>
>O Adobe Campaign Cloud Services é fundamentado em uma estratégia de várias nuvens com implantações no AWS e no Azure. Os recursos de monitoramento diferem entre a AWS, a Azure e outras implantações de data center. A tabela acima se aplica aos clientes do Campaign Cloud Services hospedados no AWS, a menos que declarado o contrário. Atualmente, a Adobe Campaign não expõe todos os dados de monitoramento usados pela engenharia em chamada para os clientes.

### Fluxos de trabalho técnicos {#technical-workflows}

Os workflows técnicos são executados silenciosamente em segundo plano para manter a instância do Campaign. Eles não são criados por usuários — são enviados com o produto. Se um workflow técnico falhar, ele poderá afetar diretamente os deliveries e a qualidade dos dados.

Verifique se cada workflow técnico está sendo executado de acordo com a programação, sendo concluído sem erros e processando os dados corretamente.

| Fluxo de trabalho | Finalidade | Se falhar |
| --- | --- | --- |
| **Rastreamento** | Processa dados de rastreamento de deliveries de email | Clicar e abrir métricas parar atualização em relatórios |
| **Limpeza** | Remove dados e logs antigos para manter o desempenho do banco de dados | O banco de dados cresce desmarcado, prejudicando o desempenho da consulta e do delivery |
| **Atualização de entregabilidade** | Atualiza as regras de capacidade de entrega e os padrões de filtro de spam | As regras se tornam obsoletas; a precisão da filtragem pode degradar |
| **Limpeza do banco de dados** | Limpa logs de entrega e rastreamento antigos | O acúmulo de logs torna as consultas e os relatórios mais lentos ao longo do tempo |

Saiba mais sobre [workflows técnicos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

### Painel de controle do Campaign {#control-panel}

O Painel de controle do Campaign fornece aos administradores recursos de autoatendimento para monitorar e gerenciar instâncias do Campaign, sem exigir um tíquete de suporte.

| Tipo de monitoramento | Capacidades |
| --- | --- |
| **Desempenho** | Uso do perfil ativo vs. limite de contrato, uso e capacidade do banco de dados, status de execução do fluxo de trabalho, taxa de transferência e latência da entrega |
| **Infraestrutura** | Capacidade de armazenamento SFTP, configuração de subdomínio, alertas de expiração de certificado SSL, lista de permissões de IP |
| **Instância** | Criar pacotes de versão e instalados, visão geral da configuração do sistema, domínios externos autorizados |

Saiba mais sobre o [Painel de Controle](../config/self-service.md) e o [monitoramento do desempenho do Painel de Controle](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=pt-BR){target="_blank"}

>[!NOTE]
>
>Para o Campaign v8 Managed Cloud Services, a Adobe monitora e gerencia a infraestrutura do servidor, o sistema operacional e a camada de aplicativos. Os recursos de monitoramento descritos nesta página e no Painel de controle do Campaign são complementares, pois fornecem visibilidade de seus dados e configuração sem a necessidade de acesso à infraestrutura.

## Rastreamento e relatórios {#tracking-reporting}

### Rastreamento de mensagens {#message-tracking}

O rastreamento registra como os recipients interagem com suas mensagens após o delivery. Todos os eventos rastreados são armazenados em logs de rastreamento e exibidos em relatórios do delivery.

- **Aberturas** — Gravado quando o pixel de rastreamento é carregado (somente email)
- **Cliques** — Gravado para cada link rastreado na mensagem
- **Cancelar assinatura** — Solicitações de recusa por meio do link de cancelamento de assinatura
- **Exibições da mirror page** — destinatários que visualizaram o email em um navegador

Saiba mais sobre o [rastreamento de mensagens](../send/tracking.md)

### Relatórios de entrega {#delivery-reports}

O Adobe Campaign fornece um conjunto abrangente de relatórios para analisar o desempenho do delivery:

- **Resumo da entrega** — Visão geral de envios, entregas e falhas de uma única entrega
- **Indicadores de rastreamento** — aberturas, cliques e taxas de click-through com tendência ao longo do tempo
- **URLs e fluxos de cliques** — Classificação dos links mais clicados, com contagens e porcentagens
- **Hot clicks** — Sobreposição visual mostrando onde os recipients clicaram no corpo do email

Saiba mais sobre [relatórios de entrega](../reporting/delivery-reports.md)

### Relatórios globais {#global-reports}

Acesse relatórios globais para analisar o desempenho em todas as campanhas e deliveries:

- **Taxa de transferência de entrega** — Mensagens enviadas por hora em todas as entregas em um período
- **Não entregues e rejeitados** — Detalhamento de entregas com falha por tipo e motivo de falha
- **Atividades do usuário** — abre, clica e cancela assinaturas agregadas em todas as campanhas

Saiba mais sobre [relatórios globais](../reporting/global-reports.md)

## Tópicos relacionados {#related-topics}

- [Práticas recomendadas de entrega](delivery-best-practices.md)
- [Gerenciamento de quarentena](../send/quarantines.md)
- [Configurar e enviar deliveries](../send/configure-and-send.md)
- [Introdução aos relatórios](../reporting/gs-reporting.md)
