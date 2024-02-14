---
title: Arquitetura geral
description: Saiba mais sobre a arquitetura e os componentes do Adobe Campaign. Saiba mais sobre como personalizar o console e o ambiente do cliente.
feature: Architecture, Deployment
role: Admin, Developer
level: Beginner
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 79d916c4d65c0c55ec20f2f5850fec40fe4e99a3
workflow-type: tm+mt
source-wordcount: '1136'
ht-degree: 6%

---

# Arquitetura geral{#general-architecture}

A implantação típica da solução Adobe Campaign consiste nos seguintes componentes:

* **Ambiente personalizado do cliente**

  Interface gráfica intuitiva na qual os usuários podem se comunicar e rastrear ofertas de marketing, criar campanhas, revisar e gerenciar todas as atividades de marketing, programas e planos, incluindo emails, fluxos de trabalho e páginas de aterrissagem, criar e gerenciar perfis de clientes e criar públicos.

* **Ambiente de desenvolvimento**

  Software do lado do servidor que executa as campanhas de marketing por meio de canais de comunicação escolhidos, incluindo emails, SMS, notificações por push, correspondência direta, Web ou redes sociais, com base nas regras e fluxos de trabalho definidos na interface do usuário.

* **Contêineres do Banco de Dados**

  Com base na tecnologia de banco de dados relacional, o banco de dados do Adobe Campaign Cloud armazena todas as informações, componentes de campanha, ofertas, fluxos de trabalho e resultados de campanha em containers de banco de dados.

## Ambiente personalizado do cliente {#client-env}

O aplicativo pode ser acessado de diferentes maneiras: interface de usuário da Web, console do cliente (cliente avançado), acesso à Web (cliente thin) ou integração de API.

![](../assets/do-not-localize/glass.png) [Saiba mais sobre a interface do usuário do Campaign](../start/campaign-ui.md).

## Ambiente de desenvolvimento {#dev-env}

O Adobe Campaign é uma plataforma única com diferentes aplicativos para criar uma arquitetura aberta e escalável. A plataforma Adobe Campaign foi criada em uma camada de aplicativo flexível e pode ser facilmente configurada para atender às suas necessidades comerciais. A arquitetura distribuída garante escalabilidade linear do sistema, de milhares a milhões de mensagens.

Alguns módulos do Campaign operam continuamente, enquanto outros são iniciados ocasionalmente para executar tarefas administrativas (por exemplo, configurar a conexão de banco de dados) ou para executar uma tarefa recorrente (por exemplo, consolidar informações de rastreamento).

Há três tipos de módulos do Adobe Campaign:

* **Módulos de várias instâncias**: um único processo é executado para todas as instâncias. Isso se aplica aos seguintes módulos: web, syslogd, trackinglogd e watchdog.
* **Módulos de instância única**: um processo é executado por instância. Isso se aplica aos seguintes módulos: mta, wfserver, inMail, sms e stat.
* **Módulos de utilitário**: são módulos executados ocasionalmente para executar operações ocasionais ou recorrentes (limpeza, configuração, download de logs de rastreamento etc.).

Os principais processos são:

* **Servidor de aplicativos** (nlserver web) - Esse processo expõe a gama completa de funcionalidades do Adobe Campaign por meio de APIs de serviços da Web (SOAP / HTTP + XML). Além disso, ele pode gerar dinamicamente as páginas da Web usadas para o acesso baseado em HTML (relatórios, formulários Web etc.). Para fazer isso, esse processo inclui um servidor JSP Apache Tomcat. Esse é o processo ao qual o Console se conecta.

* **Mecanismo de fluxo de trabalho** (nlserver wfserver) - Esse processo executa os processos de workflow definidos no aplicativo. Também lida com workflows técnicos executados periodicamente, incluindo:

   * **Rastreamento**: recupera e consolida logs de rastreamento, para que você possa recuperar os logs do servidor de redirecionamento e criar os indicadores agregados usados pelo módulo de relatórios.
   * **Cleanup**: limpa o banco de dados, elimina registros antigos e evita que o banco de dados cresça exponencialmente.
   * **Faturamento**: envia um relatório de atividades para a plataforma (tamanho do banco de dados, número de ações de marketing etc.).

* **Servidor de entrega** (nlserver mta) - o Adobe Campaign tem funcionalidade nativa de transmissão de email. Esse processo funciona como um agente de transferência de email SMTP (MTA). Ele executa a personalização &quot;um para um&quot; das mensagens e lida com a entrega física. Ele é executado usando processos de entrega e trata de tentativas automáticas. Além disso, quando o rastreamento é ativado, ele substitui automaticamente os URLs para que eles apontem para o servidor de redirecionamento. Esse processo pode lidar com a personalização e o envio automático para um roteador de terceiros para SMS, fax e correspondência direta.

