---
title: Perguntas frequentes sobre o Campaign v8
description: Obtenha respostas para perguntas comuns do Adobe Campaign v8 sobre instalação, configuração, mensagens, fluxos de trabalho e muito mais
feature: Overview
role: User
level: Beginner
keywords: Perguntas frequentes, Campaign v8, perguntas, respostas, ajuda, suporte, solução de problemas
version: Campaign v8
hide: true
hidefromtoc: true
source-git-commit: d40eacaeeea07472ae9f110d6fca2a5986a4d208
workflow-type: tm+mt
source-wordcount: '9900'
ht-degree: 12%

---

# Perguntas frequentes {#faq}

Obtenha respostas rápidas para as perguntas mais comuns sobre o Adobe Campaign v8. Esteja você apenas começando ou procurando ajuda de configuração avançada, você encontrará respostas organizadas por tópico abaixo.

**Novo no Campaign?** Comece com [Perguntas Gerais](#general) e [Conceitos-Chave](#key-concepts).\
**Precisa de ajuda com as versões?** Verifique [Atualizações](#upgrades) para obter informações de versão e processos de atualização.\
**Migrando do v7 ou do Standard?** Consulte [Campaign v8 vs Versões Anteriores](#v7-differences) para obter diretrizes sobre diferenças e transição.\
**Precisa de ajuda técnica?** Verifique [Desenvolvedores](#developers) e [Configurações do Campaign](#settings).\
**Não encontrou sua resposta?** Visite nossos [Fóruns da Comunidade](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} ou [contate o suporte](#get-help).

**Dica:** Use Ctrl+F (Cmd+F no Mac) para procurar palavras-chave específicas nesta página. Clique em qualquer pergunta para expandir a resposta.


## Perguntas gerais {#general}

Obtenha respostas para as perguntas mais comuns sobre o Adobe Campaign v8, incluindo como se conectar, começar e acessar o suporte.

+++ Como posso me conectar ao Campaign v8?

Você precisa baixar e instalar o console do cliente do Campaign para se conectar ao Adobe Campaign. [Saiba mais](connect.md).

A partir da versão v8.6 do Campaign, você terá acesso à **interface de usuário da Web do Campaign**, disponível por meio do ambiente central do Adobe Experience Cloud. O Experience Cloud é a família integrada de aplicativos de marketing digital, produtos e serviços da Adobe.

Saiba como se conectar ao Adobe Experience Cloud e acessar a interface da Web do Adobe Campaign [nesta página](campaign-ui.md#ac-web-ui). Saiba mais na [documentação da interface do Adobe Campaign Web](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Tópicos relacionados:**

[Instalar o console do cliente](connect.md) | [Interface de usuário do Campaign](campaign-ui.md) | [Permissões de usuário](gs-permissions.md)

+++

+++ Como configurar a capacidade de entrega de emails?

A capacidade de entrega de email, um componente crítico para o sucesso do programa de marketing dos remetentes, é caracterizada por critérios e regras em constante mudança. Navegar efetivamente neste mundo digital requer o ajuste regular de sua estratégia de email, considerando as principais tendências de capacidade de entrega, para melhor alcançar seus públicos-alvo.

Consulte este manual para saber mais sobre [Práticas recomendadas de capacidade de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR){target="_blank"}

Consulte [este guia](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=pt-BR){target="_blank"} para saber como implementar a capacidade de entrega no Campaign

**Tópicos relacionados:**

[Introdução à capacidade de entrega](../send/about-deliverability.md) | [Controlar conteúdo da mensagem](../send/control-message-content.md) | [Monitorar a capacidade de entrega](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ Como posso garantir que minha entrega seja enviada sem erros?

**Antes de enviar:** Execute a análise de entrega, envie provas de teste, revise avisos e verifique a contagem de destino.

**Durante/após o envio:** Monitore o painel de entrega (enviado, entregue, devoluções, erros), verifique os logs de entrega, rastreie as taxas de sucesso/rejeição e revise os endereços em quarentena.

**Práticas recomendadas:** configure alertas, use ondas para volumes grandes, teste primeiro com volumes pequenos, limpe regularmente o banco de dados do destinatário e monitore a reputação do remetente.

**Tópicos relacionados:**

[Monitorar entregas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=pt-BR){target="_blank"} | [Práticas recomendadas de entrega](delivery-best-practices.md)

+++

+++ Posso monitorar a execução do fluxo de trabalho?

Sim. O Campaign fornece várias ferramentas de monitoramento: painel de fluxo de trabalho (status e erros em tempo real), logs de fluxo de trabalho (logs de execução detalhados), heatmap (visualizar atividade e gargalos), trilha de auditoria (rastrear modificações) e alertas (notificações de falhas).

Para monitorar, abra o workflow e clique na guia **Logs**. As atividades com falha aparecem em vermelho.

**Tópicos relacionados:**

[Monitorar a execução do fluxo de trabalho](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} | [Práticas recomendadas de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso baixar o Campaign?

Você pode obter o programa de instalação e o console do cliente do Centro de download da Adobe.

Como um usuário administrador, acesse Adobe [Distribuição de software](https://experience.adobe.com/#/downloads/content/software-distribution/br/campaign.html){target="_blank"} para baixar o Adobe Campaign.

Saiba mais sobre o Centro de Distribuição [nesta página](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=pt-BR){target="_blank"}.

+++

+++ Qual é o procedimento para delegação de domínio?

Um subdomínio é uma divisão do seu domínio que pode ser usada para isolar suas marcas ou vários tipos de tráfego (mensagens transacionais, informações de marketing etc.).

>[!NOTE]
>
>Como usuário do Managed Cloud Services, entre em contato para delegar seus subdomínios à Adobe.

+++

+++ Como posso registrar um problema?

Para contatar o Suporte ao Cliente da Adobe, conecte-se ao [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"} para criar um caso ou iniciar uma sessão de chat.

Exige contas individuais com as permissões corretas. Se não conseguir fazer logon, solicite acesso via Experience League. [Saiba mais](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Como alternativa, participe da [Comunidade do Campaign](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} para procurar respostas ou perguntar a especialistas.

+++

+++ Com quais sistemas e componentes o Campaign v8 é compatível?

Você pode obter a lista de todos os sistemas e componentes compatíveis com a última build do Campaign na [Matriz de compatibilidade do Adobe Campaign &#x200B;](compatibility-matrix.md).

+++

+++ Posso usar o Campaign v8 com outras soluções da Adobe?

Sim. O Campaign v8 integra-se perfeitamente às soluções da Adobe Experience Cloud para um ecossistema de marketing unificado.

**Integrações principais:** Adobe Experience Platform (perfis unificados, dados em tempo real), Adobe Analytics (medição de desempenho), Adobe Target (personalização), Adobe Experience Manager (gerenciamento de conteúdo), Adobe Audience Manager (segmentos de público-alvo).

**Configuração:** exige autenticação do Adobe IMS, configurada automaticamente para o Campaign v8 Managed Cloud Services.

**Tópicos relacionados:**

[Integrações do Adobe Campaign](../connect/integration.md) | [Conectar-se ao Adobe ID](connect.md)

+++

+++ Quais são as limitações do Campaign v8?

O Campaign v8 traz melhorias significativas de desempenho, mas tem algumas diferenças arquitetônicas em relação ao Campaign Classic v7, especialmente em implantações FFDA.

**Principais considerações:**

* **Arquitetura FFDA** - usa o banco de dados em nuvem (Snowflake) com diferentes padrões de acesso a dados
* **Atualizações de dados** - Deve ser feito em fluxos de trabalho, não via acesso direto ao banco de dados
* **Otimizado para lote** - Otimizado para operações em lote em vez de atualizações individuais de alta frequência
* **Não disponível no FFDA** - Pesquisas, Gestão de Recursos de Marketing (MRM), alguns conectores específicos

**Impacto na migração:** O código personalizado usando gravações diretas no banco de dados precisa ser refatorado; as integrações de API podem precisar de adaptação para o processamento em lote.

Essas limitações estão evoluindo à medida que a Adobe aprimora o v8. Consulte a documentação mais recente para conhecer o status atual.

**Tópicos relacionados:**

[Migração do Campaign v7 para v8](../start/v7-to-v8.md#limitations) | [Arquitetura FFDA](../architecture/enterprise-deployment.md)

+++

+++ Como usuário do Campaign Classic v7, posso migrar para o Campaign v8?

A migração automatizada de um ambiente do Campaign Classic v7 ainda não está disponível.

O Campaign v8 está disponível **somente** como um Managed Cloud Service e não pode ser implantado em ambientes locais ou híbridos.

Para obter mais informações sobre o processo de migração, entre em contato com o representante da Adobe.

Saiba mais na seção [Campaign v8 versus versões anteriores](#v7-differences).

+++


## Principais conceitos {#key-concepts}

Saiba mais sobre os conceitos fundamentais do Campaign, incluindo autenticação, interface do usuário, fluxos de trabalho e funcionalidades principais para começar de forma eficaz.

+++ Posso me conectar ao Campaign v8 com uma Adobe ID?

Sim! Graças à integração com o IMS (Adobe Identity Management System), os usuários se conectam ao console do Adobe Campaign usando sua Adobe ID. Essa integração oferece as seguintes vantagens:

* A mesma ID pode ser usada para todas as soluções Experience Cloud.
* Ao usar o Adobe Campaign com diferentes integrações, a conexão é memorizada.
* Política de gerenciamento da segurança de senhas.
* Uso de contas de Federated ID (provedor de ID externo).

[Saiba mais](connect.md) sobre como acessar o Campaign v8 com uma Adobe ID.

+++

+++ Como posso configurar as permissões do usuário?

Como administrador do Campaign, você pode configurar permissões para os usuários da sua organização.

Veja um conjunto de direitos e restrições que autorizam ou impedem:

* Acesso a determinadas funcionalidades
* Acessar certos dados
* Criar, modificar e/ou excluir dados

**Tópicos relacionados:**

[Introdução a permissões](gs-permissions.md) | [Gerenciar permissões de usuário](manage-permissions.md) | [Adicionar permissões em pastas](folder-permissions.md)

+++

+++ Quais conceitos da interface do usuário do Campaign eu devo conhecer?

Consulte [esta seção](campaign-ui.md) para saber mais sobre as noções básicas da interface de usuário do Adobe Campaign.

A partir da versão v8.6 do Campaign, você também terá acesso à nova **interface de usuário da Web do Campaign**, disponível por meio do ambiente central do Adobe Experience Cloud.

[Saiba mais na documentação sobre a interface de usuário da Web do Adobe Campaign](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Como posso selecionar o público-alvo de minhas mensagens?

O Campaign oferece vários métodos de direcionamento para selecionar o público certo para suas mensagens:

**Métodos de direcionamento:**

* **Editor de consultas** - Crie públicos-alvo usando filtros visuais em atributos de destinatários, comportamentos ou demografia
* **Listas** - Use listas de destinatários estáticas ou dinâmicas predefinidas
* **Importação de arquivos** - Carregue arquivos de destinatários externos para campanhas únicas
* **Fluxos de trabalho** - Criar lógica de direcionamento complexa com atividades de consulta, divisão e enriquecimento
* **Filtros predefinidos** - Aplicar filtros prontos para uso (clientes ativos, assinantes, VIPs)
* **Segmentos do Adobe Experience Platform** - Aproveite perfis unificados e segmentos em tempo real

Você pode combinar vários critérios (local, histórico de compras, envolvimento) e usar exclusões, interseções ou uniões para refinar seu público-alvo.

**Tópicos relacionados:**

[Definir públicos no Campaign v8](../audiences/gs-audiences.md) | [Editor de consultas](query-editor.md) | [Mapeamentos do Target](../audiences/target-mappings.md)

+++

+++ O que é um fluxo de trabalho?

O Adobe Campaign inclui fluxos de trabalho para organizar a gama completa de processos e tarefas em diferentes módulos do servidor de aplicativos. Esse ambiente gráfico abrangente permite criar processos, inclusive segmentação, execução de campanha, processamento de arquivos, participação humana, etc. O mecanismo de fluxo de trabalho executa e rastreia esses processos.

Você pode usar um fluxo de trabalho, por exemplo, para baixar um arquivo de um servidor, descompactar e importar registros contidos no banco de dados do Adobe Campaign.

Um fluxo de trabalho também pode envolver um ou mais operadores a serem notificados ou que podem fazer escolhas e aprovar processos. Dessa forma, é possível criar uma ação de entrega, atribuir uma tarefa a um ou mais operadores para trabalhar no conteúdo, especificar alvos e aprovar testes antes de iniciar a entrega.

[Saiba mais](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=pt-BR){target="_blank"} sobre fluxos de trabalho. Você também pode ler as [práticas recomendadas de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=pt-BR){target="_blank"}.

**Tópicos relacionados:**

[Introdução aos fluxos de trabalho](../config/workflows.md) | [Crie seu primeiro fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=pt-BR){target="_blank"} | [Casos de uso de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Monitorar a execução do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=pt-BR){target="_blank"}

+++

+++ Como criar e enviar o primeiro email?

Criar seu primeiro e-mail no Campaign v8 é simples. Você começa com um modelo, seleciona o público-alvo, projeta o conteúdo com personalização, testa com provas e envia. O Campaign oferece duas interfaces para criação de email: o **console do cliente** completo para usuários avançados e a **interface da Web do Campaign** moderna para criação de email mais rápida e intuitiva.

**5 etapas principais:**

1. **Criar entrega** - Iniciar com base em um modelo de email ou criar do zero
2. **Definir público-alvo** - Selecione destinatários usando consultas, listas ou fluxos de trabalho
3. **Criar conteúdo** - Use o designer de email para criar sua mensagem com campos de personalização
4. **Enviar provas de teste** - Validar a renderização e o conteúdo entre dispositivos e clientes de email
5. **Analisar e enviar** - Execute a análise de entrega para verificar se há erros e, em seguida, envie seu email

**Tópicos relacionados:**

[Design e validação de email](../send/email.md) | [Criar primeira entrega](create-message.md) | [Modelos de entrega](../send/create-templates.md) | [Personalizar conteúdo](../send/personalize.md)

+++

+++ Como enviar mensagens SMS?

O envio de SMS requer configuração inicial (configurar canal SMS, conexão SMPP, roteamento) e criação de delivery padrão.

**Processo básico:**

1. Configurar conexão de canal e provedor SMS (configuração única)
2. Criar entrega de SMS a partir de modelo
3. Definir recipients e gravar conteúdo (padrão de 160 caracteres, concatenação automática por mais tempo)
4. Adicionar personalização e enviar provas de teste
5. Analisar e enviar

**Recursos:** vários conectores SMPP, rastreamento de entrega, suporte a GSM7/Unicode, concatenação automática de SMS longo, SMS bidirecional com fluxos de trabalho.

**Tópicos relacionados:**

[Saiba mais sobre a configuração e envio de SMS](../send/sms/sms.md) | [Configurações de entrega de SMS](../send/sms/sms-delivery-settings.md) | [Criar entrega de SMS](../send/sms/create-sms.md)

+++

+++ Como enviar notificações por push?

O envio de notificações por push requer a configuração inicial da integração de aplicativos móveis e, em seguida, a criação do delivery padrão.

**Processo básico:**

1. **Configuração inicial** (única vez): configurar o canal de push, integrar o Campaign SDK ou a Coleção de Dados, registrar aplicativos da iOS/Android, configurar certificados APNs/FCM
2. **Criar entrega**: criar notificação por push a partir de modelo, selecionar plataforma, definir público-alvo, criar notificação com mídia avançada
3. **Testar e enviar**: validar em dispositivos reais e enviar

**Recursos:** push avançado (imagens, vídeos, botões), personalização, deep linking, agendamento, teste A/B e rastreamento. Recursos específicos da plataforma para iOS e Android.

**Tópicos relacionados:**

[Saiba mais sobre notificações por push](../send/push.md) | [Configurar canal de push](../send/push-settings.md) | [push avançado do Android](../send/rich-push-android.md) | [push avançado do iOS](../send/rich-push-ios.md)

+++

+++ Como criar uma landing page?

As landing pages no Campaign permitem capturar leads, gerenciar assinaturas e coletar dados por meio de formulários web. O Campaign oferece dois métodos: o **console do cliente** para formulários avançados com lógica complexa e a **interface do usuário da Web do Campaign** para criação rápida e moderna de páginas de aterrissagem com um editor de arrastar e soltar.

**Interface do usuário da Web do Campaign (recomendada para a maioria dos usuários):**

* Usar o editor visual para criar páginas de aterrissagem responsivas
* Adicionar campos de formulário, imagens e blocos de conteúdo com arrastar e soltar
* Mapear campos de formulário para atributos de banco de dados
* Configurar pré-preenchimento, mensagens de confirmação e páginas de agradecimento
* Publicar e rastrear envios em tempo real

**Console do cliente (para casos de uso avançado):**

* Crie aplicativos Web personalizados com lógica de negócios complexa
* Definir regras avançadas de mapeamento e validação de campo
* Criar formulários de várias páginas com roteamento condicional
* Acesse o modelo de dados completo do Campaign para enriquecimento

**Tópicos relacionados:**

[Criar páginas de aterrissagem (Interface do Usuário da Web)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"} | [Aplicativos Web (console do cliente)](../dev/landing-pages.md)

+++

+++ Como posso rastrear entregas?

Você pode rastrear e monitorar as entregas feitas com o Campaign v8 por meio de [relatórios de entrega](../reporting/delivery-reports.md) exclusivos.

Saiba mais sobre a gestão de rastreamento no Campaign [nesta página](../start/tracking.md).

**Tópicos relacionados:**

[Rastrear e monitorar mensagens](tracking.md) | [Relatórios de entrega](../reporting/delivery-reports.md) | [Entender as falhas de entrega](../send/delivery-failures.md) | [Configurar links rastreados](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}

+++

+++ Como traduzir uma mensagem de erro?

Há uma mensagem de erro exibida em outro idioma? Todas as mensagens de erro com suas devidas traduções estão listadas [nesta página](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=pt-BR){target="_blank"}.

+++

+++ Posso criar um formulário web e coletar respostas no Campaign?

Sim. Crie formulários web usando o **Campaign Web Applications &amp; Forms** (console de cliente) para obter controle total sobre a lógica e a validação do formulário, ou use as **Páginas de Aterrissagem do Campaign** (interface da Web) com uma interface de arrastar e soltar moderna para assinaturas e geração de clientes potenciais. Ambos coletam dados diretamente no Campaign e se integram a fluxos de trabalho para ações automatizadas.

**Tópicos relacionados:**

[Saiba mais sobre aplicativos e formulários Web](../dev/webapps.md) | [Páginas de aterrissagem da interface do usuário da Web do Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++


## Atualizações {#upgrades}

Saiba como verificar a versão do Campaign, entender o processo de atualização e manter-se informado sobre novos lançamentos. O Campaign v8 Managed Cloud Services lida com atualizações automaticamente com o mínimo de interrupção.

+++ Qual é minha versão do Campaign?

Verifique a [versão e o número de build](upgrades.md#version) no menu **Ajuda > Sobre...** do console de cliente do Campaign.

+++

+++ Como posso atualizar o Campaign para a versão mais recente?

O Adobe Campaign é atualizado regularmente. Versões secundárias são lançadas a cada ano com novos recursos, melhorias e correções. Além disso, periodicamente liberamos builds apenas com correções cumulativas.

Essa frequência regular de atualizações tem como objetivo disponibilizar a você o que há de melhor e mais recente, mantendo seu ambiente seguro e melhorando sua experiência com nosso produto. É por isso que acreditamos que é essencial executar a versão mais recente do Adobe Campaign.

**Observação:** como usuário do Managed Cloud Services, sua instância foi atualizada pela Adobe com novas versões.

Saiba mais sobre [versões e atualizações do Campaign](upgrades.md).

+++

+++ Como posso ser informado do lançamento de uma nova versão?

Mantenha-se informado sobre novos lançamentos do Campaign através destes canais:

* **Representante da Adobe** - Contata você diretamente quando uma nova versão estiver disponível
* **Notas de versão** - Todas as versões e alterações documentadas em [Notas de versão do Campaign](release-notes.md)
* **Atualizações de Produtos Prioritárias da Adobe** - [Assinar](https://www.adobe.com/br/subscription/priority-product-update.html){target="_blank"} para receber notificações por email
* **Comunidade do Campaign** - Participe de [discussões](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} para obter atualizações antecipadas

Como usuário do Managed Cloud Services, a Adobe lida com atualizações e coordena o tempo com você.

**Tópicos relacionados:**

[Notas de versão](release-notes.md) | [Novidades](whats-new.md) | [Versões e atualizações do Campaign](upgrades.md)

+++

+++ Por que minha organização precisa de uma atualização?

A atualização para a versão mais recente do Campaign é essencial para a segurança, o desempenho e a qualidade do suporte.

**Principais benefícios:**

* **Segurança aprimorada** - Proteção contra vulnerabilidades, patches mais recentes, proteção de dados aprimorada
* **Melhor suporte** - Solução de problemas mais rápida, acesso a correções de erros, suporte prioritário em versões recentes
* **Desempenho aprimorado** - otimizações de banco de dados e fluxo de trabalho, melhor escalabilidade, operações mais confiáveis
* **Novos recursos** - Recursos mais recentes, integrações aprimoradas com o Adobe Experience Cloud, melhorias na interface do usuário moderna

A Adobe recomenda executar a versão mais recente. Como cliente do Managed Cloud Services, as atualizações são realizadas pela Adobe com interrupção mínima.

**Tópicos relacionados:**

[Versões e atualizações do Campaign](upgrades.md) | [Novidades](whats-new.md) | [Matriz de compatibilidade](compatibility-matrix.md)

+++

+++ Qual é o processo e o cronograma de uma atualização?

Como cliente do Managed Cloud Services, a Adobe gerencia todo o processo de atualização com impacto mínimo nas operações.

**Processo:**

1. **Notificação** - A Adobe notifica você com semanas de antecedência
2. **Planejamento** - Agende a atualização na hora ideal com o representante da Adobe
3. **Preparação** - o Adobe prepara o ambiente e valida
4. **Execução** - O Adobe atualiza a infraestrutura com tempo de inatividade mínimo
5. **Validação** - Teste pós-atualização da Adobe
6. **Atualização do console do cliente** - Você atualiza seus consoles de cliente para corresponder à versão do servidor

**Suas responsabilidades:**

* Coordenar os participantes internos para obter o tempo
* [Atualize os consoles clientes](connect.md#upgrade-ac-console) para a nova versão
* Testar campanhas e workflows após a atualização
* Relatar problemas ao suporte da Adobe

O Adobe realiza o upgrade da infraestrutura. Não é necessário executar nenhuma ação técnica nos servidores.

**Tópicos relacionados:**

[Versões e atualizações do Campaign](upgrades.md) | [Atualizar console do cliente](connect.md#upgrade-ac-console) | [Notas de versão](release-notes.md)

+++


## Campaign v8 versus versões anteriores {#v7-differences}

Entenda as principais diferenças entre o Campaign v8 e as versões anteriores (Classic v7 e Standard), incluindo arquitetura, implantação, caminhos de migração e alterações de recursos. Quer você venha do Campaign Classic v7 ou do Campaign Standard, saiba as novidades e saiba como fazer a transição sem problemas.


+++ Quais são as principais diferenças entre o Campaign v8 e as versões anteriores?

O Campaign v8 é construído em uma arquitetura moderna nativa em nuvem com melhorias significativas:

* **Managed Cloud Services somente** - Totalmente hospedado pela Adobe (sem opções locais/híbridas)
* **Desempenho superior** - Até 20 milhões de operações/hora, com arquitetura Full Federated Data Access (FFDA)
* **Nova interface da Web do Campaign** - Interface moderna e intuitiva com o console clássico
* **Atualizações automáticas** - Sempre ativo na versão mais recente sem tempo de inatividade
* **Recursos aprimorados** - Assistente de IA, notificações por push avançadas, SMS atualizado, integrações aprimoradas com o Adobe Experience Cloud

**Para usuários do Campaign Classic v7:** Saiba mais sobre a [transição da v7 para a v8](v7-to-v8.md), incluindo alterações na arquitetura, recursos indisponíveis e considerações sobre migração.

**Para usuários do Campaign Standard:** Descubra o [caminho de transição para a v8](acs-to-v8.md) e o [guia de migração do Campaign Standard](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

**Tópicos relacionados:**

[Principais recursos do Campaign v8](whats-new.md) | [Arquitetura do Campaign v8](../architecture/architecture.md) | [Matriz de recursos](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Medidas de proteção e limitações](ac-guardrails.md)

+++

+++ Devo migrar do Campaign Classic v7 ou Campaign Standard para o v8?

O Campaign v8 é a plataforma estratégica da Adobe, ideal para organizações que precisam de campanhas de alto volume (20 milhões de operações/hora), interface do usuário moderna da Web, benefícios nativos da nuvem e suporte a longo prazo. As versões anteriores atingirão o fim do suporte nos próximos anos.

**Principais benefícios:**

* **Para usuários do Campaign Standard** - Interface familiar da Web, paridade de recursos (Dynamic Reporting, APIs REST, Páginas de Aterrissagem), migração de dados sem problemas
* **Para usuários do Campaign Classic v7** - Interface dupla (console + interface da Web), melhor desempenho, atualizações automáticas, arquitetura FFDA aprimorada

**Considere migrar se você:**

* Lidar com grandes volumes de dados ou enfrentar problemas de desempenho
* Desejam reduzir as despesas gerais de TI e o gerenciamento de infraestrutura
* Necessidade de integração Adobe Experience Cloud/Platform
* Quer tecnologia que não se torna obsoleta com atualizações automáticas

**Próximas etapas:** Entre em contato com seu representante da Adobe para avaliar a disponibilidade da migração e acessar as ferramentas de migração.

**Tópicos relacionados:**

[Do Campaign Classic v7 para o v8](v7-to-v8.md) | [guia de transição do Campaign Standard](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Matriz de recursos](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}

+++

+++ O Campaign v8 pode ser instalado em um ambiente local ou híbrido?

Não. O Campaign v8 está disponível exclusivamente como uma **Cloud Service gerenciada**, totalmente hospedada pela Adobe.

**Principais benefícios do Managed Cloud Services:**

* Desempenho e escalabilidade superiores
* Atualizações automáticas - sempre com a versão mais recente
* Segurança aprimorada com monitoramento contínuo
* Sem gerenciamento de infraestrutura ou sobrecarga de TI
* Alta disponibilidade incorporada e recuperação de desastres

Saiba mais sobre a [arquitetura do Campaign v8](../architecture/architecture.md) e as [diferenças entre o Campaign v8 e o Classic v7](../start/v7-to-v8.md).

+++

+++ Como migrar meu ambiente Campaign Classic v7 no local ou híbrido para o Adobe Managed Services?

A migração para o Adobe Managed Services fornece um caminho estratégico do v7 local/híbrido para a nuvem, oferecendo escalabilidade aprimorada, segurança e redução das despesas gerais de TI. Geralmente, é uma etapa antes da transição para o Campaign v8.

**Pontos principais:**

* Nenhuma ferramenta de migração automatizada disponível - planejamento e execução manuais necessários
* Suporte ao Adobe Professional Services altamente recomendado
* Os benefícios incluem infraestrutura em nuvem, patches de segurança automáticos, suporte especializado e caminho mais fácil para o v8
* A migração envolve devida diligência, auditoria de ambiente, limpeza de dados, migração de preparo e transferência de produção

**Introdução**: entre em contato com o representante da Adobe para avaliar seu ambiente e desenvolver um plano de migração detalhado com a Adobe Professional Services.

Saiba mais sobre a [migração para o Managed Services](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605){target="_blank"}, incluindo desafios, práticas recomendadas e roteiro de migração detalhado.

+++

+++ Quais são as principais diferenças de terminologia e recursos no Campaign v8?

O Campaign v8 oferece a maioria dos recursos v7/Standard com melhorias, mas a terminologia e os recursos diferem devido à arquitetura nativa em nuvem.

**Principais alterações de terminologia (Campaign Standard → v8):**

* Recursos personalizados → **Esquemas** | Mensagens → **Entregas** | Usuários do produto → **Operadores**
* Grupos de Segurança → **Grupos de Operadores** | Unidades organizacionais → **Permissões de pasta**

**Atualizações na interface da Web do Campaign:**

* Destinatários → **Perfis** | Seed addresses → **Perfis de teste** | Análise de entrega → **Preparação da entrega**
* Listas → **Públicos** | Visualização de email → **Simular conteúdo**

**Não disponível na v8:**

* Implantações locais/híbridas (somente Managed Cloud Services)
* Acesso direto ao banco de dados (use APIs)
* Gerenciamento manual da infraestrutura (gerenciado pela Adobe)

**Novos recursos para usuários do Campaign Standard:**

* Relatórios dinâmicos, Marcas centralizadas, APIs REST, melhorias nas Páginas iniciais, Fragmentos visuais

**Tópicos relacionados:**

[Matriz de recursos](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Guia de transição do v7 para o v8](v7-to-v8.md) | [Transição do Campaign Standard para o v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## Perfis e públicos-alvos {#audiences}

Encontre respostas para perguntas sobre como gerenciar perfis, criar públicos, importar dados e direcionar recipients para suas campanhas.

+++ Como criar destinatários?

Crie recipients manualmente no console do cliente para perfis individuais, importe de arquivos (CSV/TXT) para adições em massa, use formulários web para se autorregistrar ou integre por meio de APIs de sistemas externos. Use workflows de importação para cargas de dados recorrentes.

**Tópicos relacionados:**

[Criar perfis manualmente](../audiences/create-profiles.md) | [Importar perfis de um arquivo](../audiences/import-profiles.md) | [Coletar perfis com formulários web](../audiences/collect-profiles.md)

+++

+++ Como importar perfis?

O Campaign oferece vários métodos de importação: importação simples de arquivos usando o assistente de importação, importação baseada em fluxo de trabalho para transformações complexas, importações recorrentes com fluxos de trabalho agendados do SFTP e importação de API para integração programática.

Para importações de arquivos, prepare seu arquivo de dados (codificação CSV/TXT, UTF-8), use o assistente de importação ou fluxo de trabalho, mapeie colunas para campos do Campaign, defina regras de atualização/inserção e teste com uma pequena amostra primeiro. Use workflows para importações recorrentes e aplique regras de desduplicação.

**Tópicos relacionados:**

[Guia de importação de dados](../start/import.md) | [Fluxo de trabalho de importação recorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [Atividade de carregamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=pt-BR){target="_blank"}

+++

+++ Como criar perfis de teste para meus deliveries?

Os perfis de teste (seed addresses) permitem direcionar recipients que não correspondem aos critérios de direcionamento definidos, permitindo que você teste o delivery antes de enviar ao público-alvo principal. Adicione-os via **[!UICONTROL Seed addresses]** nas propriedades de entrega ou use a pasta **[!UICONTROL Seed addresses]**.

Saiba mais sobre [perfis de teste](../audiences/test-profiles.md).

+++

+++ Como posso definir a população alvo de uma campanha de marketing?

O Campaign oferece vários métodos de direcionamento: criar consultas com critérios visuais, direcionar listas ou segmentos existentes, importar destinatários de arquivos externos (CSV, TXT) ou aplicar filtros predefinidos. Você pode combinar critérios com a lógica E/OU, excluir populações específicas, usar grupos de controle e dividir para testes A/B. Sempre visualize o tamanho do público-alvo antes de enviar.

**Tópicos relacionados:**

[Definir alvos da campanha](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=pt-BR){target="_blank"} | [Atividade de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=pt-BR){target="_blank"} | [Criar públicos-alvo](../audiences/create-audiences.md)

+++

+++ Como posso criar uma lista de perfis?

Uma lista é um conjunto estático de recipients que pode ser direcionado em deliveries e reutilizado em campanhas.

**Três métodos de criação:**

* **Criação manual:** Navegue até **[!UICONTROL Profiles and Targets > Lists]** e clique em **[!UICONTROL Create]**. Adicionar recipients de um query, por seleção individual ou de uma pasta.

* **Automação de fluxo de trabalho:** Use a atividade **[!UICONTROL List update]** para criar e manter listas automaticamente a partir dos resultados da consulta ou dos dados importados.

* **Durante a importação:** crie uma lista ao importar perfis para salvá-los como um grupo reutilizável.

**Dica:** use fluxos de trabalho para listas que exigem atualizações regulares e criação manual para segmentação única.

**Tópicos relacionados:**

[Criar públicos-alvo](../audiences/create-audiences.md) | [Listar atividade de atualização](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ Como posso excluir informações em duplicidade de uma população antes de enviar uma mensagem?

Use a atividade **[!UICONTROL Deduplication]** em um fluxo de trabalho para remover destinatários duplicados antes da entrega. Coloque-o entre as atividades de **[!UICONTROL Query]** e **[!UICONTROL Delivery]**, escolha os critérios de desduplicação (normalmente endereço de email ou ID de destinatário) e qual registro manter.

**Dica:** sempre elimine a duplicação antes de enviar para garantir que cada pessoa receba sua mensagem apenas uma vez.

Saiba mais sobre a [Atividade de desduplicação](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=pt-BR){target="_blank"}

+++

+++ Como identificar e direcionar assinantes a um informativo?

O Campaign rastreia automaticamente as assinaturas de boletim informativo por meio de serviços de informações. Para direcionar assinantes:

* Use uma atividade de **[!UICONTROL Query]** e filtre por **[!UICONTROL Subscriptions]** > selecione seu serviço de boletim informativo
* Direcione assinantes diretamente da sua entrega escolhendo **[!UICONTROL To > Subscribers of an information service]**
* Criar listas de assinantes com a atividade de fluxo de trabalho **[!UICONTROL Subscription Services]**

A campanha rastreia o histórico de subscrição/unsubscription e gerencia a aceitação/recusa automaticamente.

**Tópicos relacionados:**

[Gerenciar assinaturas](../start/subscriptions.md) | [Atividade de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=pt-BR){target="_blank"}

+++

+++ Qual é a prática recomendada para excluir perfis de uma população alvo?

Use a atividade **[!UICONTROL Exclusion]** em um fluxo de trabalho para remover perfis indesejados do seu público-alvo. Coloque-o após as atividades de direcionamento e defina qual população excluir.

Saiba mais sobre a [Atividade de exclusão](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ Posso usar perfis externos sem importá-los no Campaign?

Sim, o Campaign v8 permite trabalhar com perfis externos armazenados em um banco de dados externo sem carregá-los no Adobe Campaign. [Saiba mais](../audiences/external-profiles.md).

+++

## Design da mensagem {#design}

Saiba como projetar mensagens de marketing eficazes no Campaign v8, incluindo modelos de email, técnicas de personalização e conteúdo multilíngue. Projete suas mensagens no console do cliente ou use o moderno **Email Designer** na interface do usuário da Web do Campaign para obter uma experiência aprimorada de edição visual.

+++ Quais são as práticas recomendadas para criar e-mails no Campaign?

Principais diretrizes: garantir design responsivo para dispositivos móveis, usar código compatível com HTML 4.0/XHTML com CSS em linha, otimizar imagens (abaixo de 100 KB) com texto alternativo, usar campos de mesclagem de personalização, testar clientes de email antes de enviar e incluir uma versão de texto simples. Tenha como meta o tamanho total do email abaixo de 500 KB para uma entrega ideal.

[Guia de design de email](../send/email.md) | [Práticas recomendadas de entrega](delivery-best-practices.md)

+++

+++ O que é um modelo da entrega?

Um template do delivery é um delivery pré-configurado que salva todas as configurações e parâmetros para reutilização em várias campanhas. Os modelos incluem regras de direcionamento, design de conteúdo, personalização, configurações técnicas (remetente, responder para) e regras de tipologia. Crie uma única vez e reutilize para manter a consistência e acelerar a criação da campanha.

Saiba como [Criar modelos de entrega](../send/create-templates.md)

+++

+++ Posso importar facilmente um HTML existente para criar um email no Campaign?

Sim. Importe conteúdo do HTML por meio de cópia/colagem direta no editor de conteúdo, upload de arquivo do seu computador ou carregamento de um URL. Certifique-se de que o HTML usa código compatível com email (HTML 4.0/XHTML) com CSS em linha e hospeda imagens em um servidor público. O Campaign adiciona automaticamente personalização e rastreamento ao HTML importado.

**Dica:** para obter a melhor experiência de design de email, use o **Designer de email** na interface do usuário da Web do Campaign, que oferece recursos modernos de arrastar e soltar e modelos responsivos incorporados, em vez de importar HTML bruto.

Saiba como [Importar conteúdo do HTML](../send/defining-the-email-content.md)

+++

+++ Como posso criar um boletim informativo baseado em assinaturas no Campaign?

Sim. Use os serviços de informações do Campaign para gerenciar assinaturas de boletins informativos. Os principais recursos incluem controle automático de aceitação/recusa, rastreamento de assinatura, gerenciamento de conformidade (GDPR, CAN-SPAM), suporte a vários boletins informativos, integração da Web para formulários de inscrição e entrega direcionada aos assinantes.

Saiba como [gerenciar assinaturas](../start/subscriptions.md)

+++

+++ Como posso personalizar mensagens?

O Campaign oferece recursos de personalização para criar mensagens relevantes e direcionadas com base em dados, comportamento e preferências do recipient.

**Opções do Personalization:**

* **Campos de personalização** - Insira os dados do destinatário (por exemplo, `"Hello {{firstName}}")`
* **Blocos de personalização** - Use blocos de conteúdo predefinidos ou personalizados
* **Conteúdo condicional** - Exibir conteúdo diferente com base nos critérios do destinatário
* **Dados comportamentais** - Aproveite o histórico de navegação, os padrões de compra ou as métricas de envolvimento

Teste a personalização antes de enviar para verificar se os campos de mesclagem e a lógica condicional funcionam corretamente.

**Tópicos relacionados:**

[Guia do Personalization](../send/personalize.md) | [Campos de personalização](../send/personalization-fields.md) | [Conteúdo condicional](../send/conditions.md)

+++

+++ Posso enviar mensagens em vários idiomas?

Sim. O Campaign v8 oferece recursos multilíngues, com a **Interface do usuário da Web do Campaign** fornecendo a abordagem mais fácil. A interface da Web oferece delivery multilíngue nativo com variantes de idioma. Adicione variantes de idioma ao delivery e o Campaign envia automaticamente a versão apropriada com base no idioma preferencial do recipient. Disponível para email, notificações por push, SMS e mensagens transacionais.

Principais recursos: duplicação automática de conteúdo, envio automático baseado em idioma, fallback de idioma padrão e gerenciamento fácil de variantes.

O console do cliente também oferece suporte a conteúdo multilíngue usando conteúdo condicional e fluxos de trabalho, mas requer mais configuração manual.

**Tópicos relacionados:**

[Entregas multilíngues (Interface do Usuário da Web)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Conteúdo condicional (Console do cliente)](../send/conditions.md)

+++

+++ Posso traduzir um formulário web?

Sim. Os aplicativos Web do Campaign oferecem suporte à localização em vários idiomas. Defina traduções para todos os elementos de formulário (rótulos, botões, mensagens, texto de erro), com detecção automática de idioma com base no perfil do destinatário ou nas configurações do navegador. Há suporte para várias versões de idioma em um único aplicativo web, com fallback para um idioma padrão quando necessário.

Saiba mais sobre a [localização de aplicativos Web](../dev/webapps.md)

+++

+++ Posso usar conteúdo alimentado por IA em meus emails?

Sim, mas **somente por meio da interface da Web do Campaign**. O Assistente de IA, desenvolvido pelo Microsoft Azure OpenAI e Adobe Firefly, ajuda a criar conteúdo profissional e consistente com a marca por email, SMS e notificações por push.

**Principais recursos:**

* Gerar texto (cópia de email, linhas de assunto, conteúdo de SMS/push) e imagens alinhadas à marca
* Criar variações de conteúdo otimizadas para públicos diferentes
* Refinar conteúdo (elaborar, resumir, reformular, simplificar)
* Faça upload dos ativos da marca e obtenha a pontuação do alinhamento da marca
* Usar conteúdo existente como referência e fazer upload de imagens de referência de estilo

**Observação: o Assistente de IA** está disponível exclusivamente na interface do usuário da Web do Campaign e atualmente só oferece suporte a inglês. Os usuários precisam de permissões adequadas e devem concordar com um contrato de usuário.

**Tópicos relacionados:**

[Visão geral do Assistente de IA](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Casos de uso do Assistente de IA](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Alinhamento da marca](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Teste e envio de mensagens {#send}

Conheça as práticas recomendadas para testar, validar, enviar e rastrear suas mensagens de marketing para garantir o sucesso do delivery do Campaign.

+++ O que é análise de entrega?

A análise de entrega é uma fase de validação na qual a Campanha é executada antes do envio. Ele calcula a população do target, valida o conteúdo, verifica erros, aplica regras de tipologia e estima o volume de delivery.

O Campaign gera logs mostrando avisos e erros. Os erros bloqueiam a entrega e devem ser corrigidos; os avisos são consultivos. Sempre revise os logs de análise antes de enviar.

Saiba mais no [Guia de análise de entrega](../send/delivery-analysis.md)

+++

+++ Por que devo criar provas?

Provas são mensagens de teste que validam sua entrega antes de enviá-la para o público-alvo principal. Use provas para verificar a personalização, testar a renderização de conteúdo em clientes de email, confirmar links e o trabalho de rastreamento, verificar imagens e anexos e validar a capacidade de resposta móvel.

As provas ajudam a detectar erros antes que eles alcancem milhares de recipients, ativar a aprovação das partes interessadas e testar a inserção da caixa de entrada. Envie provas para vários clientes e dispositivos de email e sempre obtenha aprovação antes que a produção seja enviada.

Saiba mais no [guia de provas e visualização](../send/preview-and-proof.md)

+++

+++ Como usar seed addresses no Adobe Campaign?

Os seed addresses são recipients especiais adicionados automaticamente a cada delivery para teste, controle de qualidade e monitoramento, sem corresponder aos critérios do público-alvo. Útil para monitoramento contínuo, teste de posicionamento na caixa de entrada, validação de correspondência direta e visibilidade das partes interessadas.

**Principais diferenças das provas:**

* **Seed addresses** - Adicionado às entregas de produção automaticamente, conte para enviar volume
* **Provas** - O teste envia antes da produção, não conte no volume, usado para validação

Gerenciar seed addresses em **[!UICONTROL Resources > Campaign management > Seed addresses]**. Mantenha listas pequenas para não afetar as métricas de entrega.

Saiba mais no [Guia de seed addresses](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ Como posso configurar um processo de aprovação antes de enviar mensagens?

O Campaign fornece workflows de aprovação para garantir que as mensagens atendam aos padrões de qualidade antes do envio. Configure aprovações para conteúdo, target, extração (correspondência direta) e orçamento no nível da campanha ou do delivery.

**Instalação:**

Crie grupos de operadores em **[!UICONTROL Administration > Access management > Operator groups]** e atribua grupos de aprovações nas propriedades de campanha ou de entrega. O Campaign envia emails de notificação para revisores que podem aprovar, rejeitar ou solicitar alterações.

**Para entregas autônomas (não em uma campanha):**

Use **provas como seu processo de aprovação**. Envie provas ao seu grupo de aprovação para validação e sempre envie uma nova prova depois de fazer alterações para garantir que as partes interessadas revisem a versão mais recente.

**Tópicos relacionados:**

[Validação da entrega](../send/preview-and-proof.md) | [Aprovações de campanha](https://experienceleague.adobe.com/pt-br/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval){target="_blank"}

+++

+++ O que é uma regra de tipologia?

As regras de tipologia são uma lógica de negócios automatizada aplicada durante a análise da entrega para validar e otimizar o envio de mensagens. Elas garantem a conformidade com as políticas de marketing, protegem a capacidade de entrega e evitam a fadiga do cliente.

**Principais tipos de regras:**

* incluir na lista de bloqueios **Regras de filtragem** - Excluir destinatários (, cancelado, em quarentena)
* **Regras de pressão** - Controle a frequência da mensagem para evitar sobrecarga dos destinatários
* **Regras de capacidade** - Limitar volume de mensagens para capacidade de processamento ou limites ISP
* **Regras de controle** - Verifique a validade da mensagem (linha de assunto, link de cancelamento de inscrição, formato do remetente)

As regras são agrupadas em tipologias e aplicadas durante a análise de delivery. O Campaign pode excluir recipients, bloquear o delivery ou gerar avisos com base nas regras.

Saiba mais no [Guia de regras de tipologia](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso enviar emails em ondas?

Sim. O envio de onda divide seu delivery em vários lotes enviados em intervalos programados. Isso é essencial para campanhas de grande volume, a fim de balancear a carga do servidor, impedir a limitação do ISP, criar a reputação do remetente com novos IPs e gerenciar recusas/rejeições entre ondas.

**Configuração:**

Nas propriedades de delivery, ative o envio de ondas e defina o número de ondas (ou o tamanho do lote), o intervalo entre as ondas e a distribuição de ondas (porcentagens lineares ou personalizadas). O Campaign divide automaticamente sua população de público-alvo e envia cada onda conforme programado.

Use ondas para campanhas grandes, monitore o desempenho da primeira onda antes de continuar e aguarde tempo suficiente entre as ondas para processar rejeições e recusas.

Saiba como [Configurar envio de onda](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ Como agendar uma entrega?

O Campaign permite agendar deliveries para envio futuro, a fim de otimizar os tempos de envio e coordenar campanhas.

**Opções de agendamento:**

* **Propriedades de entrega** - Enviar imediatamente, agendar uma data/hora específica ou adiar por horas/dias
* **Nível de campanha** - Coordene todas as entregas em uma campanha
* **Atividade do Agendador de Fluxo de Trabalho** - Para entregas recorrentes, padrões complexos e campanhas acionadas por eventos

O Campaign também oferece suporte à otimização da data de contato (melhor horário de envio por recipient) e à adaptação do fuso horário (mesmo horário local para todos os recipients).

Saiba como [Agendar envio de entrega](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Posso adicionar um anexo aos emails?

Sim. O Campaign é compatível com anexos estáticos (o mesmo arquivo para todos os destinatários) e anexos personalizados (arquivos diferentes por destinatário com base nos dados de perfil). Adicione anexos na seção **[!UICONTROL Attachments]** de suas propriedades de entrega.

**Considerações importantes:**

* Mantenha os anexos abaixo de 1 MB para obter a entrega ideal
* Os anexos podem acionar filtros de spam; teste completamente antes de enviar
* Evite tipos de arquivos comumente bloqueados por clientes de email (.exe, .zip, .js)
* Para arquivos grandes, considere usar links de download rastreados

Use formatos de arquivo seguros (PDF, JPEG, PNG, DOCX) e teste com seed addresses antes do envio da produção.

Saiba mais no [Guia de anexos de email](../send/email.md#attachments)

+++

+++ Como posso configurar links rastreados em uma entrega de email?

O Campaign converte automaticamente todos os URLs no seu email em links rastreados para monitorar a participação do recipient. Acesse a seção **[!UICONTROL Tracking]** na entrega para definir as configurações de rastreamento para cada link.

**Opções de configuração:**

* **Habilitar/desabilitar rastreamento** - Controle de rastreamento por link
* **Rótulos de links** - Adicione nomes descritivos para relatórios (por exemplo, &quot;Comprar agora CTA&quot;)
* **Categorias de links** - Agrupa os links por tipo para análise agregada
* **Tipo de rastreamento** - Rastrear cliques, aberturas ou ambos

A campanha rastreia links de conteúdo, links de mirror page, links de cancelamento de inscrição e pode incluir um pixel de rastreamento opcional para aberturas de email. Use rótulos e categorias relevantes para simplificar os relatórios e identificar rapidamente o conteúdo de alto desempenho.

**Tópicos relacionados:**

[Guia de rastreamento de links](../start/tracking.md) | [Práticas recomendadas de rastreamento](../send/send.md)

+++

+++ Onde posso acessar logs de entrega e rastreamento?

Acesse os logs de delivery e rastreamento diretamente de cada painel de delivery. No console do cliente, clique na guia **[!UICONTROL Delivery]** na parte inferior. Na interface da Web do Campaign, navegue até a seção **[!UICONTROL Logs]**.

**Logs disponíveis:**

* **Logs de entrega** - Mensagens enviadas com detalhes e status do destinatário (enviado, pendente, com falha)
* **Logs de rastreamento** - Interações de destinatários (aberturas, cliques) com carimbos de data/hora
* **Logs de exclusão** - Destinatários excluídos com motivos (quarentena, regras de tipologia, duplicatas)
* **Logs de transmissão** - Histórico de envio completo, incluindo tentativas e erros

Use esses logs para solucionar problemas de entrega, analisar o engajamento e manter a higiene das listas.

**Tópicos relacionados:**

[Monitoramento de entrega](../send/send.md) | [Guia de rastreamento](../start/tracking.md)

+++

+++ Onde posso obter relatórios de entrega?

O Campaign fornece relatórios integrados abrangentes para analisar o desempenho do delivery, o engajamento do recipient e a eficácia da campanha. Acesse relatórios da guia **[!UICONTROL Reports]** em qualquer entrega, no painel de campanha ou no menu global **[!UICONTROL Reports]** para análise entre campanhas.

**Os principais relatórios incluem:**

* **Resumo da entrega** - Enviar estatísticas, aberturas, cliques, rejeições e cancelamentos de assinatura
* **Hot clicks** - mapa de calor visual do desempenho do link
* **Indicadores de rastreamento** - Taxas de click-through e métricas de envolvimento
* **Não entregues** - Análise de rejeição com motivos de falha

Os relatórios estão disponíveis no console do cliente e na interface da Web do Campaign com visualizações modernas.

**Tópicos relacionados:**

[Relatórios de entrega internos](../reporting/delivery-reports.md) | [Relatórios de campanha](../reporting/gs-reporting.md)

+++

+++ Como o Adobe Campaign qualifica e gerencia endereços em quarentena?

O Campaign gerencia automaticamente uma lista de quarentena para proteger a reputação do remetente e melhorar a capacidade de entrega. Os endereços em quarentena são excluídos automaticamente de deliveries futuros até serem validados ou removidos da quarentena.

**Por que os endereços são colocados em quarentena:**

* **Rejeições permanentes** - Falhas permanentes de entrega (endereço de email inválido, o domínio não existe e a caixa de correio foi excluída)
* **Limite de rejeição temporária** - Falhas temporárias repetidas (caixa de correio cheia, servidor temporariamente indisponível) excedendo o limite de erro
* **Reclamações de spam** - Destinatários que marcam seus emails como spam
* **Endereços inválidos** - Endereços com erros de sintaxe ou que falham na validação
* incluir na lista de bloqueios **&#x200B;**&#x200B;- Destinatários que optaram por não participar ou solicitaram a exclusão

**Como funciona a quarentena:**

A campanha rastreia erros de delivery para cada endereço. Quando um endereço atinge o limite de erro configurado, ele é automaticamente colocado em quarentena e excluído de todos os deliveries futuros durante a análise. As rejeições permanentes (falhas permanentes) são colocadas em quarentena imediatamente, enquanto as rejeições temporárias exigem várias falhas antes da quarentena.

**Gerenciando endereços em quarentena:**

Acesse o gerenciamento de quarentena em **[!UICONTROL Administration > Campaign Management > Non deliverables Management]**. Você pode exibir endereços em quarentena, remover manualmente endereços validados da quarentena ou configurar regras de limpeza automática.

**Dica:** Monitore regularmente sua lista de quarentena. O aumento das taxas de quarentena geralmente sinaliza problemas de qualidade de dados que precisam de atenção antes que afetem a reputação do remetente.

**Tópicos relacionados:**

[Guia de gerenciamento de quarentena](../send/quarantines.md) | [Gerenciamento de rejeição](../send/delivery-failures.md)

+++

## Fluxos de trabalho {#workflows}

Saiba como usar workflows para automatizar processos, gerenciar dados e orquestrar campanhas de marketing complexas no Adobe Campaign.

+++ Quais são as principais etapas para criar um fluxo de trabalho?

Criar workflows para automatizar processos de marketing no Campaign:

1. **Criar um novo fluxo de trabalho** - Navegue até **[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]** ou **[!UICONTROL Administration > Production > Technical workflows]** e clique em **[!UICONTROL Create]**
1. **Adicionar atividades** - Arraste e solte atividades da paleta (atividades de direcionamento, controle de fluxo, ação)
1. **Configurar atividades** - Clique duas vezes em cada atividade para definir parâmetros e lógica
1. **Atividades de conexão** - Vincule atividades com transições para definir o fluxo de execução
1. **Testar e validar** - Use o diagrama de fluxo de trabalho para verificar a lógica e teste com um pequeno conjunto de dados
1. **Executar** - Iniciar o fluxo de trabalho manualmente ou agendá-lo para execução automática

Padrões comuns de fluxo de trabalho: importação de dados, segmentação de público-alvo, envio de delivery, enriquecimento de dados e orquestração entre canais.

**Tópicos relacionados:**

[Criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=pt-BR){target="_blank"} | [Atividades do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [Práticas recomendadas de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=pt-BR){target="_blank"} | [Casos de uso de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Como posso importar dados no Campaign?

**Métodos:** Assistente de importação (CSV/TXT único), importação baseada em fluxo de trabalho (**[!UICONTROL Data loading (file)]** atividade para importações complexas/recorrentes com transformações), APIs REST (sincronização programática/em tempo real).

**Práticas recomendadas:** teste com amostras pequenas, use a codificação UTF-8, mapeie os campos corretamente, aplique a desduplicação e agende grandes importações fora do horário de pico.

**Tópicos relacionados:**

[Práticas recomendadas de importação](../start/import.md) | [Atividade de carregamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=pt-BR){target="_blank"} | [Fluxo de trabalho de importação recorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ Quais são os casos de uso comuns de fluxo de trabalho no Campaign?

Os workflows automatizam processos de marketing, incluindo:

**Gerenciamento de dados:** Importar/carregar dados, limpeza, enriquecimento, gerenciamento de listas\
**Automação de campanha:** série de boas-vindas, campanhas de aniversário, reengajamento, abandono de carrinho\
**Direcionamento avançado:** teste A/B, segmentação dinâmica, pontuação de clientes potenciais, orquestração entre canais\
**Monitoramento:** Monitoramento de fluxo de trabalho/entrega, alertas, manutenção de banco de dados\
**Integração:** sincronização de CRM, integrações de API, fluxos de trabalho acionados por eventos

**Tópicos relacionados:**

[Biblioteca de casos de uso de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=pt-BR){target="_blank"} | [Práticas recomendadas de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso atualizar dados do Campaign com um fluxo de trabalho?

Usar a atividade **[!UICONTROL Update data]** para operações de banco de dados em massa: Inserir (adicionar novos registros), Atualizar (modificar existentes), Inserir ou atualizar (substituir), Excluir (remover registros correspondentes).

**Usos comuns**: atualizar atributos de perfil, sincronizar com sistemas externos, manter associações de lista, limpar/desduplicar dados, aplicar alterações de status em massa.

Configure as chaves de reconciliação para uma correspondência precisa e escolha opções de atualização.

**Tópicos relacionados:**

[Atualizar atividade de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=pt-BR){target="_blank"} | [Atividades de gerenciamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Como posso aproveitar os recursos de gestão de dados?

As atividades de gerenciamento de dados permitem operações sofisticadas: Enriquecimento (adicione dados de tabelas relacionadas), Divisão (populações de segmentos), Desduplicação (remova duplicatas), Atualização de dados (operações em massa), Alteração de dimensão (alterne dimensões de direcionamento), Interseção/União/Exclusão (combine/filtre populações).

**Usos comuns:** enriqueça com dados de compra/comportamento, segmente públicos, remova duplicatas, integre bancos de dados externos (FDA), crie consultas complexas de várias tabelas.

**Tópicos relacionados:**

[Atividades de gerenciamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [Atividade de enriquecimento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=pt-BR){target="_blank"}

+++

+++ Posso automatizar o envio de mensagens personalizadas?

Sim. Criar fluxos de trabalho automatizados: Query (público-alvo) → Enriquecimento (adicionar dados de personalização) → Split (segmentos opcionais) → Delivery (mensagens personalizadas) → Scheduler (execução recorrente).

**Personalization:** Use dados de perfil, dados comportamentais, conteúdo condicional e valores dinâmicos. Cenários comuns: campanhas de aniversário, abandono de carrinho, programas de fidelidade, reconquista, mensagens acionadas por eventos.

**Tópicos relacionados:**

[Guia do Personalization](../send/personalize.md) | [Casos de uso de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=pt-BR){target="_blank"}

+++

+++ Como dividir um público-alvo em subconjuntos com um fluxo de trabalho?

Use a atividade **[!UICONTROL Split]** para dividir as populações: Condições de filtragem (idade, local, status do VIP), Distribuição percentual (teste A/B), Registros de limite (primeiro N, X% principais), Agrupamento de dados (um subconjunto por valor).

**Usos comuns:** teste A/B, roteamento de preferência de canal, implantação progressiva, mensagens específicas de segmento, balanceamento de carga. Cada subconjunto flui para separar a transição para um processamento diferente.

**Tópicos relacionados:**

[Dividir atividade](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=pt-BR){target="_blank"} | [Guia de teste A/B](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Como posso atualizar os dados do destinatário de um arquivo externo?

Sim. Fluxo de trabalho: Carregamento de dados (arquivo) → Enriquecimento (opcional) → Reconciliação (chaves de correspondência como email/ID) → Atualizar dados (atualizar registros correspondentes, inserir novo se não houver correspondência).

**Usos comuns**: atualizar atributos de perfil do CRM, atualizar status de assinatura, sincronizar pontos de fidelidade, atualizar preferências de aceitação/recusa.

**Práticas recomendadas:** use identificadores exclusivos, valide os dados primeiro, teste com amostras, agende atualizações regulares.

**Tópicos relacionados:**

[Guia de importação de dados](../start/import.md) | [Atividade de carregamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=pt-BR){target="_blank"} | [Atualizar atividade de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso identificar e direcionar novos destinatários?

Consulte o campo **[!UICONTROL Created date]** para selecionar destinatários adicionados dentro do período de tempo específico.

**Fluxo de trabalho de boas-vindas automatizado:** Agendador (execução diária) → Consulta (selecionar novos destinatários) → Desduplicação (opcional) → Entrega (mensagem de boas-vindas) → Atualizar dados (marcar como &quot;bem-vindo&quot;).

**Avançado:** Use funções de agregação para identificar dinamicamente adições recentes.

**Tópicos relacionados:**

[Atividade de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=pt-BR){target="_blank"} | [Usando agregações](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=pt-BR){target="_blank"}

+++

+++ Como faço para usar as atividades de fluxo de trabalho?

Quatro categorias de atividade:

**Direcionamento:** Query, Split, Deduplication, Enrichment, Intersection, Union, Exclusion (definir/refinar público)\
**Controle de fluxo:** Scheduler, Wait, Test, Fork, AND-join, OR-join, Jump (gerenciar lógica/tempo)\
**Ação:** Entrega, Atualização de dados, Carregamento/extração de dados, código JavaScript (executar operações)\
**Evento:** Sinal externo, Coletor de arquivos, transferência HTTP (reage aos disparadores)

Arraste da paleta, clique duas vezes para configurar, conectar com transições.

**Tópicos relacionados:**

[Atividades de direcionamento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"} | [Controle de fluxo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"} | [Atividades de ação](https://experienceleague.adobe.com/pt-br/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities){target="_blank"}

+++

+++ Quais são as práticas recomendadas de workflow?

**Design:** Limpar nomes, adicionar rótulos/descrições, agrupar atividades relacionadas, dividir processos complexos em fluxos de trabalho menores\
**Desempenho:** Limite os tamanhos das consultas, use tabelas temporárias, agende fora de pico, evite loops excessivos\
**Tratamento de erros**: adicionar caminhos de erro, configurar alertas, testar com amostras, examinar logs\
**Manutenção:** Arquive fluxos de trabalho obsoletos, controle de versão, limite de complexidade (menos de 20 atividades), use modelos\
**Segurança:** Aplicar permissões, limpar dados temporários, usar variáveis e não valores codificados

**Tópicos relacionados:**

[Guia de práticas recomendadas de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=pt-BR){target="_blank"} | [Monitorar fluxos de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=pt-BR){target="_blank"}

+++

## Configurações da campanha {#settings}

Configure sua instância do Campaign com as configurações, integrações e configurações corretas para otimizar suas operações de marketing.

+++ Posso alterar o idioma da interface do Campaign?

Depende de qual interface você está usando. O idioma **console do cliente** foi corrigido, mas a **interface da Web do Campaign** permite que usuários individuais alterem suas preferências de idioma.

**Console do Cliente (Aplicativo de Área de Trabalho):**

* O idioma é definido quando sua instância é criada e não pode ser alterado
* O console do cliente e o servidor devem usar o mesmo idioma
* Cada instância do Campaign opera em um único idioma
* Para instalações em inglês, você pode escolher entre inglês americano ou inglês do Reino Unido (eles diferem nos formatos de data e hora)

**Interface do usuário da Web do Campaign:**

* Os usuários podem alterar o idioma da interface de maneira independente por meio das preferências de perfil
* Vários idiomas são suportados com formatação específica de localidade para datas, horas e números
* Sua preferência de idioma da interface do usuário da Web é independente do idioma do servidor do Campaign e do console do cliente


**Tópicos relacionados:**

[Alterar idioma na interface do usuário da Web do Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Introdução ao console do cliente do Campaign](connect.md)

+++

+++ O que é o Painel de controle do Campaign e como faço para acessá-lo?

O Painel de controle do Campaign é uma interface administrativa baseada na Web que ajuda os administradores do Campaign a aumentar a eficiência, gerenciando configurações e monitorando o uso em instâncias do Campaign. Ele fornece recursos de autoatendimento para gerenciar configurações críticas de instâncias sem entrar em contato com o Suporte da Adobe.

**Principais recursos:**

* **Gerenciamento de subdomínio** - Delegar e gerenciar subdomínios, monitorar certificados SSL
* **Monitoramento de armazenamento** - Rastreie o uso do banco de dados e evite problemas de armazenamento
* **Gerenciamento de SFTP** - Monitorar o armazenamento SFTP, gerenciar incluis na lista de permissões de IP e chaves SSH
* **Configurações de instância** - Configurar incluis na lista de permissões de IP, gerenciar permissões de URL, examinar detalhes da instância
* **Monitoramento de perfis ativos** - Rastrear o uso do perfil ativo em relação a direitos
* **Monitoramento de desempenho** - Monitorar o desempenho do banco de dados e do fluxo de trabalho
* **Entregabilidade de email** - Configure o DMARC, o BIMI e outros registros de autenticação

**Requisitos de acesso:**

* **Somente usuários administradores** - O Painel de Controle é restrito a usuários com direitos de Administrador
* **Autenticação do Adobe IMS** - Acesse pelo Adobe Experience Cloud com sua Adobe ID
* **Serviços gerenciados de nuvem do Campaign v8** - Disponível somente para instâncias hospedadas

**Recursos adicionais:**

[Documentação do Painel de Controle](https://experienceleague.adobe.com/pt-br/docs/control-panel/using/control-panel-home){target="_blank"} | [Vídeos tutoriais sobre o Painel de Controle do Campaign](https://experienceleague.adobe.com/en/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ Como posso configurar recursos de rastreamento na minha instância do Campaign?

O Campaign v8 fornece um rastreamento abrangente para monitorar as interações do recipient com suas mensagens. O rastreamento requer a configuração adequada das configurações de instância e mensagem.

**O que você pode rastrear:**

* **Aberturas de email** - Via pixel de rastreamento (imagem transparente 1x1)
* **Cliques de link** - Todas as URLs convertidas automaticamente em links rastreados
* **Cancelar assinatura** - Rastreamento de link para opção de não participação
* **Exibições da página espelhada** - Quando os destinatários exibem a versão da Web
* **Parâmetros personalizados** - Adicione dados de rastreamento a URLs para análise avançada

**Etapas de configuração principais:**

1. Configurar o URL do servidor de rastreamento nas configurações da instância (gerenciado pelo Adobe para v8)
2. Ativar rastreamento nas propriedades de entrega
3. Configurar o rastreamento de links individuais ou de todos os links automaticamente
4. Definir período de validade de rastreamento e retenção de log

**Prática recomendada:** sempre teste o rastreamento com provas antes de enviar ao público principal para garantir que os links funcionem corretamente e os dados sejam capturados.

**Tópicos relacionados:**

[Rastrear e monitorar entregas](tracking.md) | [Configurar links rastreados](../send/email.md)

+++

+++ Como configurar a capacidade de entrega de emails?

A capacidade de entrega de email depende da configuração técnica, da qualidade do conteúdo e da reputação do remetente. O Campaign v8 fornece ferramentas e configurações para otimizar a inserção da caixa de entrada.

**Etapas de configuração essenciais:**

* **Autenticação de domínio** - Configure os registros SPF, DKIM e DMARC para verificar seu domínio de envio
* **Aquecimento de IP** - Aumente gradualmente o volume de envio em novos IPs para criar reputação
* **Configuração do remetente** - Use endereços e nomes de remetente consistentes e reconhecíveis
* **Gerenciamento de rejeição** - Configure regras de quarentena para lidar com rejeições permanentes e temporárias automaticamente
* **Loops de comentários** - Configure o tratamento de reclamações para gerenciar relatórios de spam

**Práticas recomendadas de conteúdo:**

* Teste emails com o SpamAssassin para verificar a pontuação de spam
* Manter a proporção adequada de texto para imagem
* Incluir versão de texto sem formatação ao lado do HTML
* Sempre fornecer link para cancelar inscrição
* Evite palavras de acionamento de spam e uso excessivo de maiúsculas e minúsculas

**Monitoramento:** use os relatórios de capacidade de entrega do Campaign para rastrear taxas de devolução, taxas de reclamação e posicionamento na caixa de entrada. Para o Campaign v8, a Adobe fornece otimização de capacidade de entrega no nível da infraestrutura.

**Tópicos relacionados:**

[Sobre a capacidade de entrega no Campaign](../send/about-deliverability.md) | [Guia de Práticas Recomendadas de Entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR){target="_blank"}

+++

+++ A quais bancos de dados externos posso conectar o Campaign?

O Campaign v8 oferece suporte a conexões Federated Data Access (FDA) com os principais sistemas de banco de dados corporativos (bancos de dados em nuvem, bancos de dados corporativos, data warehouses, plataformas de big data).

As versões de banco de dados compatíveis e os requisitos de conexão variam. Verifique a [Matriz de compatibilidade](compatibility-matrix.md) da sua versão do Campaign v8 para confirmar o suporte para bancos de dados específicos e garantir o licenciamento adequado para conectores FDA.

Consulte [Configurar conexões FDA](../connect/fda.md)

+++

+++ O Adobe Campaign pode se integrar a sistemas de CRM?

Sim. O Campaign fornece conectores CRM nativos para sincronização bidirecional com os principais sistemas de CRM. Sincroniza dados de contato, clientes potenciais, contas, logs do delivery, dados de rastreamento e métricas de envolvimento. Suporta modos de sincronização programados, manuais e em tempo real (via API).

Use o assistente do conector CRM do Campaign para mapear campos, selecionar tabelas e agendar sincronização. Verifique a [Matriz de Compatibilidade](compatibility-matrix.md) para obter as versões do CRM com suporte.

**Tópicos relacionados:**

[Configuração do conector do CRM](../connect/crm.md) | [Atividades do fluxo de trabalho do CRM](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html){target="_blank"}

+++

+++ Como limpar o cache do console do cliente?

Limpar o cache do console do cliente resolve muitos problemas comuns de exibição e funcionalidade. O cache armazena arquivos de configuração locais que às vezes podem se tornar corrompidos ou desatualizados.

**Quando limpar o cache:**

* Os novos elementos de marca (logotipos, cores) não são exibidos corretamente
* Falha inesperada nas funções de exportação/importação
* Elementos de interface não atualizados após alterações de configuração
* Problemas de desempenho ou resposta lenta do console
* Depois de atualizar para uma nova versão do console do cliente

**Etapas para limpar o cache:**

1. Abra o console do cliente do Campaign
2. Ir para o menu **[!UICONTROL File]**
3. Selecionar **[!UICONTROL Clear the local cache...]**
4. Confirmar a ação quando solicitado
5. Reinicie o console do cliente

Saiba mais em [Instalar e configurar o console do cliente](connect.md)

+++

+++ Posso definir as configurações da interface do usuário?

Sim. Os administradores do Campaign podem personalizar a interface do usuário para corresponder à identidade visual organizacional e otimizar a experiência do usuário. Defina as configurações no nível da instância ou do usuário.

**O que você pode personalizar:**

* **Identidade visual** - Logotipo, cores e elementos de identidade visual
* **Exibições padrão** - Layout da página inicial, visibilidade da estrutura de pastas
* **Configurações de lista** - Colunas padrão, ordem de classificação, filtros em listas de dados
* **Navegação** - Atalhos e itens de menu disponíveis
* **Configurações regionais** - Formatos de data/hora, formatos de número, fusos horários
* **Notificações** - Alertas de email, notificações no aplicativo, alertas de fluxo de trabalho

**Níveis de configuração:**

* **Toda a instância** - Aplicar a todos os usuários (requer direitos de administrador)
* **Específico do usuário** - Preferências individuais e configurações pessoais

**Tópicos relacionados:**

[Definir configurações da interface do usuário](../config/ui-settings.md) | [Permissões de usuário](gs-permissions.md)

+++

+++ Posso criar campos e tabelas personalizados?

Sim. O modelo de dados flexível do Campaign permite estender esquemas integrados com campos personalizados e criar tabelas totalmente novas para atender às suas necessidades comerciais específicas.

**O que você pode personalizar:**

* **Adicionar campos às tabelas existentes** - Estender tabela de destinatários com pontos de fidelidade, preferências personalizadas, IDs externas
* **Criar novas tabelas personalizadas** - Armazenar produtos, transações, camadas de fidelidade, entidades personalizadas
* **Definir relações** - Vincular tabelas personalizadas a tabelas existentes do Campaign
* **Estender formulários** - Atualizar interface do usuário para exibir e editar campos personalizados

**Casos de uso comuns:**

* Armazenar atributos de perfil adicionais (valor vitalício do cliente, loja preferencial, status do VIP)
* Gerenciar catálogos de produtos com atributos personalizados
* Rastrear eventos e interações personalizados
* Integrar IDs de sistema externas para sincronização de dados
* Criar modelos de dados específicos do setor (varejo, finanças, viagens)

**Tópicos relacionados:**

[Estender modelo de dados](../dev/extend-schema.md) | [Estrutura de esquema](../dev/schemas.md) | [Práticas recomendadas do modelo de dados](../dev/datamodel-best-practices.md)

+++

## Relatórios {#reporting}

Obtenha insights sobre os recursos de relatórios do Campaign, incluindo relatórios internos, relatórios personalizados e ferramentas de análise de dados como cubos.

+++ Como posso criar novos relatórios?

O Campaign oferece várias opções de relatórios dependendo das suas necessidades e especialização técnica: relatórios integrados, análise descritiva, relatórios personalizados no console do cliente e cubos.

**Opções de relatório:**

* **Relatórios internos** - Relatórios de rastreamento, campanha e entrega prontos para uso acessíveis a partir da guia **[!UICONTROL Reports]**
* **Análise descritiva** - Relatórios estatísticos rápidos sobre quaisquer dados com uma interface orientada por assistente
* **Relatórios personalizados** - Relatórios avançados criados por usuários técnicos usando o editor de relatórios
* **Cubos** - Exploração de dados multidimensionais e análise de tabela dinâmica

**Importante:** o Campaign foi projetado para relatórios de operações de marketing, não como uma ferramenta especializada de business intelligence. Para necessidades analíticas complexas, considere a integração com o Adobe Analytics ou plataformas de BI dedicadas.

**Tópicos relacionados:**

[Introdução aos relatórios](../reporting/gs-reporting.md) | [Relatórios de interface do usuário da Web do Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ Como posso criar e compartilhar relatórios de estatística sobre populações?

Use a ferramenta de análise descritiva do Campaign para gerar rapidamente relatórios estatísticos sobre quaisquer dados de população. Este recurso orientado por assistente ajuda a analisar distribuições, tendências e padrões sem conhecimento técnico.

**O que você pode analisar:**

* Detalhamentos demográficos e de segmentação de recipients
* Métricas de desempenho e taxas de resposta do Campaign
* Distribuição de atributos de perfil (idade, local, preferências)
* Estatísticas de entrega e padrões de engajamento
* Valores de campo personalizados e métricas de qualidade de dados

**Como criar:** Selecione qualquer lista ou resultado de consulta → Clique com o botão direito → **[!UICONTROL Actions > Analyze]** → Escolha o tipo de análise (qualitativa ou quantitativa) → Configurar opções de exibição → Gerar relatório.

**Compartilhamento:** exporte relatórios para Excel/PDF ou salve-os na pasta **[!UICONTROL Reports]** para obter acesso à equipe com as permissões apropriadas.

Saiba mais sobre [Análise descritiva](../reporting/built-in-reports.md)

+++

+++ Como posso criar relatórios avançados sobre os meus dados?

Use o console do cliente para criar relatórios personalizados avançados com recursos de análise complexos.

No console do cliente, é possível:

* Criar relatórios complexos usando consultas SQL e cálculos personalizados
* Criar relatórios de várias páginas com gráficos, tabelas e tabelas dinâmicas
* Criar formatação condicional e conteúdo dinâmico
* Acessar o modelo de dados completo do Campaign e os bancos de dados externos (FDA)

Saiba como [Criar relatórios personalizados (console do cliente)](../reporting/custom-reports.md)

+++

+++ O que é um cubo e como posso usá-lo para relatórios?

Os cubos são estruturas de dados multidimensionais que permitem aos usuários empresariais explorar e analisar dados do Campaign por meio de tabelas dinâmicas sem habilidades técnicas. Considere-os como modelos de dados pré-configurados que simplificam relatórios complexos. Essa ferramenta de relatórios está disponível no console do cliente e na interface do usuário da Web do Campaign.

* Os usuários técnicos criam e configuram cubos que definem dimensões (tempo, geografia, canais) e medidas (aberturas, cliques, receita)
* Usuários empresariais selecionam um cubo ao criar relatórios e arrastam e soltam dimensões para explorar dados
* Os dados são agregados e calculados automaticamente com base na configuração do cubo
* Os resultados podem ser exibidos como tabelas dinâmicas, gráficos ou exportados para o Excel

Saiba como [Explorar dados com cubos](../reporting/gs-cubes.md)

+++

+++ Posso criar um relatório com base em respostas a uma pesquisa online?

Sim! O Campaign inclui um módulo de Pesquisa que permite criar questionários online e gerar relatórios integrados sobre as respostas da pesquisa.

**Importante:** o gerenciamento de pesquisas não está disponível em implantações do Campaign v8 Enterprise (FFDA). [Saiba mais](../architecture/enterprise-deployment.md).

**Recursos da pesquisa:**

* Criar questionários online com várias páginas e tipos de perguntas
* Coletar respostas no banco de dados ou em variáveis locais
* Exibir o rastreamento das respostas da pesquisa em tempo real
* Gerar relatórios dedicados sobre respostas da pesquisa (detalhamento por pergunta, estatísticas gerais)
* Exportar respostas da pesquisa para Excel, PDF ou CSV para análise adicional
* Usar dados de pesquisa em workflows para construção do target para personalizar campanhas

**Análise avançada:**

* Acessar respostas de pesquisa da guia **[!UICONTROL Responses]** e exportar dados
* Use a atividade **[!UICONTROL Survey responses]** em fluxos de trabalho para direcionar destinatários com base em suas respostas
* Combinar dados da pesquisa com outros dados do Campaign para segmentação e personalização
* Criar relatórios e cubos personalizados para análise de pesquisa multidimensional

**Tópicos relacionados:**

[Introdução às pesquisas](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Relatórios de pesquisa](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ Como posso compartilhar o acesso aos meus relatórios?

Controle a visibilidade do relatório por meio de permissões de pasta e direitos nomeados no Campaign.

**Métodos de controle de acesso:**

* **Permissões de pasta** - Coloque relatórios em pastas com acesso apropriado para grupos de usuários
* **Direitos nomeados** - Atribuir direitos para exibir, criar ou modificar relatórios
* **Contexto de exibição** - Define onde os relatórios aparecem (pasta de relatórios, guias de campanha, telas de entrega)

**Configuração:** Salvar relatório em pasta específica → Configurar acesso à pasta para grupos de operadores → Definir propriedades do relatório e exibir contexto.

**Tópicos relacionados:**

[Relatórios personalizados](../reporting/custom-reports.md) | [Permissões de usuário](gs-permissions.md)

+++

+++ Posso exportar relatórios em diferentes formatos?

Sim, o Campaign oferece suporte a vários formatos de exportação para relatórios do console do cliente e da interface da Web, permitindo fácil compartilhamento com as partes interessadas e integração com outras ferramentas.

**Formatos de exportação disponíveis:**

* **Excel (.xlsx)** - Recomendado para manipulação de dados, análise adicional e tabelas dinâmicas
* **PDF** - Ideal para apresentações, resumos executivos e relatórios impressos
* **CSV** - Perfeito para importações de dados em outros sistemas e ferramentas de BI
* **OpenDocument (.ods)** - Formato de planilha de código aberto
* **XML** - Para integrações de sistema e processamento automatizado

**Como exportar:**

* **Console do cliente:** Abrir relatório → Clicar no botão **[!UICONTROL Export]** → Escolher formato → Salvar arquivo
* **Interface do usuário da Web:** Abrir painel → Clicar no ícone de exportação → Selecionar formato → Baixar
* **Exportações automatizadas:** agende exportações regulares usando fluxos de trabalho com atividades de exportação

**Práticas recomendadas:**

* Usar o Excel para relatórios que exigem análise e anotações da parte interessada
* Use o PDF para relatórios estáticos enviados a executivos ou arquivados para fins de conformidade
* Use o CSV para integrações com data warehouses ou ferramentas de análise externas
* Testar relatórios exportados para garantir a formatação e a precisão dos dados

**Tópicos relacionados:**

[Relatórios personalizados](../reporting/custom-reports.md) | [Relatórios de interface do usuário da Web do Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Desenvolvedores {#developers}

Acesse informações técnicas para desenvolvedores, incluindo detalhes do modelo de dados, esquemas, APIs e recursos de personalização.

+++ Qual é o modelo de dados do Campaign?

O modelo de dados do Campaign é uma estrutura de banco de dados relacional orientada por esquemas que consiste em tabelas integradas (recipients, deliveries, campanhas) que podem ser estendidas para as suas necessidades comerciais.

**Conceitos-chave:** Esquemas (definições XML), tabelas internas, links (relações), enumerações (listas de valores), extensões (campos/tabelas personalizados).

**Esquemas principais:** Destinatário (`nms:recipient`), Entrega (`nms:delivery`), Fluxo de Trabalho (`xtk:workflow`), Campanha (`nms:operation`), Logs de rastreamento.

Entender o modelo de dados é essencial para fluxos de trabalho, consultas, extensões de esquema e integrações.

**Tópicos relacionados:**

[Modelo de dados do Campaign](../dev/datamodel.md) | [Práticas recomendadas do modelo de dados](../dev/datamodel-best-practices.md)

+++

+++ Como trabalhar com esquemas do Campaign?

Os esquemas definem a estrutura de dados do Campaign em formato XML, especificando a estrutura da tabela, as propriedades do campo, os relacionamentos, os índices e o controle de acesso.

**Trabalhando com esquemas:**

* **Exibir:** Acesso via **[!UICONTROL Administration > Configuration > Data schemas]**
* **Estender:** criar esquemas de extensão (por exemplo, `cus:recipient`) para adicionar campos personalizados sem modificar os esquemas principais
* **Criar:** Criar novas tabelas para dados específicos de negócios
* **Atualizar:** Aplicar alterações via **[!UICONTROL Tools > Advanced > Update database structure]**

**Usuários comuns**: adicionar campos personalizados à tabela de destinatários, criar tabelas personalizadas, definir relações, implementar modelos específicos de negócios.

**Importante:** nunca modifique esquemas internos diretamente. Sempre use esquemas de extensão para compatibilidade de atualização.

**Tópicos relacionados:**

[Introdução a esquemas](../dev/schemas.md) | [Estender um esquema](../dev/extend-schema.md)

+++

+++ Como usar uma tabela de destinatários personalizada?

Use uma tabela de recipient personalizada ao direcionar contas B2B, dados de assinante separados, sistemas externos ou arquiteturas de várias marcas em vez da tabela de recipient padrão.

**Implementação:** crie um esquema personalizado com campos obrigatórios (email, chave primária, exclusões) → Configure target mappings → Atualize os modelos de entrega → Adapte fluxos de trabalho/consultas.

**Considerações principais:** deve incluir campos de entrega obrigatórios, fluxos de trabalho/formulários que precisam de adaptação, teste crítico antes da migração de produção.

**Prática recomendada:** primeiro estenda a tabela de destinatários padrão. Use tabelas personalizadas somente quando for realmente necessário devido à maior complexidade.

**Tópicos relacionados:**

[Tabela de destinatários personalizada](../dev/custom-recipient.md) | [Mapeamentos do Target](../audiences/target-mappings.md)

+++

+++ Quais são as práticas recomendadas para definir consultas no Campaign?

O editor de consultas do Campaign cria consultas ao banco de dados visualmente sem SQL, usadas em atividades de fluxo de trabalho, direcionamento de entrega, listas, relatórios e filtros.

**Práticas recomendadas:**

* Comece simples - crie de forma incremental e teste cada etapa
* Usar dimensões de filtro - aproveitar relacionamentos de tabelas
* Otimizar o desempenho - indexar campos consultados, evitar cálculos complexos
* Reutilizar filtros predefinidos para fins de consistência
* Testar primeiro com amostras pequenas
* Consultas complexas de documento

**Padrões comuns:** abridores de entrega do Target, localizar contatos inativos, segmentar por comportamento, excluir destinatários anteriores.

**Acesso:** **[!UICONTROL Tools > Generic query editor]** para exploração ad hoc.

**Tópicos relacionados:**

[Editor de consultas](../start/query-editor.md) | [Atividade de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso importar um pacote de dados?

Importar pacotes via **[!UICONTROL Tools > Advanced > Import package]** no console do cliente. Os pacotes contêm configurações de campanha (esquemas, workflows, tipologias) e dados para implantar entre instâncias.

**Tipos de pacote:** Pacote de usuário (configurações personalizadas), Pacote de plataforma (fornecido pela Adobe), Pacote de dados (dados reais).

**Práticas recomendadas:** teste no desenvolvimento primeiro, faça backup antes de importar, exporte da mesma versão ou de uma versão mais antiga.

Saiba mais em [Trabalhar com pacotes de dados](../dev/packages.md)

+++

+++ Onde posso encontrar a lista de APIs do Campaign v8?

O Campaign v8 fornece APIs do SOAP (operações do console do cliente), APIs REST (integrações modernas) e APIs do JavaScript (script de fluxo de trabalho).

**Usos comuns**: integrar com CRM/ERP, automatizar campanhas, sincronizar dados, criar soluções de monitoramento, criar interfaces externas.

**Acesso:** [Documentação da API do Campaign v8](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=pt-BR){target="_blank"}

+++


+++ Como monitorar workflows da API?

As APIs do Campaign permitem controlar workflows de forma programática: iniciar, pausar/retomar, parar, status de consulta, recuperar logs e monitorar o progresso da atividade.

**Ponto de extremidade de API:** `POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Comandos:** `{"method":"start"}`, `{"method":"pause"}`, `{"method":"resume"}`, `{"method":"stop"}`

**Casos de uso:** crie painéis de monitoramento, implemente alertas automatizados, orquestre de agendadores externos, crie dependências entre instâncias e gere relatórios personalizados.

**Prática recomendada:** combine o monitoramento da API com a trilha de auditoria para obter uma governança abrangente.

Ver [Controlar fluxos de trabalho por meio da API](../dev/api/controlling-a-workflow.md)

+++

+++ Como posso atualizar a estrutura do banco de dados?

Após modificar os esquemas (adicionar campos, criar tabelas, alterar tipos de dados), atualize a estrutura do banco de dados físico via **[!UICONTROL Tools > Advanced > Update database structure]** para aplicar as alterações.

**Quando necessário:** Adicionar campos, criar/estender tabelas, modificar propriedades de campos, adicionar/remover links, criar índices.

**Importante:** faça backup primeiro, teste no desenvolvimento, planeje o tempo de inatividade para grandes alterações, coordene com o suporte da Adobe (Managed Cloud Services), observe que algumas alterações podem causar perda de dados.


**Tópicos relacionados:**

[Atualizar estrutura do banco de dados](../dev/update-database-structure.md) | [Estender esquema](../dev/extend-schema.md)

+++

## Privacidade {#privacy}

Entenda como o Adobe Campaign ajuda você a cumprir as regras de privacidade, como o GDPR e o CCPA, e gerenciar solicitações de titulares de dados.

+++ Quais são os principais conceitos de privacidade do Campaign?

O Campaign ajuda você a cumprir as regras de privacidade (GDPR, CCPA, PDPA, LGPD) por meio de ferramentas para gerenciar direitos, consentimento e retenção de dados do titular dos dados. Os principais conceitos incluem regulamentos de privacidade, identificação de dados pessoais, direitos do titular dos dados (acesso, exclusão, portabilidade), gerenciamento de consentimento e políticas de retenção de dados.

Como Controlador de dados, você é responsável por lidar com solicitações de titulares de dados, manter registros de consentimento e garantir o uso transparente dos dados.

Saiba mais sobre o [Gerenciamento de privacidade](../start/privacy.md)

+++

+++ Como garantir a conformidade com a privacidade no Campaign?

O Campaign fornece ferramentas para conformidade com a privacidade, mas a responsabilidade legal é sua. Trabalhe com o departamento jurídico do seu programa de privacidade.

**Ações essenciais:**

* Estabelecer processos para lidar com solicitações de titulares de dados (acesso, exclusão)
* Implementar o gerenciamento de consentimento com carimbos de data e hora e rastreamento de escopo
* Incluir links para cancelar inscrição em todos os emails de marketing
* Auditoria de fontes de dados e remoção de dados não utilizados
* Aplicar controles de acesso de menor privilégio

O Campaign oferece integração do Serviço principal de privacidade, rastreamento de consentimento, fluxos de trabalho de exclusão automatizados e trilhas de auditoria para conformidade.

Saiba mais sobre o [Gerenciamento de privacidade](../start/privacy.md)

+++

+++ Como coletar e gerenciar o consentimento do usuário no Campaign?

O consentimento válido requer um acordo ativo, específico, informado e revogável. Os usuários devem tomar medidas explícitas — sem caixas pré-marcadas ou silêncio como consentimento. Consentimentos separados para diferentes propósitos (desagregados), fornecer explicações claras e manter registros com carimbos de data e hora.

**Práticas recomendadas**: forneça opções de aceitação granulares, atualize o consentimento periodicamente, torne os centros de preferências fáceis de acessar e enquadre o consentimento como um aumento de confiança.

**Implementação técnica no Campaign:**

O Campaign fornece serviços de assinatura, centros de preferências, sinalizadores de recusa e campos de consentimento personalizados para rastrear o consentimento.

* Estender esquema do recipient para campos de consentimento (data, tipo, origem)
* Criar serviços de assinatura para cada tipo de consentimento
* Criar formulários web da central de preferências
* Usar fluxos de trabalho para impor o consentimento no direcionamento
* Manter trilhas de auditoria

Consulte o departamento jurídico para garantir que sua implementação atenda aos requisitos normativos.

**Tópicos relacionados:**

[Serviços de assinatura](../start/subscriptions.md) | [Privacidade e consentimento](../start/privacy.md#consent-retention-roles) | [Gerenciamento de privacidade](../start/privacy.md)

+++

+++ Quais dados são excluídos quando procuro uma solicitação de exclusão?

O Campaign exclui automaticamente todos os dados vinculados a um titular de dados: perfil do recipient, logs de delivery e rastreamento, dados personalizados com relacionamentos de propriedade, histórico de subscrição e dados de rastreamento Web.

**Como funciona:** o Campaign exclui todos os dados nos quais o link para o destinatário tem `integrity="own"` na definição do esquema, garantindo a exclusão em cascata nas tabelas relacionadas.

Você pode personalizar o escopo de exclusão modificando a integridade do link em esquemas, mas consulte o departamento jurídico primeiro. A exclusão é permanente e não pode ser desfeita.

**Tópicos relacionados:**

[Gerenciamento de privacidade](../start/privacy.md) | [Links de esquema](../dev/schemas.md)

+++

+++ As exclusões de privacidade afetam meus relatórios de entrega?

Não. Os relatórios de campanha são baseados em métricas agregadas pré-calculadas (total enviado, aberturas, cliques), não em consultas ativas em logs individuais. A exclusão de dados de destinatários individuais não altera as estatísticas agregadas históricas.

As estatísticas de entrega gerais e as métricas de desempenho permanecem intactas, enquanto os logs de rastreamento individuais e os detalhes pessoais são removidos. Dessa forma, você pode manter as análises de marketing e, ao mesmo tempo, respeitar os direitos do titular dos dados.

**Tópicos relacionados:**

[Gerenciamento de privacidade](../start/privacy.md) | [Relatórios](../reporting/gs-reporting.md)

+++

+++ Como evitar a reimportação de dados excluídos?

Você deve excluir os dados de todos os sistemas de origem, não apenas do Campaign. Os dados geralmente fluem de sistemas externos (CRM, comércio eletrônico, data warehouses).

**Ações necessárias:** identifique todas as fontes de dados, exclua dos sistemas de origem, adicione a listas de exclusão/supressão, atualize fluxos de trabalho de importação para respeitar sinalizadores de exclusão e documente o processo.

Como controlador de dados, você é responsável pela remoção completa dos dados em todo o seu ecossistema de tecnologia.

**Tópicos relacionados:**

[Gerenciamento de privacidade](../start/privacy.md) | [Importar fluxos de trabalho](../config/workflows.md)

+++

+++ Usuários excluídos podem aceitar novamente?

Sim. Os titulares de dados podem aceitar novamente após a exclusão. O Campaign cria um registro de recipient completamente novo sem link para dados excluídos anteriores; o perfil começa com uma tabulação limpa.

A trilha de auditoria do Campaign registra o evento de exclusão e a criação do novo perfil, demonstrando a conformidade e mostrando que a nova aceitação foi fornecida livremente após a exclusão.

**Tópicos relacionados:**

[Gerenciamento de privacidade](../start/privacy.md) | [Assinaturas](../start/subscriptions.md)

+++

## Ainda precisa de ajuda? {#get-help}

Não consegue encontrar o que você está procurando? Estes são recursos adicionais para ajudá-lo a ter sucesso com o Adobe Campaign v8.

### Suporte da comunidade

Conecte-se com outros usuários do Campaign e especialistas do Adobe para compartilhar conhecimento e obter respostas.

* **[Comunidade do Adobe Campaign](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** - Faça perguntas, compartilhe soluções e conecte-se com a comunidade do Campaign
* **[Fóruns do Experience League](https://experienceleaguecommunities.adobe.com/){target="_blank"}** - Procure discussões em todos os produtos da Adobe
* **[Horário comercial da comunidade do Campaign](https://experienceleague.adobe.com/){target="_blank"}** - Participe de sessões ao vivo com especialistas da Adobe

### Documentação e aprendizado

Acesse guias, tutoriais e materiais de treinamento abrangentes.

* **[Tutoriais do Campaign](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=pt-BR){target="_blank"}** - guias de vídeo passo a passo e tutoriais práticos
* **[Novidades](whats-new.md)** - Recursos e funcionalidades mais recentes
* **[Notas de versão](release-notes.md)** - Informações de versões atuais e anteriores
* **[Versões e atualizações](upgrades.md)** - Saiba mais sobre versões e atualizações do Campaign e como verificar sua versão

### Recursos técnicos

Encontre documentação técnica detalhada e recursos do desenvolvedor.

* **[APIs do Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=pt-BR){target="_blank"}** - Documentação de referência de API concluída
* **[Matriz de Compatibilidade](compatibility-matrix.md)** - Sistemas e versões com suporte
* **[Perguntas frequentes sobre Versões e Atualizações](upgrades.md#upgrades-faq)** - Verifique a sua versão e saiba mais sobre atualizações

### Suporte e serviços

Obtenha ajuda da equipe de suporte da Adobe e gerencie sua instância.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Registre casos de suporte e gerencie usuários
* **[Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Contate a equipe de suporte
* **[Painel de controle](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR){target="_blank"}** - Gerenciar as configurações da instância do Campaign
* **[Status do sistema](https://status.adobe.com/){target="_blank"}** - Verificar o status dos serviços da Adobe

### Treinamento e certificação

Aprimore suas habilidades com programas oficiais de treinamento e certificação da Adobe.

* **[Ajuda do Experience League](https://experienceleague.adobe.com/en/browse/campaign/campaign-v8){target="_blank"}** - Recursos de ajuda do Campaign v8 (Interface Web e console do cliente)
* **[Serviços de aprendizado digital da Adobe](https://learning.adobe.com/){target="_blank"}** - Cursos oficiais ministrados por instrutores e individualizados
* **[Certificação da Adobe Campaign](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - Valide sua experiência com a certificação profissional
* **[Caminhos de aprendizagem do Experience League](https://experienceleague.adobe.com/?lang=pt-BR#dashboard/learning){target="_blank"}** - jornadas de aprendizagem guiadas

### Outros recursos úteis

* **[Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=pt-BR){target="_blank"}** - Referência para usuários do Classic v7
* **[Documentação da interface da Web do Campaign](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Novo guia de interface da Web
* **[Práticas recomendadas de capacidade de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR){target="_blank"}** - Otimizar a entrega de emails

