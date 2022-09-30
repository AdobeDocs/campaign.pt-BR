---
title: Arquitetura geral
description: Saiba mais sobre a arquitetura e os componentes do Campaign
feature: Architecture
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 6%

---

# Arquitetura geral{#general-architecture}

A implantação típica da solução Adobe Campaign consiste nos seguintes componentes:

* **Ambiente de cliente personalizado**

   Interface gráfica intuitiva na qual os usuários podem se comunicar e rastrear ofertas de marketing, criar campanhas, revisar e gerenciar todas as atividades, programas e planos de marketing - incluindo emails, fluxos de trabalho e páginas de aterrissagem -, criar e gerenciar perfis de clientes e criar públicos.

* **Ambiente de desenvolvimento**

   Software do lado do servidor que executa as campanhas de marketing por meio de canais de comunicação escolhidos, incluindo emails, SMS, notificações por push, mala direta, Web ou social, com base nas regras e fluxos de trabalho definidos na interface do usuário.

* **Contêineres de Banco de Dados**

   Com base na tecnologia de banco de dados relacional, o Adobe Campaign Cloud Database armazena todas as informações, componentes de campanha, ofertas, workflows e resultados de campanha em contêineres de banco de dados.

## Ambiente de cliente personalizado {#client-env}

O aplicativo pode ser acessado de diferentes maneiras: Integração avançada de cliente, cliente thin ou API.

![](../assets/do-not-localize/glass.png) [Saiba mais sobre a camada de apresentação do Campaign](../start/ac-components.md).

## Ambiente de desenvolvimento {#dev-env}

O Adobe Campaign é uma plataforma única com aplicativos diferentes para criar uma arquitetura aberta e escalável. A plataforma Adobe Campaign é gravada em uma camada de aplicativo flexível e pode ser facilmente configurada para atender às suas necessidades comerciais. A arquitetura distribuída garante a escalabilidade linear do sistema, de milhares de mensagens a milhões de mensagens.

Alguns módulos do Campaign operam continuamente, enquanto outros são iniciados ocasionalmente para executar tarefas administrativas (por exemplo, para configurar a conexão do banco de dados) ou para executar uma tarefa recorrente (por exemplo, consolidando informações de rastreamento).

Existem três tipos de módulos Adobe Campaign:

* **Módulos de várias instâncias**: um único processo é executado para todas as instâncias. Isso se aplica aos seguintes módulos: web, syslogd, trackinglogd e watchdog.
* **Módulos de instância única**: um processo é executado por instância. Isso se aplica aos seguintes módulos: mta, wfserver, inMail, sms e stat.
* **Módulos do utilitário**: são módulos executados ocasionalmente para executar operações ocasionais ou recorrentes (limpeza, configuração, download de logs de rastreamento etc.).

Os principais processos são:

* **Servidor de aplicativos** (nlserver web) - Esse processo expõe a gama completa da funcionalidade do Adobe Campaign por meio das APIs de Serviços da Web (SOAP / HTTP + XML). Além disso, ele pode gerar dinamicamente as páginas da Web usadas para acesso baseado em HTML (relatórios, formulários Web etc.). Para isso, esse processo inclui um servidor JSP Apache Tomcat. Esse é o processo ao qual o Console se conecta.

* **Mecanismo de workflow** (nlserver wfserver) - Esse processo executa os processos de workflow definidos no aplicativo. Também lida com workflows técnicos executados periodicamente, incluindo:

   * **Rastreamento**: Recupera e consolida logs de rastreamento, de modo que você possa recuperar os logs do servidor de redirecionamento e criar os indicadores agregados usados pelo módulo de relatórios.
   * **Limpeza**: Limpa o banco de dados e elimina registros antigos e evita que o banco de dados cresça exponencialmente.
   * **Faturamento**: Envia um relatório de atividade para a plataforma (tamanho do banco de dados, número de ações de marketing etc.).

* **Servidor de entrega** (nlserver mta) - A Adobe Campaign tem funcionalidade nativa de transmissão de email. Esse processo funciona como um agente de transferência de email SMTP (MTA). Ele executa a personalização &quot;um para um&quot; de mensagens e manipula sua entrega física. Ele é executado usando tarefas de delivery e lida com tentativas automáticas. Além disso, quando o rastreamento é ativado, ele substitui automaticamente os URLs para que apontem para o servidor de redirecionamento. Esse processo pode lidar com a personalização e o envio automático para um roteador de terceiros para SMS, fax e mala direta.

