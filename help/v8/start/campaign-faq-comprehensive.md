---
title: Perguntas frequentes sobre o Campaign v8
description: Obtenha respostas para perguntas comuns do Adobe Campaign v8 sobre instalação, configuração, mensagens, fluxos de trabalho e muito mais
feature: Overview
role: User
level: Beginner
keywords: Perguntas frequentes, Campaign v8, perguntas, respostas, ajuda, suporte, solução de problemas
hide: true
hidefromtoc: true
source-git-commit: 4b295f804e76074ed9ae57f115e0694c302835e3
workflow-type: tm+mt
source-wordcount: '12512'
ht-degree: 10%

---

# Perguntas frequentes {#faq}

Obtenha respostas rápidas para as perguntas mais comuns sobre o Adobe Campaign v8. Esteja você apenas começando ou procurando ajuda de configuração avançada, você encontrará respostas organizadas por tópico abaixo.

**Novo no Campaign?** Comece com [Perguntas Gerais](#general) e [Conceitos-Chave](#key-concepts).\
**Precisa de ajuda técnica?** Verifique [Desenvolvedores](#developers) e [Configurações do Campaign](#settings).\
**Não encontrou sua resposta?** Visite nossos [Fóruns da Comunidade](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} ou [contate o suporte](#get-help).

**Dica:** Use Ctrl+F (Cmd+F no Mac) para procurar palavras-chave específicas nesta página. Clique em qualquer pergunta para expandir a resposta.


## Perguntas gerais {#general}

Obtenha respostas para as perguntas mais comuns sobre o Adobe Campaign v8, incluindo como se conectar, atualizar e obter suporte.

+++ Como posso me conectar ao Campaign v8?

É necessário baixar e instalar o console do cliente do Campaign para se conectar ao Adobe Campaign.

[Clique aqui para saber mais](connect.md).

A partir da versão v8.6 do Campaign, você terá acesso à **interface de usuário da Web do Campaign**, disponível por meio do ambiente central do Adobe Experience Cloud. O Experience Cloud é a família integrada de aplicativos de marketing digital, produtos e serviços da Adobe.

Saiba como se conectar à Adobe Experience Cloud e acessar a interface do Adobe Campaign Web [nesta página](campaign-ui.md#ac-web-ui).

Saiba mais na [documentação da interface do Adobe Campaign Web](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

**Solução de problemas de conexão:**

* Verifique se as credenciais do Adobe ID estão corretas
* Verifique se a versão do console do cliente corresponde à versão do servidor
* Verificar as configurações de firewall e conectividade de rede
* Limpe o cache do console do cliente em caso de problemas
* Entre em contato com o administrador para verificar suas permissões de usuário

**Tópicos relacionados:**

* [Instalar o console do cliente](connect.md)
* [Interface do usuário do Campaign](campaign-ui.md)
* [Permissões de usuário](gs-permissions.md)

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

+++ Como posso atualizar o Campaign para a versão mais recente?

O Adobe Campaign é atualizado regularmente. Versões secundárias são lançadas a cada ano com novos recursos, melhorias e correções. Além disso, periodicamente liberamos builds apenas com correções cumulativas.

Essa frequência regular de atualizações tem como objetivo disponibilizar a você o que há de melhor e mais recente, mantendo seu ambiente seguro e melhorando sua experiência com nosso produto. É por isso que acreditamos que é essencial executar a versão mais recente do Adobe Campaign.

**Observação:** como usuário do Managed Cloud Services, sua instância foi atualizada pela Adobe com novas versões.

Saiba mais sobre [versões e atualizações do Campaign](upgrades.md).

+++

+++ Como configurar a capacidade de entrega de emails?

A capacidade de entrega de email, um componente crítico para o sucesso do programa de marketing dos remetentes, é caracterizada por critérios e regras em constante mudança. Navegar efetivamente neste mundo digital requer o ajuste regular de sua estratégia de email, considerando as principais tendências de capacidade de entrega, para melhor alcançar seus públicos-alvo.

Consulte este manual para saber mais sobre [Práticas recomendadas de capacidade de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR){target="_blank"}

Consulte [este guia](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=pt-BR){target="_blank"} para saber como implementar a capacidade de entrega no Campaign

**Principais dicas de entrega:**

* Mantenha uma lista de email limpa e remova assinantes inativos regularmente
* Use a aceitação dupla para garantir destinatários engajados
* Monitorar a reputação do remetente e a reputação de IP
* Autentique seus emails com SPF, DKIM e DMARC
* Respeitar solicitações de cancelamento de inscrição imediatamente
* Teste seus emails antes de enviar para públicos grandes

**Tópicos relacionados:**

* [Sobre a capacidade de entrega](../send/about-deliverability.md)
* [Controlar conteúdo da mensagem](../send/control-message-content.md)
* [Monitorar a capacidade de entrega](../send/monitoring-deliverability.md)
* [SpamAssassin](../send/spamassassin.md)

+++

+++ Como posso garantir que minha entrega seja enviada sem erros?

Siga estas etapas para garantir um delivery bem-sucedido:

**Antes de enviar:**

* Execute a análise do delivery para detectar erros (personalização ausente, destinatários inválidos, problemas de conteúdo)
* Envie provas de teste para verificar a renderização e a personalização
* Revisar avisos durante a preparação
* Verificar contagem de população de destino

**Durante e após o envio:**

* Monitore o painel do delivery para obter estatísticas em tempo real (enviadas, entregues, devoluções, erros)
* Verificar status no nível de mensagem nos logs do delivery
* Rastrear taxa de sucesso, taxa de rejeição e mensagens de erro
* Revisar endereços em quarentena

**Práticas recomendadas:**

* Configurar alertas para limites de erro
* Usar ondas (envio em lote) para grandes volumes
* Testar primeiro com volumes pequenos
* Limpar regularmente o banco de dados do recipient
* Monitorar a reputação do remetente

Saiba mais sobre [monitoramento de entregas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=pt-BR){target="_blank"} e [práticas recomendadas de entrega](delivery-best-practices.md).

+++

+++ Posso monitorar a execução do fluxo de trabalho?

Sim. O Campaign fornece várias ferramentas para monitorar a execução do fluxo de trabalho:

* **Painel de fluxo de trabalho** - Exibir o status, o progresso e os erros em tempo real de cada atividade de fluxo de trabalho
* **[Logs de fluxo de trabalho](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}** - Acesse logs de execução detalhados para solucionar problemas
* **[Heatmap](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}** - Visualize a atividade do fluxo de trabalho e identifique gargalos de desempenho
* **[Trilha de auditoria](../reporting/audit-trail.md)** - Rastrear todas as modificações feitas nos fluxos de trabalho
* **[Alertas](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}** - Configurar notificações para falhas ou atrasos de fluxo de trabalho

Para monitorar um workflow, abra-o e clique na guia **Logs**. Atividades com falha são destacadas em vermelho e você pode exibir detalhes do erro clicando nelas.

Saiba mais sobre [monitoramento da execução do fluxo de trabalho](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} e [práticas recomendadas do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=pt-BR){target="_blank"}.

+++

+++ Com quais sistemas e componentes o Campaign v8 é compatível?

Você pode obter a lista de todos os sistemas e componentes compatíveis com a última build do Campaign na [Matriz de compatibilidade do Adobe Campaign ](compatibility-matrix.md).

+++

+++ Como posso baixar o Campaign?

Você pode obter o programa de instalação e o console do cliente do Centro de download da Adobe.

Como um usuário administrador, acesse Adobe [Distribuição de software](https://experience.adobe.com/#/downloads/content/software-distribution/br/campaign.html){target="_blank"} para baixar o Adobe Campaign.

Saiba mais sobre o Centro de Distribuição [nesta página](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=pt-BR){target="_blank"}.

+++

+++ Como posso registrar um problema?

A criação de um caso permite que você entre em contato com a Equipe de suporte ao cliente da Adobe sobre qualquer problema que você tiver com produtos da Adobe. Para ajudar a resolver ou solucionar problemas, o Adobe Admin Console permitirá que você fale com o Suporte ao cliente da Adobe.

Para registrar um problema ou iniciar uma sessão de chat nesse novo sistema, conecte-se ao [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}.

Esse sistema exige contas individuais para cada usuário, com as permissões corretas. Se você não conseguir fazer logon com sua Adobe ID, solicite acesso por meio da Experience League, e a equipe de Atendimento ao cliente resolverá seu problema o mais rápido possível. [Saiba mais](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Associe-se à Comunidade do Campaign: procure respostas em uma pergunta existente ou pergunte aos especialistas. [Participe da conversa](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}

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

+++ Qual é minha versão do Campaign?

Verifique a [versão e o número de build](upgrades.md#version) no menu **Ajuda > Sobre...** do console de cliente do Campaign.

+++

+++ Quais são as diferenças entre o Campaign Classic v7 e o Campaign v8?

O Campaign v8 é a versão de última geração do Campaign, projetada para o Managed Cloud Services. Ela traz melhorias significativas em infraestrutura, segurança, capacidade de entrega e monitoramento.

O Adobe Campaign v8 está disponível exclusivamente como um **Managed Cloud Service**, e não pode ser implantado em um ambiente local ou híbrido.

[Saiba mais sobre a transição do Campaign Classic v7 para o v8](v7-to-v8.md).

+++

+++ Como posso configurar as permissões do usuário?

Como administrador do Campaign, você pode configurar permissões para os usuários da sua organização.

Veja um conjunto de direitos e restrições que autorizam ou impedem:

* Acesso a determinadas funcionalidades
* Acessar certos dados
* Criar, modificar e/ou excluir dados

[Saiba mais](../start/gs-permissions.md) sobre permissões de usuário no Campaign v8.

**Tópicos relacionados:**

* [Introdução a permissões](gs-permissions.md)
* [Gerenciar permissões do usuário](manage-permissions.md)
* [Adicionar permissões em pastas](folder-permissions.md)

+++

+++ Como garantir a conformidade da privacidade com o Campaign?

O Adobe Campaign oferece um conjunto de ferramentas para ajudá-lo a estar em conformidade com privacidade para GDPR, CCPA e outras regulamentações de privacidade.

[Saiba mais](../start/privacy.md) sobre o gerenciamento de privacidade e as ferramentas e funcionalidades que a Adobe Campaign fornece para ajudá-lo a estar em conformidade com a privacidade.

+++

+++ Quais conceitos da interface do usuário do Campaign eu devo conhecer?

Consulte [esta seção](campaign-ui.md) para saber mais sobre as noções básicas da interface de usuário do Adobe Campaign.

A partir da versão v8.6 do Campaign, você também terá acesso à nova **interface de usuário da Web do Campaign**, disponível por meio do ambiente central do Adobe Experience Cloud.

[Saiba mais na documentação sobre a interface de usuário da Web do Adobe Campaign](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Como posso selecionar o público-alvo de minhas mensagens?

Com o Adobe Campaign, você pode usar estratégias diferentes para criar públicos-alvos e selecionar destinatários.

[Saiba mais](../audiences/gs-audiences.md) sobre como definir públicos no Campaign v8.

+++

+++ O que é um fluxo de trabalho?

O Adobe Campaign inclui fluxos de trabalho para organizar a gama completa de processos e tarefas em diferentes módulos do servidor de aplicativos. Esse ambiente gráfico abrangente permite criar processos, inclusive segmentação, execução de campanha, processamento de arquivos, participação humana, etc. O mecanismo de fluxo de trabalho executa e rastreia esses processos.

Você pode usar um fluxo de trabalho, por exemplo, para baixar um arquivo de um servidor, descompactar e importar registros contidos no banco de dados do Adobe Campaign.

Um fluxo de trabalho também pode envolver um ou mais operadores a serem notificados ou que podem fazer escolhas e aprovar processos. Dessa forma, é possível criar uma ação de entrega, atribuir uma tarefa a um ou mais operadores para trabalhar no conteúdo, especificar alvos e aprovar testes antes de iniciar a entrega.

[Saiba mais](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=pt-BR){target="_blank"} sobre fluxos de trabalho. Você também pode ler as [práticas recomendadas de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=pt-BR){target="_blank"}.

**Tópicos relacionados:**

* [Introdução aos fluxos de trabalho](../config/workflows.md)
* [Crie seu primeiro fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=pt-BR){target="_blank"}
* [Casos de uso de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}
* [Monitorar a execução do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=pt-BR){target="_blank"}

+++

+++ Como criar e enviar o primeiro email?

A criação do seu primeiro e-mail no Campaign v8 envolve várias etapas principais:

1. **Criar a entrega** - Comece criando uma nova entrega de email a partir de um modelo ou do zero
1. **Definir o público-alvo** - Selecione seus destinatários de destino usando consultas, listas ou fluxos de trabalho
1. **Criar o conteúdo** - Use o designer de email para criar sua mensagem com personalização
1. **Teste com provas** - Enviar emails de teste para validar o conteúdo e a personalização
1. **Analisar e enviar** - Execute a análise de entrega para verificar se há erros e, em seguida, envie seu email

O Campaign v8 oferece duas interfaces para a criação de email:

* **Console do cliente** - Aplicativo de desktop completo com recursos avançados
* **Interface do usuário da Web do Campaign** - Interface da Web moderna e intuitiva para criação mais rápida de email

[Saiba mais sobre design e validação de email](../send/email.md) no Campaign v8.

**Tópicos relacionados:**

* [Criar a primeira entrega](create-message.md) - guia passo a passo
* [Trabalhar com modelos de entrega](../send/create-templates.md) - Economizar tempo com modelos
* [Práticas recomendadas de entrega](delivery-best-practices.md) - Recomendações para o sucesso
* [Definir o conteúdo do email](../send/defining-the-email-content.md) - Opções de criação de conteúdo
* [Pré-visualização e provas](../send/preview-and-proof.md) - Testar antes de enviar
* [Configurar e enviar](../send/configure-and-send.md) - Etapas finais para enviar
* [Personalizar conteúdo](../send/personalize.md) - Adicionar personalização dinâmica

+++

+++ Como enviar mensagens SMS?

O envio de mensagens SMS com o Campaign v8 requer configuração inicial e, em seguida, segue um processo de delivery simples:

**Instalação Inicial (configuração única):**

1. **Configurar canal de SMS** - Defina as configurações de entrega de SMS e a conta externa
1. **Configurar conexão SMPP** - Conecte-se ao seu provedor de serviços SMS por meio do protocolo SMPP
1. **Testar a conexão** - Valide a conectividade com seu provedor de SMS
1. **Configurar o roteamento** - Define como as mensagens SMS são roteadas pelo seu provedor

**Criando e Enviando SMS:**

1. **Criar entrega de SMS** - Iniciar uma nova entrega de SMS a partir de um modelo
1. **Definir destinatários** - Selecione o público móvel usando campos de número de telefone
1. **Gravar conteúdo de SMS** - Crie sua mensagem (padrão de 160 caracteres ou mais com concatenação)
1. **Adicionar personalização** - Incluir campos dinâmicos específicos para cada destinatário
1. **Enviar provas** - Testar entrega de SMS para validar conteúdo e entrega
1. **Analisar e enviar** - Execute a análise e envie para seu público

**Principais recursos de SMS:**

* **Vários conectores SMPP** - Suporte para vários provedores e protocolos SMS
* **Relatórios de entrega** - Rastrear mensagens enviadas, entregues e com falha
* **Codificação de caracteres** - Suporte para GSM7, Unicode e caracteres especiais
* **Suporte a SMS longo** - Concatenação automática de mensagens para textos mais longos
* **SMS Bidirecional** - Gerenciar respostas de SMS de entrada com fluxos de trabalho

[Saiba mais sobre a configuração e envio de SMS](../send/sms/sms.md) no Campaign v8.

**Tópicos relacionados:**

* [Introdução ao SMS](../send/sms/sms.md) - Guia completo de SMS
* [Configurações de entrega de SMS](../send/sms/sms-delivery-settings.md) - Opções de configuração
* [Configurações de conta externa SMPP](../send/sms/smpp-external-account.md) - Configuração do provedor
* [Criar uma entrega de SMS](../send/sms/create-sms.md) - Criação passo a passo
* [Conteúdo de SMS](../send/sms/sms-content.md) - Diretrizes de design de conteúdo
* [Enviar provas de SMS](../send/sms/sms-proofs.md) - Testando SMS
* [Monitorar SMS](../send/sms/sms-monitor.md) - Rastrear e analisar entregas

+++

+++ Como enviar notificações por push?

O envio de notificações por push com o Campaign v8 envolve a configuração da integração de aplicativos móveis e a criação de notificações envolventes:

**Instalação Inicial (configuração única):**

1. **Configurar canal de notificação por push** - Definir configurações de canal de notificação por push no Campaign
1. **Integrar o Campaign SDK** - Adicionar o Adobe Campaign SDK ao aplicativo móvel (ou usar a Coleção de dados)
1. **Configurar aplicativo móvel** - Registre seus aplicativos iOS e Android no Campaign
1. **Configurar certificados** - Configurar o certificado APNs (iOS) e a chave FCM (Android)
1. **Registro de teste** - Verifique se os dispositivos podem registrar e receber tokens

**Criando e Enviando Notificações por Push:**

1. **Criar entrega por push** - Iniciar uma nova notificação por push de um modelo
1. **Selecionar plataforma** - Escolha iOS, Android ou ambas as plataformas
1. **Definir público-alvo** - Assinantes de aplicativos de destino que usam dados de assinatura de aplicativos móveis
1. **Notificação de design** - Criar título, mensagem e conteúdo de mídia avançada
1. **Configurar comportamento** - Definir ações de clique, deep links e dados personalizados
1. **Enviar notificações de teste** - Validar em dispositivos reais antes de enviar
1. **Analisar e enviar** - Revise o direcionamento e envie para seu público móvel

**Recursos de notificação por push:**

* **Notificações por push avançadas** - Incluir imagens, vídeos e botões interativos (iOS e Android)
* **Personalization** - Conteúdo dinâmico baseado no perfil do usuário e no comportamento
* **Deep linking** - Direciona os usuários para telas ou conteúdo específicos do aplicativo
* **Agendamento** - Enviar em horários ideais com base no fuso horário do usuário
* **Teste A/B** - Testar mensagens diferentes e otimizar participação
* **Rastreamento** - Monitorar aberturas, cliques e conversões

**Recursos específicos da plataforma:**

* **iOS** - Notificações silenciosas, categorias de notificação, personalização de som
* **Android** - Modelos avançados de push, canais de notificação, layouts personalizados

[Saiba mais sobre a configuração de notificação por push](../send/push-settings.md) no Campaign v8.

**Tópicos relacionados:**

* [Criar e enviar notificações por push](../send/push.md) - Guia de push concluído
* [Configurar canal de notificação por push](../send/push-settings.md) - Configuração de canal
* [Criar um push avançado do Android](../send/rich-push-android.md) - Notificações avançadas do Android
* [Criar um push avançado do iOS](../send/rich-push-ios.md) - Notificações avançadas do iOS
* [Configurar com Coleção de Dados](../send/push-data-collection.md) - Método de integração revisado moderno
* [Rastrear e monitorar](tracking.md) - Analisar desempenho de push

+++

+++ Como criar uma landing page?

Você pode usar o editor de conteúdo digital do Adobe Campaign para criar páginas de aterrissagem e definir o mapeamento com campos de banco de dados.

[Saiba mais](../dev/landing-pages.md) na documentação do Campaign v8.

Você também pode usar a interface da Web do Campaign para criar e publicar páginas de aterrissagem - [Saiba mais](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ Como posso rastrear entregas?

Você pode rastrear e monitorar as entregas feitas com o Campaign v8 por meio de [relatórios de entrega](../reporting/delivery-reports.md) exclusivos.

Saiba mais sobre a gestão de rastreamento no Campaign [nesta página](../start/tracking.md).

**Tópicos relacionados:**

* [Rastrear e monitorar mensagens](tracking.md)
* [Relatórios de entrega](../reporting/delivery-reports.md)
* [Entender as falhas de entrega](../send/delivery-failures.md)
* [Configurar links rastreados](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"} (documentação do Campaign Classic v7)

+++

+++ Como traduzir uma mensagem de erro?

Há uma mensagem de erro exibida em outro idioma? Todas as mensagens de erro com suas devidas traduções estão listadas [nesta página](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=pt-BR){target="_blank"}.

+++

+++ Posso criar um formulário web e coletar respostas no Campaign?

Sim. Crie formulários web usando o **Campaign Web Applications &amp; Forms** (console de cliente) para obter controle total sobre a lógica e a validação do formulário, ou use as **Páginas de Aterrissagem do Campaign** (interface da Web) com uma interface de arrastar e soltar moderna para assinaturas e geração de clientes potenciais. Ambos coletam dados diretamente no Campaign e se integram a fluxos de trabalho para ações automatizadas.

[Saiba mais sobre aplicativos e formulários Web](../dev/webapps.md) | [Páginas de aterrissagem da interface do usuário da Web do Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8 versus versões anteriores {#v7-differences}

Entenda as principais diferenças entre o Campaign v8 e as versões anteriores (Classic v7 e Standard), incluindo arquitetura, implantação, caminhos de migração e alterações de recursos. Quer você venha do Campaign Classic v7 ou do Campaign Standard, saiba as novidades e saiba como fazer a transição sem problemas.

+++ Quais são as principais diferenças entre o Campaign v8 e as versões anteriores?

O Campaign v8 é uma reformulação completa do Adobe Campaign, projetada para a arquitetura moderna nativa em nuvem e que traz melhorias significativas em relação ao Campaign Classic v7 e ao Campaign Standard:

**Modelo de Implantação:**

* **v8:** Managed Cloud Services somente - totalmente hospedado e gerenciado pela Adobe
* **v7/Standard:** Opções locais, híbridas ou hospedadas disponíveis
* **Benefício:** gerenciamento de infraestrutura zero, dimensionamento automático, segurança de nível empresarial, monitoramento pró-ativo

**Arquitetura e desempenho:**

* **v8:** arquitetura Full FDA (FFDA) aprimorada com banco de dados PostgreSQL
* **v8:** Taxa de transferência de processamento em lote atingindo até **20 milhões de operações por hora**
* **v8:** Taxa de transferência de mensagem transacional de **1 milhões por hora**
* **v8:** Exploração de dados em tempo real e construção rápida de público-alvo (minutos vs. horas)
* **Benefício:** melhor desempenho para operações de larga escala e campanhas complexas

**Interface de Usuário:**

* **v8:** Nova **interface da Web do Campaign** junto com o console do cliente - intuitiva, acessível, ideal para profissionais de marketing
* **v8:** design moderno e responsivo com recursos de arrastar e soltar
* **v8:** fluxos de trabalho simplificados de criação e gerenciamento de campanhas
* **v8:** compartilha muitas semelhanças com a interface do Campaign Standard
* **Benefício:** integração mais rápida, execução mais fácil da campanha, melhor acessibilidade, curva de aprendizado mínima

**Novos Recursos de Chave:**

* **Notificações por push avançadas** com imagens, vídeos, botões interativos, carrosséis e timers
* **Assistente de IA** para geração de conteúdo (email, SMS, push) com pontuação de alinhamento de marca
* **Infraestrutura de SMS atualizada (SMS v2.0)** com confiabilidade e compatibilidade aprimoradas
* **Integração do Adobe Experience Manager as a Cloud Service** para um gerenciamento de conteúdo simples
* **Relatórios aprimorados** incluindo Relatórios dinâmicos para usuários do Campaign Standard

**Atualizações e manutenção:**

* **v8:** Atualizações automáticas gerenciadas pelo Adobe - versão estável sempre ativa com modelo de entrega contínua
* **v7/Standard:** Planejamento e execução de atualização manual necessários
* **Benefício:** redução da carga de manutenção, acesso imediato a novos recursos, sem tempo de inatividade

**APIs e integração:**

* **v8:** APIs REST modernas com desempenho e confiabilidade aprimorados
* **v8:** Integração perfeita com o Adobe Experience Cloud e o Adobe Experience Platform
* **Vantagem:** integrações mais fáceis, melhor interoperabilidade, práticas modernas de desenvolvimento

[Saiba mais sobre os principais recursos do Campaign v8](whats-new.md)

**Tópicos relacionados:**

* [Do Campaign Classic v7 para o v8](v7-to-v8.md) | [Guia de transição do v7 para o v8](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}
* [Do Campaign Standard para a v8](acs-to-v8.md) | [Transição do Campaign Standard](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Guia de adoção do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Matriz de recursos do Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Arquitetura do Campaign v8](../architecture/architecture.md)
* [Medidas de proteção e limitações](ac-guardrails.md)

+++

+++ Devo migrar do Campaign Classic v7 ou Campaign Standard para o v8?

O **Campaign v8 é ideal para organizações que precisam:**

* **Campanhas de alto volume** - Envie milhões de mensagens com desempenho e confiabilidade aprimorados (20 milhões de operações/hora)
* **Escalabilidade corporativa** - Aumente seu banco de dados e suas campanhas sem preocupações com o desempenho
* **Moderna interface da Web** - Interface da Web do Campaign intuitiva e responsiva para criação mais rápida de campanhas e melhor experiência do usuário
* **Benefícios nativos em nuvem** - Aproveite as atualizações automáticas, a infraestrutura gerenciada, o dimensionamento elástico e o monitoramento pró-ativo
* **Suporte de longo prazo** - O Campaign v8 é a plataforma estratégica da Adobe com suporte estendido, enquanto as versões anteriores atingirão o Fim do Suporte nos próximos anos
* **Redução das despesas gerais de TI** - Elimine o gerenciamento da infraestrutura e o planejamento de atualizações
* **Recursos avançados** - Assistente de IA, push avançado, SMS aprimorado, integração com o Adobe Experience Platform

**Para usuários do Campaign Standard:**

Os usuários do Campaign Standard agora estão qualificados para a transição para o Campaign v8 Managed Cloud Services. Os principais benefícios incluem:

* **Interface familiar** - A interface da Web do Campaign compartilha muitas semelhanças com o Campaign Standard, minimizando a curva de aprendizado
* **Paridade de recursos** - Os principais recursos do Campaign Standard foram adicionados à v8 (Relatórios Dinâmicos, Marcas Centralizadas, APIs REST, Páginas de Aterrissagem, Fragmentos Visuais)
* **Suporte avançado** - Assistência de alto nível com transição suave e monitoramento contínuo da plataforma
* **Migração de dados** - Todos os seus dados da Campaign Standard são importados com o mínimo de interrupção
* **Experiência de usuário consistente** - Continue trabalhando com fluxos de trabalho e interface familiares

**Para usuários do Campaign Classic v7:**

O Campaign v8 traz melhorias substanciais, mantendo os principais recursos do Campaign:

* **Interface dupla** - Acesse o poderoso console do cliente e a interface moderna da Web do Campaign
* **Melhor desempenho** - Desempenho de consulta e processamento de dados significativamente melhorados
* **Vantagens da nuvem** - Atualizações automáticas, patches de segurança, backup/recuperação gerenciados pela Adobe
* **Arquitetura moderna** - arquitetura FFDA aprimorada com PostgreSQL para melhor escalabilidade

**Quando considerar a migração:**

* Sua instância atual do Campaign lida com grandes volumes de dados (milhões de perfis)
* Você está tendo problemas de desempenho com fluxos de trabalho complexos ou com direcionamento
* Você deseja reduzir os custos de gerenciamento e manutenção da infraestrutura
* Você precisa de integração perfeita com o Adobe Experience Cloud ou o Adobe Experience Platform
* Você está planejando uma atualização importante ou uma atualização da infraestrutura de qualquer maneira
* **Você deseja uma tecnologia inovadora** - as versões anteriores chegarão ao Fim do Suporte
* **Sua equipe precisa de uma interface moderna** - A interface da Web do Campaign oferece melhor acessibilidade para os profissionais de marketing

**Considerações sobre migração:**

* A Adobe oferece suporte, orientação e ferramentas de migração
* O v8 é gerenciado somente pelo Cloud Service (sem implantação local ou híbrida)
* Algumas implementações técnicas podem ser diferentes - revise a [matriz de recursos](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* A migração e o teste de dados exigem planejamento e recursos
* **Para usuários do Campaign Standard** - A transição foi projetada para ser tranquila e causar o mínimo de interrupção do fluxo de trabalho

**Próximas etapas:**

Entre em contato com seu representante da Adobe para:

* Avaliar a prontidão e o cronograma da migração
* Entenda os benefícios específicos para seu caso de uso
* Planejar a estratégia de migração e a alocação de recursos
* Acessar ferramentas e suporte de migração

**Tópicos relacionados:**

**Para usuários do Campaign Classic v7:**

* [Do Campaign Classic v7 para o v8](v7-to-v8.md)
* [Guia detalhado do v7 para o v8](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**Para usuários do Campaign Standard:**

* [Transição do Campaign Standard para v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Guia de adoção do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Do Campaign Standard para a visão geral do v8](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/overview){target="_blank"}
* [Introdução para profissionais de marketing](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/marketers){target="_blank"}
* [Introdução para administradores/desenvolvedores](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**Recursos gerais:**

* [Matriz de recursos do Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Matriz de compatibilidade](compatibility-matrix.md)

+++

+++ Quais são as principais diferenças de terminologia e recursos no Campaign v8?

O Campaign v8 traz a maioria dos recursos do Campaign Classic v7 e do Campaign Standard com melhorias, mas alguns recursos mudaram devido à arquitetura nativa em nuvem e alguma terminologia difere entre as versões.

**Diferenças de terminologia (Campaign Standard para v8):**

* **Os recursos personalizados** agora são **Esquemas**
* **As mensagens** são chamadas de **entregas**
* **Usuários do produto** agora são **Operadores**
* **Funções** estão configuradas com **Direitos Nomeados**
* **Grupos de Segurança** agora são **Grupos de Operadores**
* **As unidades organizacionais** são gerenciadas por meio de **Permissões de Pasta**

**Atualizações de terminologia da interface da Web do Campaign:**

Os termos a seguir foram atualizados na interface do usuário da Web do Campaign (o console do cliente usa termos tradicionais):

* **Destinatários** agora são **Perfis**
* **Seed addresses** agora são **Perfis de teste**
* **Análise de entrega** agora é **Preparação de entrega** (clique no botão **Preparar**)
* A **Visualização de email** está disponível por meio do botão **Simular conteúdo**
* **Listas** agora são **Públicos**

**Não disponível na v8:**

* **Implantações locais e híbridas** - a v8 é somente o Managed Cloud Services
* **Acesso direto ao banco de dados** - Em vez disso, use as APIs e ferramentas fornecidas
* **Infraestrutura gerenciada pelo cliente** - a Adobe gerencia toda a infraestrutura
* **Atualizações manuais de compilação** - Agora automático (gerenciado pelo Adobe)

**Diferentes implementações na v8:**

* **Fluxos de trabalho técnicos** - Alguns otimizados para a arquitetura de nuvem, podem funcionar de forma diferente
* **Estrutura de banco de dados** - A arquitetura FFDA aprimorada pode exigir adaptações de esquema
* **Integrações personalizadas** - Talvez sejam necessárias atualizações para a arquitetura baseada em nuvem
* **Personalizações de baixo nível** - Algumas exigem abordagens diferentes no ambiente gerenciado

**Aprimorado ou substituído na v8:**

* **Atualizações de compilação** - Automática com modelo de entrega contínua em vez de manual
* **Ajuste de desempenho** - Administrado pela otimização da infraestrutura do Adobe
* **Patches de segurança** - Aplicados automaticamente pela Adobe
* **Backup e recuperação** - Gerenciado pela Adobe como parte do serviço
* **Interface do usuário** - Nova interface da Web do Campaign junto com o console do cliente

**Recursos adicionados para usuários do Campaign Standard em transição para o v8:**

* **Relatórios Dinâmicos** - Relatórios personalizáveis em tempo real com análise demográfica
* **Marcas centralizadas** - Defina as diretrizes técnicas e visuais da marca
* **APIs REST** - Crie integrações e crie seu ecossistema
* **Melhorias nas páginas de aterrissagem** - Paridade de recursos aprimorada com o Campaign Standard
* **Fragmentos visuais** - Componentes visuais reutilizáveis para emails e modelos de conteúdo

**Importante:** a maioria dos recursos operacionais e de marketing estão disponíveis e foram aprimorados na v8. Os recursos técnicos e de nível de infraestrutura são gerenciados pela Adobe no ambiente de nuvem.

**Tópicos relacionados:**

* [Matriz de recursos](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} - Comparar recursos entre interfaces
* [Matriz de compatibilidade](compatibility-matrix.md) - Sistemas e componentes com suporte
* [Medidas de proteção e limitações](ac-guardrails.md)
* [Guia de transição do v7 para o v8](v7-to-v8.md)
* [Transição do Campaign Standard para o v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++

## Perfis e públicos-alvos {#audiences}

Encontre respostas para perguntas sobre como gerenciar perfis, criar públicos, importar dados e direcionar recipients para suas campanhas.

+++ Como criar destinatários?

Crie recipients manualmente no console do cliente para perfis individuais, importe de arquivos (CSV/TXT) para adições em massa, use formulários web para se autorregistrar ou integre por meio de APIs de sistemas externos. Use workflows de importação para cargas de dados recorrentes.

[Criar perfis manualmente](../audiences/create-profiles.md) | [Importar perfis de um arquivo](../audiences/import-profiles.md) | [Coletar perfis com formulários web](../audiences/collect-profiles.md)

+++

+++ Como importar perfis?

O Campaign oferece vários métodos de importação: importação simples de arquivos usando o assistente de importação, importação baseada em fluxo de trabalho para transformações complexas, importações recorrentes com fluxos de trabalho agendados do SFTP e importação de API para integração programática.

Para importações de arquivos, prepare seu arquivo de dados (codificação CSV/TXT, UTF-8), use o assistente de importação ou fluxo de trabalho, mapeie colunas para campos do Campaign, defina regras de atualização/inserção e teste com uma pequena amostra primeiro. Use workflows para importações recorrentes e aplique regras de desduplicação.

[Guia de importação de dados](../start/import.md) | [Fluxo de trabalho de importação recorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [Atividade de carregamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso definir a população alvo de uma campanha de marketing?

O Campaign oferece vários métodos de direcionamento: criar consultas com critérios visuais, direcionar listas ou segmentos existentes, importar destinatários de arquivos externos (CSV, TXT) ou aplicar filtros predefinidos. Você pode combinar critérios com a lógica E/OU, excluir populações específicas, usar grupos de controle e dividir para testes A/B. Sempre visualize o tamanho do público-alvo antes de enviar.

[Definir alvos da campanha](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=pt-BR){target="_blank"} | [Atividade de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=pt-BR){target="_blank"} | [Criar públicos-alvo](../audiences/create-audiences.md)

+++

+++ Como posso criar uma lista de perfis?

Uma lista é um conjunto estático de recipients que pode ser direcionado em deliveries e reutilizado em campanhas.

**Três métodos de criação:**

* **Criação manual:** Navegue até **[!UICONTROL Profiles and Targets > Lists]** e clique em **[!UICONTROL Create]**. Adicionar recipients de um query, por seleção individual ou de uma pasta.

* **Automação de fluxo de trabalho:** Use a atividade **[!UICONTROL List update]** para criar e manter listas automaticamente a partir dos resultados da consulta ou dos dados importados.

* **Durante a importação:** crie uma lista ao importar perfis para salvá-los como um grupo reutilizável.

**Dica:** use fluxos de trabalho para listas que exigem atualizações regulares e criação manual para segmentação única.

[Criar públicos-alvo](../audiences/create-audiences.md) | [Listar atividade de atualização](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ Como posso excluir informações em duplicidade de uma população antes de enviar uma mensagem?

Use a atividade **[!UICONTROL Deduplication]** em um fluxo de trabalho para remover destinatários duplicados antes da entrega. Coloque-o entre as atividades de **[!UICONTROL Query]** e **[!UICONTROL Delivery]**, escolha os critérios de desduplicação (normalmente endereço de email ou ID de destinatário) e qual registro manter.

**Dica:** sempre elimine a duplicação antes de enviar para garantir que cada pessoa receba sua mensagem apenas uma vez.

[Atividade de desduplicação](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=pt-BR){target="_blank"}

+++

+++ Como identificar e direcionar assinantes a um informativo?

O Campaign rastreia automaticamente as assinaturas de boletim informativo por meio de serviços de informações. Para direcionar assinantes:

* Use uma atividade de **[!UICONTROL Query]** e filtre por **[!UICONTROL Subscriptions]** > selecione seu serviço de boletim informativo
* Direcione assinantes diretamente da sua entrega escolhendo **[!UICONTROL To > Subscribers of an information service]**
* Criar listas de assinantes com a atividade de fluxo de trabalho **[!UICONTROL Subscription Services]**

A campanha rastreia o histórico de subscrição/unsubscription e gerencia a aceitação/recusa automaticamente.

[Gerenciar assinaturas](../start/subscriptions.md) | [Atividade de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=pt-BR){target="_blank"}

+++

+++ Qual é a prática recomendada para excluir perfis de uma população alvo?

Use a atividade **[!UICONTROL Exclusion]** em um fluxo de trabalho para remover perfis indesejados do seu público-alvo. Coloque-o após as atividades de direcionamento e defina qual população excluir.

[Atividade de exclusão](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ Posso usar perfis externos sem importá-los no Campaign?

Sim, o Campaign v8 permite trabalhar com perfis externos armazenados em um banco de dados externo sem carregá-los no Adobe Campaign. [Saiba mais](../audiences/external-profiles.md).

+++

+++ Como criar perfis de teste para meus deliveries?

Os perfis de teste são destinatários especiais usados para enviar provas e validar deliveries sem afetar o banco de dados de produção. Crie-os no **[!UICONTROL Profiles and Targets > Test profiles]** ou use o recurso **[!UICONTROL Seed addresses]** para adicionar automaticamente recipients de teste às suas entregas para controle de qualidade e monitoramento da caixa de entrada.

[Perfis de teste](../audiences/test-profiles.md)

+++

## Design da mensagem {#design}

Saiba como projetar mensagens de marketing eficazes no Campaign v8, incluindo modelos de email, técnicas de personalização e conteúdo multilíngue. Projete suas mensagens no console do cliente ou use o moderno **Email Designer** na interface do usuário da Web do Campaign para obter uma experiência aprimorada de edição visual.

+++ Quais são as práticas recomendadas para criar e-mails no Campaign?

Principais diretrizes: garantir design responsivo para dispositivos móveis, usar código compatível com HTML 4.0/XHTML com CSS em linha, otimizar imagens (abaixo de 100 KB) com texto alternativo, usar campos de mesclagem de personalização, testar clientes de email antes de enviar e incluir uma versão de texto simples. Tenha como meta o tamanho total do email abaixo de 500 KB para uma entrega ideal.

[Guia de design de email](../send/email.md) | [Práticas recomendadas de entrega](delivery-best-practices.md)

+++

+++ O que é um modelo da entrega?

Um template do delivery é um delivery pré-configurado que salva todas as configurações e parâmetros para reutilização em várias campanhas. Os modelos incluem regras de direcionamento, design de conteúdo, personalização, configurações técnicas (remetente, responder para) e regras de tipologia. Crie uma única vez e reutilize para manter a consistência e acelerar a criação da campanha.

[Criar modelos de entrega](../send/create-templates.md)

+++

+++ Posso importar facilmente um HTML existente para criar um email no Campaign?

Sim. Importe conteúdo do HTML por meio de cópia/colagem direta no editor de conteúdo, upload de arquivo do seu computador ou carregamento de um URL. Certifique-se de que o HTML usa código compatível com email (HTML 4.0/XHTML) com CSS em linha e hospeda imagens em um servidor público. O Campaign adiciona automaticamente personalização e rastreamento ao HTML importado.

**Dica:** para obter a melhor experiência de design de email, use o **Designer de email** na interface do usuário da Web do Campaign, que oferece recursos modernos de arrastar e soltar e modelos responsivos incorporados, em vez de importar HTML bruto.

[Importar conteúdo do HTML](../send/defining-the-email-content.md)

+++

+++ Como posso criar um boletim informativo baseado em assinaturas no Campaign?

Sim. Use os serviços de informações do Campaign para gerenciar assinaturas de boletins informativos. Os principais recursos incluem controle automático de aceitação/recusa, rastreamento de assinatura, gerenciamento de conformidade (GDPR, CAN-SPAM), suporte a vários boletins informativos, integração da Web para formulários de inscrição e entrega direcionada aos assinantes.

[Gerenciar assinaturas](../start/subscriptions.md)

+++

+++ Como posso personalizar mensagens?

O Campaign oferece recursos de personalização para criar mensagens relevantes e direcionadas com base em dados, comportamento e preferências do recipient.

**Opções do Personalization:**

* **Campos de personalização** - Insira os dados do destinatário (por exemplo, `"Hello {{firstName}}")`
* **Blocos de personalização** - Use blocos de conteúdo predefinidos ou personalizados
* **Conteúdo condicional** - Exibir conteúdo diferente com base nos critérios do destinatário
* **Dados comportamentais** - Aproveite o histórico de navegação, os padrões de compra ou as métricas de envolvimento

Teste a personalização antes de enviar para verificar se os campos de mesclagem e a lógica condicional funcionam corretamente.

[Guia do Personalization](../send/personalize.md) | [Campos de personalização](../send/personalization-fields.md) | [Conteúdo condicional](../send/conditions.md)

+++

+++ Posso enviar mensagens em vários idiomas?

Sim. O Campaign v8 oferece recursos multilíngues, com a **Interface do usuário da Web do Campaign** fornecendo a abordagem mais fácil. A interface da Web oferece delivery multilíngue nativo com variantes de idioma. Adicione variantes de idioma ao delivery e o Campaign envia automaticamente a versão apropriada com base no idioma preferencial do recipient. Disponível para email, notificações por push, SMS e mensagens transacionais.

Principais recursos: duplicação automática de conteúdo, envio automático baseado em idioma, fallback de idioma padrão e gerenciamento fácil de variantes.

O console do cliente também oferece suporte a conteúdo multilíngue usando conteúdo condicional e fluxos de trabalho, mas requer mais configuração manual.

[Entregas multilíngues (Interface do Usuário da Web)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Conteúdo condicional (Console do cliente)](../send/conditions.md)

+++

+++ Posso traduzir um formulário web?

Sim. Os aplicativos Web do Campaign oferecem suporte à localização em vários idiomas. Defina traduções para todos os elementos de formulário (rótulos, botões, mensagens, texto de erro), com detecção automática de idioma com base no perfil do destinatário ou nas configurações do navegador. Há suporte para várias versões de idioma em um único aplicativo web, com fallback para um idioma padrão quando necessário.

[Localização do aplicativo web](../dev/webapps.md)

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

[Visão geral do Assistente de IA](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Casos de uso do Assistente de IA](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Alinhamento da marca](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Teste e envio de mensagens {#send}

Conheça as práticas recomendadas para testar, validar, enviar e rastrear suas mensagens de marketing para garantir o sucesso do delivery do Campaign.

+++ O que é análise de entrega?

A análise de entrega é uma fase de validação na qual a Campanha é executada antes do envio. Ele calcula a população do target, valida o conteúdo, verifica erros, aplica regras de tipologia e estima o volume de delivery.

O Campaign gera logs mostrando avisos e erros. Os erros bloqueiam a entrega e devem ser corrigidos; os avisos são consultivos. Sempre revise os logs de análise antes de enviar.

[Guia de análise de entrega](../send/delivery-analysis.md)

+++

+++ Por que devo criar provas?

Provas são mensagens de teste que validam sua entrega antes de enviá-la para o público-alvo principal. Use provas para verificar a personalização, testar a renderização de conteúdo em clientes de email, confirmar links e o trabalho de rastreamento, verificar imagens e anexos e validar a capacidade de resposta móvel.

As provas ajudam a detectar erros antes que eles alcancem milhares de recipients, ativar a aprovação das partes interessadas e testar a inserção da caixa de entrada. Envie provas para vários clientes e dispositivos de email e sempre obtenha aprovação antes que a produção seja enviada.

[Guia de provas e visualização](../send/preview-and-proof.md)

+++

+++ Como usar seed addresses no Adobe Campaign?

Os seed addresses são recipients especiais adicionados automaticamente a cada delivery para teste, controle de qualidade e monitoramento, sem corresponder aos critérios do público-alvo. Útil para monitoramento contínuo, teste de posicionamento na caixa de entrada, validação de correspondência direta e visibilidade das partes interessadas.

**Principais diferenças das provas:**

* **Seed addresses** - Adicionado às entregas de produção automaticamente, conte para enviar volume
* **Provas** - O teste envia antes da produção, não conte no volume, usado para validação

Gerenciar seed addresses em **[!UICONTROL Resources > Campaign management > Seed addresses]**. Mantenha listas pequenas para não afetar as métricas de entrega.

[Guia de seed addresses](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ Como posso configurar um processo de aprovação antes de enviar mensagens?

O Campaign fornece workflows de aprovação para garantir que as mensagens atendam aos padrões de qualidade antes do envio. Configure aprovações para conteúdo, target, extração (correspondência direta) e orçamento no nível da campanha ou do delivery.

**Instalação:**

Crie grupos de operadores em **[!UICONTROL Administration > Access management > Operator groups]** e atribua grupos de aprovações nas propriedades de campanha ou de entrega. O Campaign envia emails de notificação para revisores que podem aprovar, rejeitar ou solicitar alterações.

**Para entregas autônomas (não em uma campanha):**

Use **provas como seu processo de aprovação**. Envie provas ao seu grupo de aprovação para validação e sempre envie uma nova prova depois de fazer alterações para garantir que as partes interessadas revisem a versão mais recente.

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

[Guia de regras de tipologia](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso enviar emails em ondas?

Sim. O envio de onda divide seu delivery em vários lotes enviados em intervalos programados. Isso é essencial para campanhas de grande volume, a fim de balancear a carga do servidor, impedir a limitação do ISP, criar a reputação do remetente com novos IPs e gerenciar recusas/rejeições entre ondas.

**Configuração:**

Nas propriedades de delivery, ative o envio de ondas e defina o número de ondas (ou o tamanho do lote), o intervalo entre as ondas e a distribuição de ondas (porcentagens lineares ou personalizadas). O Campaign divide automaticamente sua população de público-alvo e envia cada onda conforme programado.

Use ondas para campanhas grandes, monitore o desempenho da primeira onda antes de continuar e aguarde tempo suficiente entre as ondas para processar rejeições e recusas.

[Configurar envio de onda](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ Quais são as principais etapas para criar um email no Campaign?

A criação de um email no Campaign v8 envolve estas etapas principais: criar o delivery, definir o público-alvo, criar o conteúdo, adicionar personalização, definir as configurações (remetente, assunto, responder para), executar a análise do delivery, enviar provas para teste e finalmente enviar ou agendar.

**Etapas principais:**

1. **Criar a entrega** - Escolha o email como canal e, opcionalmente, selecione um modelo de entrega
1. **Definir o público-alvo** - Selecione o público-alvo do destinatário usando consultas, listas ou arquivos importados
1. **Criar o conteúdo** - Crie sua mensagem usando o editor de email (Designer de Email da Interface do Usuário da Web ou editor do console do cliente)
1. **Adicionar personalização** - Inserir campos dinâmicos, blocos de personalização e conteúdo condicional
1. **Definir configurações** - Definir endereço do remetente, linha de assunto, responder para e parâmetros de entrega
1. **Executar análise de entrega** - A campanha valida o conteúdo, calcula o destino e verifica se há erros
1. **Enviar provas** - Teste seu email com grupos de aprovação para validar a renderização e o conteúdo
1. **Enviar ou agendar** - Enviar imediatamente para o destino principal ou agendar para uma data posterior

**Duas opções de interface:**

* **Interface do usuário da Web do Campaign** - Interface moderna com Designer de email aprimorado, Assistente de IA e recursos multilíngues
* **Console do cliente** - Interface tradicional com recursos avançados de direcionamento e fluxo de trabalho

**Dica:** use a interface do usuário da Web do Campaign para criar emails mais rápidos e intuitivos com ferramentas de design modernas. Use o console do cliente para direcionamento complexo ou campanhas avançadas baseadas em fluxo de trabalho.

[Criar seu primeiro email](create-message.md) | [Guia de design de email](../send/email.md)

+++

+++ Como agendar uma entrega?

O Campaign permite agendar deliveries para envio futuro, a fim de otimizar os tempos de envio e coordenar campanhas.

**Opções de agendamento:**

* **Propriedades de entrega** - Enviar imediatamente, agendar uma data/hora específica ou adiar por horas/dias
* **Nível de campanha** - Coordene todas as entregas em uma campanha
* **Atividade do Agendador de Fluxo de Trabalho** - Para entregas recorrentes, padrões complexos e campanhas acionadas por eventos

O Campaign também oferece suporte à otimização da data de contato (melhor horário de envio por recipient) e à adaptação do fuso horário (mesmo horário local para todos os recipients).

[Agendar envio de entrega](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Posso adicionar um anexo aos emails?

Sim. O Campaign é compatível com anexos estáticos (o mesmo arquivo para todos os destinatários) e anexos personalizados (arquivos diferentes por destinatário com base nos dados de perfil). Adicione anexos na seção **[!UICONTROL Attachments]** de suas propriedades de entrega.

**Considerações importantes:**

* Mantenha os anexos abaixo de 1 MB para obter a entrega ideal
* Os anexos podem acionar filtros de spam; teste completamente antes de enviar
* Evite tipos de arquivos comumente bloqueados por clientes de email (.exe, .zip, .js)
* Para arquivos grandes, considere usar links de download rastreados

Use formatos de arquivo seguros (PDF, JPEG, PNG, DOCX) e teste com seed addresses antes do envio da produção.

[Guia de anexos de email](../send/email.md#attachments)

+++

+++ Como posso configurar links rastreados em uma entrega de email?

O Campaign converte automaticamente todos os URLs no seu email em links rastreados para monitorar a participação do recipient. Acesse a seção **[!UICONTROL Tracking]** na entrega para definir as configurações de rastreamento para cada link.

**Opções de configuração:**

* **Habilitar/desabilitar rastreamento** - Controle de rastreamento por link
* **Rótulos de links** - Adicione nomes descritivos para relatórios (por exemplo, &quot;Comprar agora CTA&quot;)
* **Categorias de links** - Agrupa os links por tipo para análise agregada
* **Tipo de rastreamento** - Rastrear cliques, aberturas ou ambos

A campanha rastreia links de conteúdo, links de mirror page, links de cancelamento de inscrição e pode incluir um pixel de rastreamento opcional para aberturas de email. Use rótulos e categorias relevantes para simplificar os relatórios e identificar rapidamente o conteúdo de alto desempenho.

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

[Relatórios de entrega internos](../reporting/delivery-reports.md) | [Relatórios de campanha](../reporting/gs-reporting.md)

+++

+++ Como o Adobe Campaign qualifica e gerencia endereços em quarentena?

O Campaign gerencia automaticamente uma lista de quarentena para proteger a reputação do remetente e melhorar a capacidade de entrega. Os endereços em quarentena são excluídos automaticamente de deliveries futuros até serem validados ou removidos da quarentena.

**Por que os endereços são colocados em quarentena:**

* **Rejeições permanentes** - Falhas permanentes de entrega (endereço de email inválido, o domínio não existe e a caixa de correio foi excluída)
* **Limite de rejeição temporária** - Falhas temporárias repetidas (caixa de correio cheia, servidor temporariamente indisponível) excedendo o limite de erro
* **Reclamações de spam** - Destinatários que marcam seus emails como spam
* **Endereços inválidos** - Endereços com erros de sintaxe ou que falham na validação
* incluir na lista de bloqueios **** - Destinatários que optaram por não participar ou solicitaram a exclusão

**Como funciona a quarentena:**

A campanha rastreia erros de delivery para cada endereço. Quando um endereço atinge o limite de erro configurado, ele é automaticamente colocado em quarentena e excluído de todos os deliveries futuros durante a análise. As rejeições permanentes (falhas permanentes) são colocadas em quarentena imediatamente, enquanto as rejeições temporárias exigem várias falhas antes da quarentena.

**Gerenciando endereços em quarentena:**

Acesse o gerenciamento de quarentena em **[!UICONTROL Administration > Campaign Management > Non deliverables Management]**. Você pode exibir endereços em quarentena, remover manualmente endereços validados da quarentena ou configurar regras de limpeza automática.

**Dica:** Monitore regularmente sua lista de quarentena. O aumento das taxas de quarentena geralmente sinaliza problemas de qualidade de dados que precisam de atenção antes que afetem a reputação do remetente.

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

* [Criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=pt-BR){target="_blank"}
* [Atividades do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"}
* [Práticas recomendadas para fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=pt-BR){target="_blank"}
* [Casos de uso de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Como posso importar dados no Campaign?

Importe dados para o Campaign usando vários métodos dependendo das suas necessidades:

**Importação de arquivo simples:**

* Use o assistente de importação para importações CSV/TXT únicas com uma interface guiada
* Ideal para uploads manuais e carregamentos de dados rápidos

**Importação baseada em fluxo de trabalho:**

* Criar fluxos de trabalho com a atividade **[!UICONTROL Data loading (file)]** para importações complexas
* Adição de transformações de dados, enriquecimento e desduplicação
* Agendar importações recorrentes de SFTP, diretórios locais ou armazenamento na nuvem

**Integração de API:**

* Usar APIs REST para importar dados programaticamente de sistemas externos
* Ideal para sincronização em tempo real com CRM, comércio eletrônico ou outras plataformas

**Práticas recomendadas:** sempre teste com amostras pequenas, use a codificação UTF-8, mapeie os campos corretamente, aplique regras de desduplicação e agende grandes importações fora do horário de pico.

**Tópicos relacionados:**

* [Práticas recomendadas de importação](../start/import.md)
* [Atividade de carregamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=pt-BR){target="_blank"}
* [Fluxo de trabalho de importação recorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ Posso monitorar a execução do fluxo de trabalho?

Sim. O Campaign oferece recursos abrangentes de monitoramento de fluxo de trabalho para rastrear a execução, identificar problemas e otimizar o desempenho.

**Opções de monitoramento:**

* **Painel de fluxo de trabalho** - Exibir o status de execução em tempo real, o progresso e os estados de atividade
* **Logs de execução** - Acesse logs detalhados para cada atividade e transição
* **Trilha de auditoria** - Rastrear as modificações do fluxo de trabalho e o histórico de execução
* **Alertas e notificações** - Configurar alertas de email para falhas ou condições específicas

**Principais recursos de monitoramento:**

* Indicadores visuais de status (pendente, em andamento, concluído, com falha)
* Rastreamento do tempo de execução para otimização do desempenho
* Mensagens de erro no nível de atividade para solução de problemas
* Pausar, parar ou reiniciar workflows conforme necessário

Acesse o monitoramento a partir de **[!UICONTROL Administration > Production > Objects created automatically > Campaign workflows]** ou diretamente do painel de fluxo de trabalho.

**Tópicos relacionados:**

* [Monitorar a execução do fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=pt-BR){target="_blank"}
* [Práticas recomendadas para fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=pt-BR){target="_blank"}
* [Iniciar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/executing-a-workflow/start-a-workflow.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso atualizar dados do Campaign com um fluxo de trabalho?

Use a atividade **[!UICONTROL Update data]** em fluxos de trabalho para executar operações em massa no banco de dados:

**Operações com suporte:**

* **Inserir** - Adicionar novos registros ao banco de dados
* **Atualização** - Modificar registros existentes com base em critérios correspondentes
* **Inserir ou atualizar** - Adicionar novos registros ou atualizar os existentes (substituir)
* **Excluir** - Remover registros que correspondam a critérios específicos

**Casos de uso comuns:**

* Atualizar atributos de perfil após o enriquecimento de dados
* Sincronizar dados com sistemas externos
* Manter associações de lista com base no comportamento
* Limpar e desduplicar dados
* Aplicar alterações de status em massa (por exemplo, recusa, quarentena)

Configure as chaves de reconciliação para corresponder os registros com precisão e escolha as opções de atualização (atualize todos os campos ou apenas os vazios).

**Tópicos relacionados:**

* [Atualizar atividade de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=pt-BR){target="_blank"}
* [Atividades de gerenciamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Como posso aproveitar os recursos de gestão de dados?

As atividades de gestão de dados do Campaign permitem operações de dados sofisticadas dentro de workflows para direcionamento e segmentação complexos.

**Atividades de gerenciamento de dados principais:**

* **Enriquecimento** - Adicione dados de tabelas relacionadas ou fontes externas à sua população de trabalho
* **Split** - Segmente populações com base em critérios ou distribua aleatoriamente
* **Eliminação de Duplicação** - Remover registros duplicados com base em chaves especificadas
* **Atualizar dados** - Executar operações de inserção, atualização ou exclusão em massa
* **Alterar dimensão** - Alternar dimensões de direcionamento (por exemplo, de destinatários para assinaturas)
* **Interseção/União/Exclusão** - Combinar ou filtrar várias populações

**Casos de uso comuns:**

* Enriquecer perfis com dados de histórico de compras ou comportamento
* Segmentar públicos em vários grupos para mensagens diferentes
* Remover duplicatas antes da entrega
* Integrar dados de bancos de dados externos (FDA - Federated Data Access)
* Criar consultas e junções complexas de várias tabelas

Essas atividades permitem trabalhar com dados que não estão diretamente na tabela principal de recipients e executar operações avançadas de banco de dados.

**Tópicos relacionados:**

* [Atividades de gerenciamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"}
* [Fluxos de trabalho de direcionamento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=pt-BR){target="_blank"}
* [Atividade de enriquecimento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=pt-BR){target="_blank"}

+++

+++ Posso automatizar o envio de mensagens personalizadas?

Sim. Os workflows permitem campanhas de mensagem personalizadas totalmente automatizadas com base em dados, comportamento e critérios personalizados do recipient.

**Estrutura de fluxo de trabalho de automação:**

1. **Consulta** - Selecione seu público-alvo de destino com base em critérios
1. **Enriquecimento** - Adicionar dados de personalização de tabelas relacionadas
1. **Divisão** - Segmentar em grupos para diferentes variantes de mensagem (opcional)
1. **Entrega** - Enviar mensagens personalizadas com campos de mesclagem
1. **Agendador** - Configurar execução recorrente para campanhas automatizadas

**Opções do Personalization:**

* Usar dados de perfil do recipient (nome, local, preferências)
* Incluir dados comportamentais (histórico de compras, pontuações de engajamento)
* Aplicar conteúdo condicional com base em segmentos ou atributos
* Calcular valores dinâmicos (pontos de fidelidade, datas de expiração)

Cenários comuns: campanhas de aniversário, abandono do carrinho, programas de fidelidade, campanhas de retorno e mensagens acionadas por eventos.

**Tópicos relacionados:**

* [Guia do Personalization](../send/personalize.md)
* [Casos de uso de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=pt-BR){target="_blank"}
* [Atividade de enriquecimento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=pt-BR){target="_blank"}

+++

+++ Como dividir um público-alvo em subconjuntos com um fluxo de trabalho?

Use a atividade **[!UICONTROL Split]** para dividir uma única população em vários subconjuntos com base em critérios ou regras de distribuição.

**Métodos de divisão:**

* **Condições de filtragem** - Crie subconjuntos com base em critérios (por exemplo, faixa etária, local, status do VIP)
* **Distribuição percentual** - Dividir aleatoriamente em porcentagens iguais ou personalizadas para teste A/B
* **Limitar registros** - Restringir tamanhos de subconjunto (primeiros N registros, X% superior, seleção aleatória)
* **Agrupamento de dados** - Crie um subconjunto por valor distinto (por exemplo, um subconjunto por país)

**Casos de uso comuns:**

* Teste A/B com grupos de controle
* Roteamento de preferência de canal (email vs. SMS)
* Implantação progressiva (enviar para 10% e, em seguida, 90%)
* Mensagens específicas do segmento (VIP, clientes comuns, novos)
* Balanceamento de carga em vários servidores de entrega

Cada subconjunto dividido flui para uma transição separada, permitindo processamento ou delivery diferente para cada grupo.

**Tópicos relacionados:**

* [Dividir atividade](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=pt-BR){target="_blank"}
* [Guia de teste A/B](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Como posso atualizar os dados do destinatário de um arquivo externo?

Sim. Use workflows para atualizar dados do Campaign com valores de arquivos externos (CSV, TXT).

**Estrutura de fluxo de trabalho:**

1. **Carregamento de dados (arquivo)** - Carregar o arquivo externo e mapear colunas
1. **Enriquecimento** (opcional) - Adicionar dados ou transformações adicionais
1. **Reconciliação** - Defina as chaves para corresponder os registros do arquivo com os registros do banco de dados (por exemplo, endereço de email, ID do destinatário)
1. **Atualizar dados** - Escolha as opções de atualização:
   * Atualizar somente registros correspondentes
   * Atualizar campos existentes ou apenas campos vazios
   * Inserir novos registros se nenhuma correspondência for encontrada

**Cenários comuns:**

* Atualizar atributos de perfil das exportações do CRM
* Atualizar status de assinatura de sistemas externos
* Sincronizar pontos de fidelidade ou pontuações do cliente
* Atualizar preferências de aceitação/recusa
* Enriquecer perfis com dados comportamentais

**Práticas recomendadas:** use identificadores exclusivos para reconciliação, valide dados antes de atualizar, teste com amostras pequenas e agende atualizações regulares para sincronização contínua.

**Tópicos relacionados:**

* [Guia de importação de dados](../start/import.md)
* [Atividade de carregamento de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=pt-BR){target="_blank"}
* [Atualizar atividade de dados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso identificar e direcionar novos destinatários?

Use workflows com atividades de query para identificar recipients adicionados recentemente e acionar campanhas de boas-vindas automatizadas.

**Abordagem da consulta:**

Crie uma filtragem de consulta no campo **[!UICONTROL Created date]** para selecionar destinatários adicionados em um período específico (por exemplo, últimas 24 horas, semana passada).

**Estrutura automatizada do fluxo de trabalho de boas-vindas:**

1. **Agendador** - Executar diariamente ou em intervalos específicos
1. **Consulta** - Selecionar destinatários criados desde a última execução
1. **Eliminação de Duplicação** (opcional) - Verifique se não há duplicatas
1. **Entrega** - Enviar mensagem de boas-vindas
1. **Atualizar dados** (opcional) - Marcar destinatários como &quot;bem-vindos&quot;

**Técnica avançada com agregações:**

Use funções de agregação para identificar dinamicamente as adições mais recentes e comparar com recipients processados anteriormente para detecção sofisticada de novos recipients.

**Tópicos relacionados:**

* [Atividade Query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=pt-BR){target="_blank"}
* [Uso de agregações](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=pt-BR){target="_blank"}
* [Programas de boas-vindas](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=pt-BR){target="_blank"}

+++

+++ Como faço para usar as atividades de fluxo de trabalho?

Os workflows da campanha são criados usando quatro categorias principais de atividades, cada uma com finalidades específicas:

**Atividades de direcionamento** - Defina e refine seu público

* Query, Split, Deduplication, Enrichment, Intersection, Union, Exclusion
* Use-os para selecionar recipients, segmentar populações e combinar fontes de dados

**Atividades de controle de fluxo** - Gerenciar lógica e tempo do fluxo de trabalho

* Scheduler, Wait, Test, Fork, AND-join, OR-join, Saltar
* Controle o fluxo de execução, adicione condições e gerencie caminhos paralelos

**Atividades de ação** - Executar operações e enviar mensagens

* Entrega, Atualização de dados, Carregamento de dados (arquivo), Extração de dados (arquivo), Código JavaScript
* Executar operações de banco de dados, transferências de arquivos e envio de mensagens

**Atividades de evento** - Reagir a acionadores externos

* Sinal externo, Coletor de arquivos, Transferência HTTP, SMS, Email
* Lidar com dados de entrada e interações externas do sistema

Para usar atividades, arraste-as da paleta para a tela do fluxo de trabalho, clique duas vezes para configurar parâmetros e conecte-os com transições.

**Tópicos relacionados:**

* [Referência às atividades de direcionamento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}
* [Referência a atividades de controle de fluxo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}
* [Referência de atividades de ação](https://experienceleague.adobe.com/pt-br/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities){target="_blank"}
* [Referência de atividades de evento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}

+++

+++ Quais são as práticas recomendadas de workflow?

Siga estas práticas recomendadas para criar workflows eficientes, sustentáveis e confiáveis:

**Design e organização:**

* Usar nomes claros e descritivos para fluxos de trabalho e atividades
* Adicionar rótulos e descrições à lógica do documento
* Agrupar visualmente atividades relacionadas para facilitar a leitura
* Divida processos complexos em vários workflows menores

**Otimização de desempenho:**

* Limitar os tamanhos dos resultados da consulta com filtros apropriados
* Usar tabelas temporárias para armazenamento de dados intermediário
* Agendar fluxos de trabalho que consomem muitos recursos fora das horas de pico
* Evite loops desnecessários e iterações excessivas

**Tratamento e monitoramento de erros:**

* Adicionar caminhos de tratamento de erros com supervisores
* Configurar alertas para fluxos de trabalho com falha
* Teste com amostras de dados pequenos antes da execução completa
* Revisar logs de execução regularmente para problemas de desempenho

**Manutenção e governança:**

* Arquivar ou excluir workflows obsoletos
* Alterações no fluxo de trabalho de controle de versão e modificações no documento
* Limitar a complexidade do fluxo de trabalho (meta para &lt; 20 atividades)
* Usar modelos de fluxo de trabalho para padrões recorrentes

**Gerenciamento de segurança e de dados:**

* Aplicar permissões apropriadas do operador
* Limpar dados temporários com a limpeza do fluxo de trabalho
* Evite codificar valores fixos — use variáveis e opções
* Revisar e otimizar fluxos de trabalho com baixo desempenho regularmente

**Tópicos relacionados:**

* [Guia de práticas recomendadas de fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=pt-BR){target="_blank"}
* [Criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=pt-BR){target="_blank"}
* [Monitorar fluxos de trabalhos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=pt-BR){target="_blank"}

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


[Alterar idioma na interface do usuário da Web do Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Introdução ao console do cliente do Campaign](connect.md)

+++

+++ Posso usar o Campaign v8 com outras soluções da Adobe?

Sim. O Campaign v8 integra-se perfeitamente às soluções da Adobe Experience Cloud para criar um ecossistema de marketing poderoso e unificado. Como um Managed Cloud Service, o v8 foi projetado para integração nativa com os aplicativos corporativos da Adobe.

**Principais integrações disponíveis:**

* **Adobe Experience Platform** - Aproveite perfis unificados de clientes e dados em tempo real
* **Adobe Analytics** - Meça o desempenho da campanha e o comportamento do cliente entre canais
* **Adobe Target** - Personalizar conteúdo com base nos segmentos e no comportamento do cliente
* **Adobe Experience Manager** - Centralizar a criação de conteúdo e o gerenciamento de ativos
* **Adobe Audience Manager** - Criar e ativar segmentos de público-alvo entre plataformas

**Benefícios:** dados unificados do cliente, experiências consistentes do usuário, fluxos de trabalho simplificados e recursos de personalização aprimorados.

**Configuração:** a integração com soluções da Adobe exige a autenticação do Adobe Identity Management System (IMS), configurada automaticamente para o Campaign v8 Managed Cloud Services.

[Integrações do Adobe Campaign](../connect/integration.md) | [Conectar-se ao Adobe ID](connect.md)

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

[Sobre a capacidade de entrega no Campaign](../send/about-deliverability.md) | [Guia de Práticas Recomendadas de Entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR){target="_blank"}

+++

+++ A quais bancos de dados externos posso conectar o Campaign?

O Campaign v8 oferece suporte a conexões Federated Data Access (FDA) com os principais sistemas de banco de dados corporativos, permitindo que você aproveite a infraestrutura de dados existente.

**Bancos de dados com suporte:**

* **Bancos de dados na nuvem:** Amazon Redshift, Google BigQuery, Snowflake, Azure Synapse Analytics
* **Bancos de dados corporativos:** Oracle, Microsoft SQL Server, PostgreSQL, MySQL
* **Data warehouses:** Teradata, Vertica, SAP HANA
* **Big data:** Hadoop via Hive

**Considerações específicas da plataforma:** As versões do banco de dados com suporte e os requisitos de conexão variam. O Campaign v8 as a Managed Cloud Service pode ter requisitos específicos de rede e segurança para acesso ao banco de dados externo.

**Importante:** sempre verifique a matriz de compatibilidade oficial da versão do Campaign v8 para confirmar o suporte para versões específicas do banco de dados e garanta o licenciamento adequado para conectores de banco de dados externos.

[Matriz de compatibilidade](compatibility-matrix.md) | [Configurar conexões FDA](../connect/fda.md)

+++

+++ O Adobe Campaign pode se integrar a sistemas de CRM?

Sim. O Campaign fornece conectores CRM nativos para uma sincronização bidirecional perfeita entre o Campaign e seu sistema CRM, garantindo dados consistentes do cliente em todas as plataformas.

**Sistemas de CRM com suporte:**

* **Salesforce** - Clientes potenciais, contatos, contas, oportunidades, campanhas
* **Microsoft Dynamics 365** - Contatos, contas, clientes potenciais, entidades personalizadas
* Outros CRMs por meio de integrações de API personalizadas

**Que sincronizações:**

* **Do CRM para o Campaign:** registros de contato, informações de conta, clientes potenciais, campos personalizados, dados de segmentação
* **Do Campaign para o CRM:** Logs de entrega, dados de rastreamento, métricas de envolvimento, respostas da campanha, status da assinatura

**Modos de sincronização:**

* **Agendado** - Sincronização automática em intervalos definidos (a cada hora, diariamente)
* **Manual** - Sincronização sob demanda acionada por operadores
* **Tempo real** - Via API para atualizações imediatas (desenvolvimento personalizado)

**Configuração:** use o assistente do conector CRM integrado do Campaign para mapear campos do CRM para atributos do Campaign, selecionar tabelas para sincronização e agendar sincronização. O conector lida com a resolução de conflitos e mantém a consistência dos dados.

**Prática recomendada:** comece com sincronização somente leitura para testar o mapeamento e, em seguida, habilite a sincronização bidirecional. Monitore logs de sincronização para verificar se há erros e mantenha dados limpos em ambos os sistemas.

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



[Instalar e configurar o console do cliente](connect.md)

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
* **Grupo de operadores** - Configurações herdadas por todos os membros do grupo


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


[Estender modelo de dados](../dev/extend-schema.md) | [Estrutura de esquema](../dev/schemas.md) | [Práticas recomendadas do modelo de dados](../dev/datamodel-best-practices.md)

+++

## Relatórios {#reporting}

Obtenha insights sobre os recursos de relatórios do Campaign, incluindo relatórios internos, relatórios personalizados e ferramentas de análise de dados como cubos.

+++ Como posso criar novos relatórios?

O Campaign oferece várias opções de relatórios dependendo das suas necessidades e da sua experiência técnica. Você pode usar relatórios internos, criar relatórios personalizados no console do cliente ou criar painéis visuais na interface do usuário da Web do Campaign.

**Opções de relatório:**

* **Relatórios internos** - Relatórios de rastreamento, campanha e entrega prontos para uso acessíveis a partir da guia **[!UICONTROL Reports]**
* **Análise descritiva** - Relatórios estatísticos rápidos sobre quaisquer dados com uma interface orientada por assistente
* **Relatórios personalizados** - Relatórios avançados criados por usuários técnicos usando o editor de relatórios
* **Painéis da Interface do Usuário da Web** - Relatórios visuais modernos e painéis com interface de arrastar e soltar
* **Cubos** - Exploração de dados multidimensionais e análise de tabela dinâmica

**Importante:** o Campaign foi projetado para relatórios de operações de marketing, não como uma ferramenta especializada de business intelligence. Para necessidades analíticas complexas, considere a integração com o Adobe Analytics ou plataformas de BI dedicadas.

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

[Análise descritiva](../reporting/built-in-reports.md)

+++

+++ Como posso criar relatórios avançados sobre os meus dados?

O Campaign oferece duas abordagens para a criação de relatórios personalizados avançados: relatórios técnicos no console do cliente para análise complexa e painéis visuais para facilitar a criação de relatórios.

No console do cliente, é possível:

* Criar relatórios complexos usando consultas SQL e cálculos personalizados
* Criar relatórios de várias páginas com gráficos, tabelas e tabelas dinâmicas
* Criar formatação condicional e conteúdo dinâmico
* Acessar o modelo de dados completo do Campaign e os bancos de dados externos (FDA)


[Criar relatórios personalizados (console do cliente)](../reporting/custom-reports.md)

+++

+++ O que é um cubo e como posso usá-lo para relatórios?

Os cubos são estruturas de dados multidimensionais que permitem aos usuários empresariais explorar e analisar dados do Campaign por meio de tabelas dinâmicas sem habilidades técnicas. Considere-os como modelos de dados pré-configurados que simplificam relatórios complexos.


* Os usuários técnicos criam e configuram cubos que definem dimensões (tempo, geografia, canais) e medidas (aberturas, cliques, receita)
* Usuários empresariais selecionam um cubo ao criar relatórios e arrastam e soltam dimensões para explorar dados
* Os dados são agregados e calculados automaticamente com base na configuração do cubo
* Os resultados podem ser exibidos como tabelas dinâmicas, gráficos ou exportados para o Excel


[Explorar dados com cubos](../reporting/gs-cubes.md)

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

**Relatórios de pesquisa internos:**

* **Relatório geral** - Tendências de resposta ao longo do tempo, distribuição por origem e idioma
* **Detalhamento das respostas** - Detalhamento detalhado das respostas para cada pergunta
* **Relatório de documentação** - Representação visual da estrutura de pesquisa

**Análise avançada:**

* Acessar respostas de pesquisa da guia **[!UICONTROL Responses]** e exportar dados
* Use a atividade **[!UICONTROL Survey responses]** em fluxos de trabalho para direcionar destinatários com base em suas respostas
* Combinar dados da pesquisa com outros dados do Campaign para segmentação e personalização
* Criar relatórios e cubos personalizados para análise de pesquisa multidimensional


[Introdução às pesquisas](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Relatórios de pesquisa](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ Como posso compartilhar o acesso aos meus relatórios?

O Campaign oferece opções flexíveis para compartilhar relatórios com diferentes grupos de usuários, controlando visibilidade e permissões de acesso com base em funções e responsabilidades.

**Controle de acesso ao relatório:**

* **Permissões de pasta** - Coloque relatórios em pastas com acesso apropriado de leitura/gravação para grupos de usuários
* **Direitos nomeados** - Atribua direitos específicos para exibir, criar ou modificar relatórios
* **Contexto de exibição** - Defina onde os relatórios aparecem: na pasta **[!UICONTROL Reports]**, nas guias de campanha ou nas telas de entrega
* **Compartilhamento da interface da Web** - Compartilhe links de painel com membros da equipe por meio da interface da Web do Campaign

**Como configurar o acesso:**

1. Salve o relatório em uma pasta específica no console do cliente
2. Configurar permissões de acesso a pastas para grupos de operadores relevantes
3. Definir as propriedades do relatório: tipo de relatório, contexto de exibição e disponibilidade
4. Testar o acesso com um usuário do grupo-alvo antes de uma implantação mais ampla

**Prática recomendada:** crie pastas de relatório dedicadas para equipes diferentes (marketing, operações, gerenciamento) com permissões de acesso personalizadas. Finalidade do relatório do documento e agendamentos de atualização.

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

[Relatórios personalizados](../reporting/custom-reports.md) | [Relatórios de interface do usuário da Web do Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Desenvolvedores {#developers}

Acesse informações técnicas para desenvolvedores, incluindo detalhes do modelo de dados, esquemas, APIs e recursos de personalização.

+++ Qual é o modelo de dados do Campaign?

O modelo de dados do Campaign é uma estrutura de banco de dados relacional orientada por esquema que define como os dados de marketing são organizados e relacionados. Ele consiste em tabelas integradas para os principais objetos de marketing (recipients, deliveries, campanhas) e pode ser estendido para atender às suas necessidades comerciais específicas.

**Principais conceitos do modelo de dados:**

* **Esquemas** - definições XML que descrevem a estrutura da tabela, os campos e as relações
* **Tabelas internas** - Entidades de marketing principais (recipients, entregas, fluxos de trabalho, campanhas)
* **Links** - Relações entre tabelas (1-1, 1-N, N-N)
* **Enumerações** - Listas de valores predefinidas para campos suspensos
* **Extensões** - Campos e tabelas personalizados adicionados ao modelo padrão

**Principais esquemas internos:**

* **Destinatário (nms:recipient)** - Perfis de clientes e informações de contato
* **Entrega (nms:delivery)** - Campanhas por email, SMS e push
* **Fluxo de trabalho (xtk:workflow)** - Processos de automação
* **Campanha (nms:operation)** - Orquestração de campanha de marketing
* **Logs de rastreamento** - Abre, clica e dados de participação

**Por que é importante:** entender o modelo de dados é essencial para criar fluxos de trabalho, criar consultas, estender esquemas e desenvolver integrações personalizadas. A abordagem baseada em esquema garante a consistência dos dados e habilita recursos avançados de consulta.

[Modelo de dados do Campaign](../dev/datamodel.md) | [Práticas recomendadas do modelo de dados](../dev/datamodel-best-practices.md)

+++

+++ Como trabalhar com esquemas do Campaign?

Os esquemas são a base da estrutura de dados do Campaign, definindo tabelas, campos e relacionamentos no formato XML. Entender esquemas é fundamental para a personalização, a integração e o desenvolvimento avançado de fluxos de trabalho.

**O que os esquemas definem:**

* **Estrutura de tabela** - Tabelas de banco de dados e seus objetos de aplicativo correspondentes
* **Propriedades do campo** - Tipos de dados, rótulos, regras de validação e valores padrão
* **Relações** - Links entre tabelas (junções) e cardinalidade
* **Índices** - Otimização do banco de dados para desempenho de consulta
* **Controle de acesso** - Quais campos os usuários podem exibir e modificar

**Trabalhando com esquemas:**

* **Exibir esquemas:** Acesso via **[!UICONTROL Administration > Configuration > Data schemas]** no console do cliente
* **Estender esquemas:** crie esquemas de extensão (por exemplo, `cus:recipient` estende `nms:recipient`) para adicionar campos personalizados sem modificar os esquemas principais
* **Criar esquemas personalizados:** Crie tabelas totalmente novas para dados específicos de negócios
* **Atualizar banco de dados:** Aplicar alterações de esquema usando **[!UICONTROL Tools > Advanced > Update database structure]**

**Casos de uso comuns:**

* Adicionar campos personalizados à tabela de recipients (ID da empresa, nível de fidelidade, preferências)
* Criação de tabelas personalizadas para produtos, lojas ou transações
* Definição de relações entre tabelas personalizadas e integradas
* Implementação de modelos de dados específicos de negócios

**Importante:** nunca modifique esquemas internos diretamente. Sempre use esquemas de extensão para preservar a compatibilidade de atualização e o suporte ao Adobe.

[Introdução a esquemas](../dev/schemas.md) | [Estender um esquema](../dev/extend-schema.md)

+++

+++ Como usar uma tabela de destinatários personalizada?

O Campaign permite usar uma tabela personalizada em vez da tabela de recipients integrada quando sua empresa requer uma estrutura de dados diferente para o direcionamento (por exemplo, contas B2B, assinantes, clientes potenciais ou contatos externos).

**Por que usar uma tabela de destinatários personalizada:**

* Direcionar empresas B2B ou unidades organizacionais em vez de contatos individuais
* Separar dados do assinante do banco de dados do cliente principal
* Usar uma tabela de cliente existente de outro sistema
* Implementar arquiteturas de várias marcas com tabelas de contato separadas
* Cumprir requisitos específicos de governança de dados

**Etapas de implementação:**

1. Criar o esquema personalizado definindo a estrutura da tabela de destinatários
2. Incluir campos obrigatórios (email, chave primária, sinalizadores de exclusão)
3. Configurar target mappings para vincular sua tabela com deliveries
4. Atualizar modelos de entrega para usar o novo target mapping
5. Adaptar workflows e queries para fazer referência à tabela personalizada

**Principais considerações:**

* As tabelas de recipients personalizadas devem incluir campos obrigatórios para deliveries (email, exclusões, rastreamento)
* Os fluxos de trabalho e formulários precisam de adaptação para funcionar com a estrutura personalizada
* Alguns recursos integrados podem exigir personalização
* Os testes são essenciais antes de migrar campanhas de produção

**Prática recomendada:** comece com a extensão da tabela de destinatários padrão antes de considerar uma tabela personalizada. As tabelas de recipients personalizadas adicionam complexidade e só devem ser usadas quando realmente necessário.

[Tabela de destinatários personalizada](../dev/custom-recipient.md) | [Mapeamentos do Target](../audiences/target-mappings.md)

+++

+++ Quais são as práticas recomendadas para definir consultas no Campaign?

O editor de consultas do Campaign é uma ferramenta visual poderosa para criar consultas de banco de dados sem conhecimento em SQL. Dominar isso é essencial para o direcionamento, a segmentação e a análise de dados eficientes.

**Onde as consultas são usadas:**

* **Atividades do fluxo de trabalho** - Atividades Query, Split, Update data, Enrichment
* **Direcionamento de entrega** - Defina as populações de destinatários para campanhas
* **Listas** - Criar listas de destinatários dinâmicas ou estáticas
* **Relatórios** - Criar extrações e análises de dados personalizadas
* **Filtros** - Criar critérios de direcionamento reutilizáveis

**Práticas recomendadas de consulta:**

* **Iniciar simples** - Criar consultas de forma incremental, testando em cada etapa
* **Usar dimensões de filtragem** - Aproveitar relações entre tabelas (destinatários → entregas → logs de rastreamento)
* **Otimizar desempenho** - Indexar campos consultados com frequência, evitar campos calculados complexos
* **Usar filtros predefinidos** - Reutilizar e combinar filtros existentes para fins de consistência
* **Teste com amostras pequenas** - Valide a lógica da consulta antes de executar no banco de dados completo
* **Consultas complexas de documentos** - Adicione descrições para manutenção e transferência de conhecimento

**Padrões de consulta comuns:**

* Destinatários do Target que abriram um delivery específico: filtrar logs de rastreamento vinculados aos recipients
* Localizar contatos inativos: consulta na última data de entrega ou atividade de rastreamento
* Segmentar por comportamento: combinar critérios de entrega, rastreamento e perfil
* Excluir recipients anteriores: usar operações de conjunto (união, interseção, exclusão)

**Acesse o editor de consulta genérico:** **[!UICONTROL Tools > Generic query editor]** para exploração de banco de dados ad-hoc e extração de dados fora de fluxos de trabalho.

[Editor de consultas](../start/query-editor.md) | [Atividade de query em fluxos de trabalho](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=pt-BR){target="_blank"}

+++

+++ Como posso importar um pacote de dados?

Os pacotes de dados permitem exportar e importar configurações do Campaign (schemas, workflows, tipologias, filtros) e dados entre instâncias. Isso é essencial para implantar configurações desde o desenvolvimento até a produção ou compartilhar componentes entre organizações.

**O que pode ser empacotado:**

* **Objetos de configuração** - Esquemas, fluxos de trabalho, regras de tipologia, formulários, filtros
* **Componentes da campanha** - Modelos de entrega, modelos de campanha, blocos de conteúdo
* **Configurações do aplicativo** - Operadores, grupos de operadores, estruturas de pastas
* **Dados** - Listas de destinatários, seed addresses, fragmentos de conteúdo
* **Desenvolvimentos personalizados** - código JavaScript, scripts SQL, aplicativos Web


**Tipos de pacote:**

* **Pacote do usuário** - Configurações personalizadas que você cria e exporta
* **Pacote de plataforma** - recursos e atualizações fornecidos pela Adobe
* **Pacote de dados** - Contém registros de dados reais, não apenas a estrutura

**Práticas recomendadas:**

* Sempre exportar pacotes da mesma versão ou de uma versão mais antiga do Campaign
* Testar importações de pacotes no ambiente de desenvolvimento antes da produção
* Conteúdo e dependências do pacote de documentos
* Usar controle de versão para arquivos XML de pacote
* Fazer backup da instância antes das importações de pacote principal

[Trabalhar com pacotes de dados](../dev/packages.md)

+++

+++ Onde posso encontrar a lista de APIs do Campaign v8?

O Campaign v8 fornece uma documentação abrangente de API que abrange APIs do SOAP (para interações do console do cliente) e APIs REST (para integrações modernas). A referência da API inclui todos os métodos, parâmetros e formatos de resposta disponíveis.

**Tipos de API do Campaign:**

* **APIs do SOAP** - APIs tradicionais para operações de console do cliente do Campaign, manipulação de esquemas e controle de fluxos de trabalho
* **REST APIs** - APIs HTTP modernas para integrações de sistema externas, gerenciamento de perfis e acionamento de eventos
* **APIs do JavaScript** - APIs de script do lado do servidor para atividades de fluxo de trabalho e lógica de negócios personalizada

**Recursos da documentação da API:**

* **Referência da API completa:** documentação abrangente da API do SOAP com assinaturas de método, parâmetros e exemplos
* **Guia da API REST:** endpoints REST modernos para perfis, eventos e unidades organizacionais
* **API do JavaScript:** funções do lado do servidor disponíveis em scripts de fluxo de trabalho e aplicativos Web

**Casos de uso comuns da API:**

* Integrar o Campaign com aplicativos de CRM, ERP ou personalizados
* Automatizar operações de campanha e execução de fluxo de trabalho
* Sincronizar dados entre sistemas em tempo real
* Criar soluções personalizadas de monitoramento e alerta
* Criar interfaces externas para dados e operações do Campaign

**Acesso:** [Documentação da API do Campaign v8](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=pt-BR){target="_blank"}

+++


+++ Como monitorar workflows da API?

As APIs do Campaign permitem controlar e monitorar programaticamente a execução do fluxo de trabalho, habilitando sistemas de monitoramento externos, alertas automatizados e soluções de orquestração personalizadas.

**O que você pode fazer por meio da API:**

* **Iniciar fluxos de trabalho** - Acionar a execução do fluxo de trabalho de forma programática
* **Pausar/Retomar fluxos de trabalho** - Controlar fluxo de execução de fluxo de trabalho
* **Parar fluxos de trabalho** - Encerrar fluxos de trabalho em execução
* **Status do fluxo de trabalho de consulta** - Verifique se os fluxos de trabalho estão em execução, pausados ou concluídos
* **Recuperar logs** - Acessar logs de execução de fluxo de trabalho e mensagens de erro
* **Monitorar progresso da atividade** - Rastrear conclusão de atividade de fluxo de trabalho individual

**Métodos de API:**

* `xtk:workflow#Start` - Iniciar uma instância de fluxo de trabalho
* `xtk:workflow#Pause` - Pausar fluxo de trabalho em execução
* `xtk:workflow#Stop` - Interromper a execução do fluxo de trabalho
* `xtk:workflow#GetState` - Obter o estado atual do fluxo de trabalho
* `xtk:workflow#GetLogs` - Recuperar logs de execução

**Casos de uso comuns:**

* Criar painéis de monitoramento personalizados mostrando a integridade do fluxo de trabalho
* Implementar alertas automatizados quando os fluxos de trabalho falharem ou forem executados por muito tempo
* Orquestrar workflows de schedulers externos ou sistemas de eventos
* Criar dependências de fluxo de trabalho em várias instâncias do Campaign
* Gerar relatórios de execução de fluxo de trabalho personalizados

**Prática recomendada:** combine o monitoramento da API com a trilha de auditoria do fluxo de trabalho para obter uma governança abrangente do fluxo de trabalho. Use ferramentas de monitoramento externas para rastrear SLAs de fluxo de trabalho e métricas de desempenho.

[Controlar workflows por meio da API](../dev/api/controlling-a-workflow.md)

+++

+++ Como posso atualizar a estrutura do banco de dados?

Após modificar os esquemas do Campaign (adicionar campos, criar tabelas, alterar tipos de dados), você deve atualizar a estrutura do banco de dados físico para aplicar as alterações. Essa sincronização garante que o banco de dados corresponda às definições do esquema.

**Quando são necessárias atualizações do banco de dados:**

* Adição de novos campos a esquemas existentes
* Criação de tabelas personalizadas ou extensão de tabelas integradas
* Modificação das propriedades do campo (tipo de dados, comprimento, status obrigatório)
* Adição ou remoção de links entre tabelas
* Criação de novos índices para otimização de consulta


**Considerações importantes:**

* **Fazer backup primeiro** - Sempre fazer backup do banco de dados antes das alterações estruturais
* **Teste em desenvolvimento** - Valide as alterações de esquema no ambiente de desenvolvimento antes da produção
* **Planejamento de tempo de inatividade** - Grandes alterações estruturais podem exigir breves janelas de manutenção
* **Para Managed Cloud Services** - Coordene as principais alterações com o suporte da Adobe
* **Reversibilidade** - Algumas alterações (como a remoção de campos) podem causar perda de dados

**Prática recomendada:** usar controle de versão e alterações de esquema. Documente todas as modificações personalizadas do esquema para manutenção e solução de problemas.

[Atualizar estrutura do banco de dados](../dev/update-database-structure.md) | [Estender esquema](../dev/extend-schema.md)

+++

+++ Quais são as limitações do Campaign v8?

O Campaign v8 apresenta alterações de arquitetura (principalmente em implantações FFDA) que trazem melhorias significativas de desempenho, mas também algumas diferenças em relação ao Campaign Classic v7. Compreendê-los ajuda a planejar migrações e a definir expectativas apropriadas.

**Considerações principais sobre a v8:**

* **Arquitetura FFDA** - As implantações corporativas usam o banco de dados em nuvem (Snowflake) com diferentes padrões de acesso a dados
* **Atualizações de unidade** - As atualizações de dados devem ser feitas em fluxos de trabalho, não por meio de APIs ou acesso direto ao banco de dados
* **Gravações em tempo real** - Otimizadas para operações em lote em vez de atualizações individuais de alta frequência
* **Modelo de dados** - Algumas personalizações de esquema requerem abordagens diferentes
* **Acesso ao banco de dados externo** - A configuração FDA (Federated Data Access) é diferente da v7

**Recursos não disponíveis em implantações FFDA:**

* Pesquisas (disponíveis em implantações padrão do v8)
* Gerenciamento dos recursos de marketing (MRM)
* Algumas configurações específicas de conector

**Considerações sobre migração:**

* O código personalizado usando gravações diretas no banco de dados precisa ser refatorado
* As integrações de API podem exigir adaptação para processamento em lote
* Os workflows devem seguir as práticas recomendadas do FFDA para operações de dados
* Testes são essenciais para validar desenvolvimentos personalizados

**Importante:** essas limitações estão evoluindo à medida que a Adobe continua aprimorando o v8. Consulte a documentação mais recente para obter o status atual e o roteiro.

[Migração do Campaign v7 para v8](../start/v7-to-v8.md#limitations) | [Arquitetura FFDA](../architecture/enterprise-deployment.md)

+++

## Privacidade {#privacy}

Entenda como o Adobe Campaign ajuda você a cumprir as regras de privacidade, como o GDPR e o CCPA, e gerenciar solicitações de titulares de dados.

+++ Quais são os principais conceitos de privacidade do Campaign?

O Campaign ajuda você a cumprir as regras de privacidade (GDPR, CCPA, PDPA, LGPD) por meio de ferramentas para gerenciar direitos, consentimento e retenção de dados do titular dos dados. Os principais conceitos incluem regulamentos de privacidade, identificação de dados pessoais, direitos do titular dos dados (acesso, exclusão, portabilidade), gerenciamento de consentimento e políticas de retenção de dados.

Como Controlador de dados, você é responsável por lidar com solicitações de titulares de dados, manter registros de consentimento e garantir o uso transparente dos dados.

[Gerenciamento de privacidade](../start/privacy.md)

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

[Gerenciamento de privacidade](../start/privacy.md)

+++

+++ Como devo coletar e gerenciar o consentimento do usuário?

O consentimento válido requer um acordo ativo, específico, informado e revogável. Os usuários devem tomar medidas explícitas — sem caixas pré-marcadas ou silêncio como consentimento. Consentimentos separados para diferentes propósitos (desagregados), fornecer explicações claras e manter registros com carimbos de data e hora.

**Práticas recomendadas**: forneça opções de aceitação granulares, atualize o consentimento periodicamente, torne os centros de preferências fáceis de acessar e enquadre o consentimento como um aumento de confiança.

O Campaign oferece serviços de assinatura, centros de preferências, campos de consentimento personalizados com rastreamento de carimbo de data e hora e atualização de consentimento baseada em fluxo de trabalho.

[Assinaturas](../start/subscriptions.md) | [Privacidade e consentimento](../start/privacy.md#consent-retention-roles)

+++

+++ Como implementar o gerenciamento de consentimento no Campaign?

O Campaign fornece serviços de assinatura, centros de preferências, sinalizadores de recusa e campos de consentimento personalizados para rastrear o consentimento.

**Abordagem de implementação:** Estenda o esquema do destinatário para campos de consentimento (data, tipo, origem), crie serviços de assinatura para cada tipo de consentimento, crie formulários Web do centro de preferências, use fluxos de trabalho para impor o consentimento no direcionamento e mantenha as trilhas de auditoria.

Consulte o departamento jurídico para garantir que sua implementação atenda aos requisitos normativos.

[Serviços de assinatura](../start/subscriptions.md) | [Gerenciamento de privacidade](../start/privacy.md)

+++

+++ Quais dados são excluídos quando procuro uma solicitação de exclusão?

O Campaign exclui automaticamente todos os dados vinculados a um titular de dados: perfil do recipient, logs de delivery e rastreamento, dados personalizados com relacionamentos de propriedade, histórico de subscrição e dados de rastreamento Web.

**Como funciona:** o Campaign exclui todos os dados nos quais o link para o destinatário tem `integrity="own"` na definição do esquema, garantindo a exclusão em cascata nas tabelas relacionadas.

Você pode personalizar o escopo de exclusão modificando a integridade do link em esquemas, mas consulte o departamento jurídico primeiro. A exclusão é permanente e não pode ser desfeita.

[Gerenciamento de privacidade](../start/privacy.md) | [Links de esquema](../dev/schemas.md)

+++

+++ As exclusões de privacidade afetam meus relatórios de entrega?

Não. Os relatórios de campanha são baseados em métricas agregadas pré-calculadas (total enviado, aberturas, cliques), não em consultas ativas em logs individuais. A exclusão de dados de destinatários individuais não altera as estatísticas agregadas históricas.

As estatísticas de entrega gerais e as métricas de desempenho permanecem intactas, enquanto os logs de rastreamento individuais e os detalhes pessoais são removidos. Dessa forma, você pode manter as análises de marketing e, ao mesmo tempo, respeitar os direitos do titular dos dados.

[Gerenciamento de privacidade](../start/privacy.md) | [Relatórios](../reporting/gs-reporting.md)

+++

+++ Como evitar a reimportação de dados excluídos?

Você deve excluir os dados de todos os sistemas de origem, não apenas do Campaign. Os dados geralmente fluem de sistemas externos (CRM, comércio eletrônico, data warehouses).

**Ações necessárias:** identifique todas as fontes de dados, exclua dos sistemas de origem, adicione a listas de exclusão/supressão, atualize fluxos de trabalho de importação para respeitar sinalizadores de exclusão e documente o processo.

Como controlador de dados, você é responsável pela remoção completa dos dados em todo o seu ecossistema de tecnologia.

[Gerenciamento de privacidade](../start/privacy.md) | [Importar fluxos de trabalho](../config/workflows.md)

+++

+++ Usuários excluídos podem aceitar novamente?

Sim. Os titulares de dados podem aceitar novamente após a exclusão. O Campaign cria um registro de recipient completamente novo sem link para dados excluídos anteriores; o perfil começa com uma tabulação limpa.

A trilha de auditoria do Campaign registra o evento de exclusão e a criação do novo perfil, demonstrando a conformidade e mostrando que a nova aceitação foi fornecida livremente após a exclusão.

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

* **[Página inicial de documentação do Campaign v8](../campaign-home.md)** - Documentação completa do produto
* **[Tutoriais do Campaign](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=pt-BR){target="_blank"}** - guias de vídeo passo a passo e tutoriais práticos
* **[Novidades](whats-new.md)** - Recursos e funcionalidades mais recentes
* **[Notas de versão](release-notes.md)** - Informações de versões atuais e anteriores
* **[Versões e atualizações](upgrades.md)** - Saiba mais sobre versões e atualizações do Campaign e como verificar sua versão
* **[Práticas recomendadas](delivery-best-practices.md)** - Abordagens recomendadas para tarefas comuns

### Recursos técnicos

Encontre documentação técnica detalhada e recursos do desenvolvedor.

* **[APIs do Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=pt-BR){target="_blank"}** - Documentação de referência de API concluída
* **[GitHub da campanha](https://github.com/AdobeDocs/campaign.en)** - Contribuir com a documentação
* **[Notas técnicas](https://experienceleague.adobe.com/pt-br/docs/campaign/technotes-ac/technotes-home){target="_blank"}** - Artigos técnicos detalhados
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

* **[Serviços de aprendizado digital da Adobe](https://learning.adobe.com/){target="_blank"}** - Cursos oficiais ministrados por instrutores e individualizados
* **[Certificação da Adobe Campaign](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - Valide sua experiência com a certificação profissional
* **[Caminhos de aprendizagem do Experience League](https://experienceleague.adobe.com/?lang=pt-BR#dashboard/learning){target="_blank"}** - jornadas de aprendizagem guiadas

### Outros recursos úteis

* **[Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=pt-BR){target="_blank"}** - Referência para usuários do Classic v7
* **[Documentação da interface da Web do Campaign](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Novo guia de interface da Web
* **[Práticas recomendadas de capacidade de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR){target="_blank"}** - Otimizar a entrega de emails
* **[Atualizações de produto](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current){target="_blank"}** - Atualizações mais recentes do Adobe Experience Cloud

**Última atualização:** novembro de 2025 | **Aplica-se a:** Campaign v8.6 e posterior

*Encontrou um erro ou deseja sugerir uma melhoria? [Editar esta página no GitHub](https://github.com/AdobeDocs/campaign.en/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

