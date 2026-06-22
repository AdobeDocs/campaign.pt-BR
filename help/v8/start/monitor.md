---
title: Visão geral do monitoramento de campanha
description: Saiba como monitorar deliveries, workflows e a instância do Campaign
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6cf587ecc9cc1e4cf9b3de0d2067e0c4562afe01
workflow-type: tm+mt
source-wordcount: 2206
ht-degree: 4%

---

# Visão geral do monitoramento de campanha {#monitor-campaign}

O Adobe Campaign oferece visibilidade em todos os níveis: desde a entrega de uma mensagem individual, o motivo da falha de um fluxo de trabalho até a capacidade restante do banco de dados. Esta página mapeia todos os recursos de monitoramento para que você saiba onde procurar quando algo precisa de atenção.

>[!NOTE]
>
>Como administrador do Campaign, você também pode usar o [Painel de Controle do Campaign](#control-panel) para monitorar suas instâncias, gerenciar o desempenho e definir configurações com recursos de autoatendimento.

>[!TIP]
>
>**Não tem certeza de onde começar?**
>
>- Verificação do profissional de marketing em uma campanha → [Monitorar suas entregas](#monitor-deliveries)
>- Solução de problemas de um fluxo de trabalho → [Monitorar fluxos de trabalho](#monitor-workflows)
>- Administração verificando a integridade da instância → [Monitorar sua instância](#monitor-instance)

## Monitore entregas {#monitor-deliveries}

O monitoramento de deliveries, após serem enviados, é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes. Após enviar um delivery, você poderá monitorar seu status e rastrear as métricas principais no painel do delivery. O painel fornece acesso a logs do delivery, logs de exclusão, logs de rastreamento e outros recursos de monitoramento para ajudar você a analisar o desempenho do delivery em todos os canais.

>[!NOTE]
>
>**Novo no Campaign?** O painel de delivery é sua tela principal do dia a dia. Abra qualquer entrega enviada, clique na guia **Logs** e você verá quais destinatários receberam a mensagem, quais foram excluídos e o motivo, e quem clicou ou abriu.

**Entregas de email** - Monitore o status da entrega de email, rastreie as métricas principais e acesse os logs detalhados. Saiba mais sobre o [monitoramento de entregas na interface do usuário do Campaign](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/send/monitor/delivery-dashboard), [status de entrega](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/send/monitor/delivery-statuses) e [monitoramento de entrega de email](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/emails/send#email-monitoring).

**Entregas de SMS** - Rastreie o status da entrega de SMS e monitore as métricas principais no painel de entrega de SMS. Saiba mais sobre o [monitoramento de SMS](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/sms/sms-monitor).

**Notificações por push** - Monitore entregas de notificações por push para garantir que elas cheguem aos usuários do aplicativo móvel de maneira eficaz. Saiba mais sobre o [monitoramento de notificação por push](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/push/push#push-test).

**Mensagens transacionais** - Para mensagens acionadas por eventos, monitore o status do processamento do evento, a execução da mensagem e o status da entrega. Saiba mais sobre [monitoramento de mensagens transacionais](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/real-time/event/delivery-execution#monitor-messages).

**Falhas de entrega** - Entender por que uma entrega falhou é essencial para manter um banco de dados limpo e garantir boas taxas de entrega. As falhas de delivery são classificadas em três tipos: entender a diferença ajuda a decidir que ação tomar:

| Tipo de falha | O que significa | O que a campanha faz |
| --- | --- | --- |
| **Rejeição permanente** | O endereço é inválido permanentemente (não existe, domínio desconhecido) | O contato é colocado automaticamente em quarentena — ele não será direcionado em deliveries futuros |
| **Rejeição leve** | Um problema temporário (caixa de correio cheia, servidor temporariamente indisponível) | O Campaign tenta novamente automaticamente por um período configurado |
| **Ignorado** | O endereço já estava em quarentena ou em um incluo na lista de bloqueios antes de enviar | Nenhuma tentativa é feita; contado separadamente das rejeições |

Saiba mais sobre [falhas de entrega e quarentenas](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/send/monitor/delivery-failures).

## Monitorar a capacidade de entrega {#monitor-deliverability}

>[!NOTE]
>
>Uma mensagem contada como &quot;entregue&quot; significa que foi aceita pelo servidor de recebimento — ela não garante a inserção da caixa de entrada. O monitoramento da capacidade de entrega informa se a autenticação de domínio de envio, a reputação de IP e o conteúdo de email estão cumprindo os padrões do provedor da caixa de entrada.

A monitoração da capacidade de entrega ajuda a garantir que as mensagens cheguem às caixas de entrada dos destinatários e evite filtros de spam. O Adobe Campaign fornece várias ferramentas integradas para monitorar e melhorar a capacidade de entrega, incluindo relatórios de entrega, renderização da caixa de entrada, testes do SpamAssassin e estatísticas de transmissão. Seguir as práticas recomendadas de capacidade de entrega, como manter uma lista de email limpa, monitorar a reputação do remetente e autenticar domínios de envio, é essencial para manter boas taxas de capacidade de entrega.

Saiba mais sobre as [ferramentas de monitoramento da capacidade de entrega](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/monitoring-deliverability) e as [práticas recomendadas de capacidade de entrega](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/about-deliverability).

## Monitorar fluxos de trabalho {#monitor-workflows}

Os workflows são essenciais para automatizar suas campanhas de marketing e o processamento de dados. O monitoramento da execução do fluxo de trabalho ajuda a:

- Garantir que os fluxos de trabalho sejam concluídos com êxito
- Identificar e solucionar erros
- Otimizar o desempenho do fluxo de trabalho

>[!TIP]
>
>Se um fluxo de trabalho mostrar um status de **Falha**, abra-o, clique com o botão direito do mouse na atividade vermelha e selecione **Exibir logs**. A mensagem de erro identifica exatamente o que deu errado e em qual registro.

### Recursos de monitoramento de fluxo de trabalho {#workflow-monitoring}

**Monitorar os seguintes elementos de fluxo de trabalho:**

**Status de execução do fluxo de trabalho** - Rastreie se os fluxos de trabalho estão em execução, pausados, com falha ou concluídos. [Saiba mais sobre a execução do fluxo de trabalho](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#_blank)

**Logs de execução de atividade** - Acesse logs detalhados para cada atividade de fluxo de trabalho para solucionar problemas e otimizar o desempenho.

**Workflow HeatMap** - Uma visão geral visual de todos os fluxos de trabalho que estão sendo executados simultaneamente em sua instância. Use-o para identificar períodos de carga máxima, fluxos de trabalho ocasionais que consomem recursos desproporcionados e planejar o agendamento para evitar conflitos de execução. Disponível somente para administradores do Campaign. [Saiba mais sobre o mapa de calor do fluxo de trabalho](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap#_blank)

**Histórico do fluxo de trabalho** - Rastreie todas as execuções e modificações do fluxo de trabalho ao longo do tempo para entender o comportamento e o desempenho do fluxo de trabalho.

## Monitorar sua instância {#monitor-instance}

O monitoramento de instâncias ajuda a garantir a integridade e o desempenho do ambiente do Adobe Campaign. Para o Campaign v8 Managed Cloud Services, a Adobe também monitora e gerencia a infraestrutura em seu nome. Saiba mais sobre o [monitoramento gerenciado pela Adobe](#adobe-cloud-monitoring).

### Trilha de auditoria {#audit-trail}

A interface de autoatendimento da trilha de auditoria permite monitorar alterações feitas na instância do Adobe Campaign. A trilha de auditoria captura em tempo real uma lista abrangente de ações e eventos que ocorrem na sua instância.

**Usar trilha de auditoria para:**

- **Rastrear alterações em componentes**: Monitore o que aconteceu com seus fluxos de trabalho, esquemas, opções e outros componentes
- **Identifique quem fez as alterações**: veja quem atualizou um elemento específico pela última vez e quando
- **Entender as ações do usuário**: revise o que os usuários fizeram na instância para solução de problemas ou auditoria
- **Manter conformidade**: controle todas as alterações de configuração para fins de conformidade e segurança

A Trilha de auditoria pode ser acessada por meio do console do cliente do Campaign e fornece informações detalhadas sobre as ações executadas pelos usuários.

Saiba mais sobre [Trilha de auditoria](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/audit-trail)

### Monitoramento de desempenho {#performance-monitoring}

O Campaign v8 fornece vários recursos de monitoramento para rastrear o desempenho da sua instância e garantir a operação ideal:

**Monitoramento de banco de dados** - Monitore o uso e a capacidade do banco de dados por meio do Painel de Controle para garantir desempenho e gerenciamento de armazenamento ideais. [Saiba mais sobre o monitoramento de banco de dados](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring#_blank)

**Monitoramento de perfis ativos** - Rastreie o uso do perfil ativo em relação aos limites contratuais para manter a conformidade e otimizar a alocação de recursos. [Saiba mais sobre perfis ativos](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/active-profiles-monitoring#_blank)

**Monitoramento do fluxo de trabalho** - Monitore o status de execução do fluxo de trabalho para identificar fluxos de trabalho de longa duração e garantir que todos os fluxos de trabalho técnicos estejam sendo executados corretamente. [Saiba mais sobre fluxos de trabalho técnicos](#technical-workflows)

**Taxa de transferência e latência de entrega** - Rastrear a taxa de transferência de entrega (mensagens enviadas por hora) e a latência de comunicações transacionais por meio do Painel de Controle. [Saiba mais sobre o monitoramento de taxa de transferência](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/throughputs-latencies#_blank)

>[!NOTE]
>
>Para o Campaign v8 Managed Cloud Services, a infraestrutura do servidor (CPU, memória, disco) é monitorada e gerenciada pela Adobe. Saiba mais sobre o [monitoramento gerenciado pela Adobe](#adobe-cloud-monitoring).

### Monitoramento gerenciado pela Adobe {#adobe-cloud-monitoring}

Os serviços em nuvem da Adobe Campaign oferecem suporte essencial para as necessidades exigentes de entrega da experiência do cliente por meio de infraestruturas em nuvem flexíveis. Isso permite que as organizações iniciem, monitorem e otimizem as experiências do cliente sem a necessidade de gerenciar ou operar a infraestrutura do Campaign.

O Adobe monitora os ambientes do Campaign Cloud Services para ajudar a gerenciar vários problemas e minimizar interrupções detectando problemas técnicos e fornecendo feedback contínuo sobre desempenho e projetos em andamento.

**Como a Adobe responde**

O Adobe monitora todos os equipamentos de rede críticos na rede do Campaign 24 horas por dia, 7 dias por semana e recebe notificações dos sistemas de monitoramento quando correções ou escalonamentos são necessários. Ao detectar um problema, o sistema usa mecanismos de reinicialização automática e inicialização automática para tentar corrigir o problema. Se o sistema não corrigir automaticamente, o Adobe On-Call Engineering intervém para executar a solução de problemas com base em runbooks de alerta predefinidos.

>[!NOTE]
>
>Algumas ações de monitoramento executadas pela Adobe aparecem nos logs do Campaign sob o usuário **campaign-loginmonitor**.

Além do monitoramento interno da Adobe, você pode acessar recursos de monitoramento diretamente pelo console do cliente do Campaign ou pelo [Painel de Controle do Campaign](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service). Com o Painel de controle do Campaign, você pode assinar alertas em tempo real sobre suas instâncias e receber etapas de correção recomendadas para incidentes identificados (por exemplo, certificados SSL próximos à expiração).

**Taxonomia de monitoramento**

A Adobe monitora seu ambiente em três níveis:

| Nível | Grupo | Possível impacto nos negócios |
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
>O Adobe Campaign Cloud Services é fundamentado em uma estratégia de várias nuvens e oferece implantações no AWS e no Azure. Devido às diferenças do fornecedor, os recursos de monitoramento diferem entre a AWS, a Azure e outras implantações de data center. A tabela acima se aplica aos clientes do Campaign Cloud Services hospedados no AWS, a menos que declarado o contrário. Observe também que a Adobe Campaign não expõe atualmente todos os dados de monitoramento usados pela engenharia em chamada para os clientes.

### Fluxos de trabalho técnicos {#technical-workflows}

Os workflows técnicos são processos essenciais executados em segundo plano para manter a instância do Campaign.

**Monitorar se os fluxos de trabalho técnicos são:**

- Execução programada
- Concluindo com êxito sem erros
- Processamento correto de dados

**Principais fluxos de trabalho técnicos a serem monitorados:**

| Fluxo de trabalho | Finalidade | Se falhar |
| --- | --- | --- |
| **Rastreamento** | Processa dados de rastreamento de deliveries de email | Clicar e abrir métricas parar atualização em relatórios |
| **Limpeza** | Remove dados e logs antigos para manter o desempenho do banco de dados | O banco de dados cresce desmarcado, prejudicando o desempenho da consulta e do delivery |
| **Atualização de entregabilidade** | Atualiza as regras de capacidade de entrega e os padrões de filtro de spam | As regras se tornam obsoletas; a precisão da filtragem pode degradar |
| **Limpeza do banco de dados** | Limpa logs de entrega e rastreamento antigos | O acúmulo de logs torna as consultas e os relatórios mais lentos ao longo do tempo |

Saiba mais sobre [workflows técnicos](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows#_blank)

### Painel de controle do Campaign {#control-panel}

O Painel de controle do Campaign fornece aos administradores recursos de autoatendimento para monitorar e gerenciar instâncias do Campaign.

| Tipo de monitoramento | Capacidades |
| --- | --- |
| **Desempenho** | Rastrear o uso do perfil ativo, monitorar o uso e a capacidade do banco de dados, exibir o status de execução do fluxo de trabalho, monitorar a taxa de transferência e a latência da entrega |
| **Infraestrutura** | Monitorar a capacidade de armazenamento SFTP, rastrear a configuração de subdomínio, monitorar a expiração do certificado SSL, gerenciar a lista de permissões de IP |
| **Instância** | Exibir a versão de compilação e os pacotes instalados, monitorar a configuração do sistema, gerenciar domínios externos autorizados |

Saiba mais sobre o [Painel de Controle](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service) e o [monitoramento do desempenho do Painel de Controle](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring#_blank)

>[!NOTE]
>
>Para o Campaign v8 Managed Cloud Services, a Adobe monitora e gerencia a infraestrutura do servidor, o sistema operacional e a camada de aplicativos. Saiba mais sobre o [monitoramento gerenciado pela Adobe](#adobe-cloud-monitoring). Você pode usar os recursos de monitoramento descritos nesta página e no Painel de controle do Campaign para monitorar o desempenho da instância, os workflows e os deliveries.

## Rastreamento e relatórios {#tracking-reporting}

### Rastreamento de mensagens {#message-tracking}

Acompanhe o comportamento do recipient e meça a eficácia de suas campanhas:

- **Aberturas**: rastrear quando os destinatários abrem seus emails
- **Cliques**: monitorar em quais links os destinatários clicam
- **Cancelamentos de assinatura**: rastrear solicitações de recusa
- **Exibições da mirror page**: veja quantos destinatários visualizam seu email em um navegador

Saiba mais sobre o [rastreamento de mensagens](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/analytics/tracking/tracking)

### Relatórios de entrega {#delivery-reports}

O Adobe Campaign fornece um conjunto abrangente de relatórios para analisar o desempenho do delivery:

- **Resumo da entrega**: visão geral de envios, entregas e falhas
- **Indicadores de rastreamento**: aberturas, cliques e taxas de click-through
- **Fluxos de clique e URLs**: links mais populares em suas entregas
- **Hot clicks**: representação visual de onde os recipients clicaram no seu email

Saiba mais sobre [relatórios de entrega](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/delivery-reports)

### Relatórios globais {#global-reports}

Acesse relatórios globais para analisar o desempenho em todas as campanhas e deliveries:

- **Taxa de transferência de entrega**: mensagens enviadas ao longo do tempo
- **Não entregues e rejeitados**: análise de entregas com falha
- **Atividades do usuário**: aberturas, cliques e cancelamentos de assinatura em todas as campanhas

Saiba mais sobre [relatórios globais](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/global-reports)

## Tópicos relacionados {#related-topics}

- [Práticas recomendadas de entrega](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/send/delivery-best-practices)
- [Gerenciamento de quarentena](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/send/monitor/quarantines)
- [Configurar e enviar deliveries](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/validate/configure-and-send)
- [Introdução aos relatórios](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/gs-reporting)