* **Redirecionar servidor** (nlserver webmdl) - Para email, o Adobe Campaign trata automaticamente o rastreamento de cliques e aberturas (o rastreamento transacional no nível do site é uma outra possibilidade). Para isso, os URLs incorporados nas mensagens de email são reescritos para apontar para esse módulo, que registra a passagem do usuário da Internet antes de redirecioná-los para o URL necessário.

   Para garantir a maior disponibilidade, esse processo é totalmente independente do banco de dados: os outros processos de servidor se comunicam com ele usando chamadas SOAP (HTTP, HTTP(S) e XML) somente. Tecnicamente, essa funcionalidade é implementada em um módulo de extensão de um servidor HTTP (extensão ISAPI no IIS ou um módulo DSO Apache etc.) e está disponível somente no Windows.

Outros processos mais técnicos também estão disponíveis:

* **Gestão de emails de devolução** (nlserver inMail) - Esse processo permite coletar automaticamente emails de caixas de correio configuradas para receber mensagens devolvidas em caso de falha no delivery. Essas mensagens passam por um processamento com base em regras para determinar os motivos para não entrega (recipient desconhecido, cota excedida, etc.) e para atualizar o status do delivery no banco de dados. Todas essas operações são totalmente automáticas e pré-configuradas.

* **Status do delivery SMS** (nlserver sms) - Esse processo pesquisa o roteador SMS para coletar o status de progresso e atualizar o banco de dados.

* **Gravando mensagens de log** (nlserver syslogd) - Esse processo técnico captura mensagens de log e rastreamentos gerados pelos outros processos e as grava no disco rígido. Isso disponibiliza amplas informações para diagnóstico em caso de problemas.

* **Gravação de logs de rastreamento** (nlserver trackinglogd) - Esse processo salva em disco os logs de rastreamento gerados pelo processo de redirecionamento.

* **Gravação de eventos de entrada** (nlserver interaction) - Esse processo garante a gravação no disco de eventos de entrada, dentro da estrutura de interação.

* **Supervisão de módulos** (nlserver watchdog) - Esse processo técnico atua como um processo principal que cria os outros. Ele também os monitora e reinicializa automaticamente em caso de incidentes, mantendo assim o tempo máximo de atividade do sistema.

* **Servidor de estatísticas** (nlserver stat) - Esse processo mantém estatísticas sobre o número de conexões, as mensagens enviadas para cada servidor de email para o qual as mensagens são enviadas, bem como suas limitações (o maior número de conexões simultâneas, mensagens por hora/e ou conexão). Também permite federar várias instâncias ou máquinas se elas compartilharem os mesmos endereços IP públicos.

## Contêineres de banco de dados {#db-containers}

O banco de dados da Adobe Campaign Cloud depende do [!DNL Snowflake] que contém os dados funcionais (perfis, assinaturas, conteúdo etc.), os dados técnicos (tarefas e logs do delivery, logs de rastreamento etc.) e os dados de trabalho (compras, clientes em potencial) da solução, e todos os componentes do Adobe Campaign se comunicam com o banco de dados para executar suas tarefas específicas.

Você pode implantar o Adobe Campaign usando o banco de dados e os esquemas predefinidos e, se necessário, esse ambiente predefinido pode ser estendido. Todos os dados no data mart são acessados pela Adobe Campaign através de chamadas SQL. A Adobe Campaign também fornece um complemento completo das ferramentas Extrair transformação e carregamento (ETL) para executar a importação e exportação de dados para dentro e para fora do sistema.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Com o **Campaign Managed Cloud Services**, o ambiente e a configuração inicial foram definidos pela Adobe, de acordo com os termos do contrato de licença. Você não tem permissão para modificar pacotes incorporados instalados, esquemas ou relatórios incorporados.
>
>Se precisar usar um complemento do Campaign ou um recurso específico que não foi fornecido para você, entre em contato com o **Atendimento ao cliente da Adobe**.