* **Servidor de redirecionamento** (nlserver webmdl) - Para email, o Adobe Campaign lida automaticamente com o rastreamento de cliques e aberturas (o rastreamento transacional no nível do site é uma outra possibilidade). Para isso, os URLs incorporados nas mensagens de email são reescritos para apontar para esse módulo, que registra a passagem do usuário da Internet antes de redirecioná-lo para o URL necessário.

  Para garantir a maior disponibilidade, esse processo é totalmente independente do banco de dados: os outros processos do servidor se comunicam com ele usando chamadas SOAP (HTTP, HTTP(S) e XML) apenas. Tecnicamente, essa funcionalidade é implementada em um módulo de extensão de um servidor HTTP (extensão ISAPI no IIS, ou um módulo DSO Apache etc.) e está disponível somente no Windows.

Outros processos mais técnicos também estão disponíveis:

* **Gestão de emails de devolução** (nlserver inMail) - Esse processo permite que você colete automaticamente emails de caixas de correio configuradas para receber mensagens devolvidas que são retornadas em caso de falha no delivery. Essas mensagens são submetidas a processamento com base em regras para determinar os motivos para a não entrega (recipient desconhecido, cota excedida etc.) e para atualizar o status do delivery no banco de dados. Todas essas operações são totalmente automáticas e pré-configuradas.

* **Status de entrega do SMS** (nlserver sms) - Esse processo pesquisa o roteador SMS para coletar o status do progresso e atualizar o banco de dados.

* **Gravando mensagens de log** (nlserver syslogd) - Esse processo técnico captura mensagens e rastreamentos de log gerados por outros processos e os grava no disco rígido. Isso disponibiliza amplas informações para o diagnóstico em caso de problemas.

* **Gravação de logs de rastreamento** (nlserver trackinglogd) - Esse processo salva em disco os logs de rastreamento gerados pelo processo de redirecionamento.

* **Gravação de eventos de entrada** (nlserver interaction) - Esse processo garante o registro no disco de eventos de entrada, dentro da estrutura de Interação.

* **Supervisão de módulos** (nlserver watchdog) - Esse processo técnico atua como um processo principal que gera os outros. Ele também os monitora e reinicia automaticamente em caso de incidentes, mantendo o máximo de tempo de atividade do sistema.

* **Servidor de estatísticas** (nlserver stat) - Esse processo mantém estatísticas sobre o número de conexões, as mensagens enviadas para cada servidor de e-mail para o qual as mensagens são enviadas, bem como suas limitações (maior número de conexões simultâneas, mensagens por hora/e/ou conexão). Ela também permite federar várias instâncias ou máquinas se compartilharem os mesmos endereços IP públicos.


## Contêineres de banco de dados {#db-containers}

No seu [Implantação corporativa (FFDA)](enterprise-deployment.md), o banco de dados do Adobe Campaign Cloud depende [!DNL Snowflake] que contém os dados funcionais (perfis, assinaturas, conteúdo, etc.), os dados técnicos (tarefas de delivery e logs, logs de rastreamento etc.) e os dados de trabalho (compras, clientes potenciais) da solução, e todos os componentes do Adobe Campaign se comunicam com o banco de dados para executar suas tarefas específicas.

Você pode implantar o Adobe Campaign usando o banco de dados e os esquemas predefinidos e, se necessário, esse ambiente predefinido pode ser estendido. Todos os dados no data mart são acessados pela Adobe Campaign por meio de chamadas SQL. O Adobe Campaign também fornece um complemento completo de ferramentas de ETL (Extract Transform and Load, Transformação e Carregamento de Extração) para executar a importação e exportação de dados para dentro e para fora do sistema.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Com o **Campaign Managed Cloud Services**, o ambiente e a configuração inicial foram definidos pela Adobe, de acordo com os termos do contrato de licença. Você não tem permissão para modificar pacotes incorporados instalados, esquemas ou relatórios incorporados.
>
>Se precisar usar um complemento do Campaign ou um recurso específico que não foi fornecido para você, entre em contato com o **Atendimento ao cliente da Adobe**.

## Armazenamento de banco de dados {#db-storage}

A permissão de armazenamento total é dividida entre o banco de dados principal e o banco de dados secundário Snowflake (opcional). O local onde os dados são armazenados deve ser determinado na implementação ou no momento da atualização, dependendo dos casos de uso específicos do cliente.

Saiba como monitorar o uso do banco de dados no [Documentação do Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring.html){target="_blank"}.