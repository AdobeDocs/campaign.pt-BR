---
title: Arquitetura geral
description: Saiba mais sobre a arquitetura e os componentes do Campaign
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 8%

---

# Arquitetura geral{#general-architecture}

A implantação típica da solução Adobe Campaign consiste nos seguintes componentes:

* **Ambiente de cliente personalizado**

   Interface gráfica intuitiva na qual os usuários podem se comunicar e rastrear ofertas de marketing, criar campanhas, revisar e gerenciar todas as atividades, programas e planos de marketing - incluindo emails, fluxos de trabalho e páginas de aterrissagem -, criar e gerenciar perfis de clientes e criar públicos.

* **Ambiente de desenvolvimento**

   Software do lado do servidor que executa as campanhas de marketing por meio de canais de comunicação escolhidos, incluindo emails, SMS, notificações por push, mala direta, Web ou social, com base nas regras e fluxos de trabalho definidos na interface do usuário.

* **Contêineres de Banco de Dados**

   Com base na tecnologia de banco de dados relacional, o Adobe Campaign Cloud Database armazena todas as informações dos clientes, componentes da campanha, ofertas e workflows, bem como os resultados da campanha em contêineres de banco de dados do cliente.

## Ambiente de cliente personalizado {#client-env}

O aplicativo pode ser acessado de diferentes maneiras: Integração avançada de cliente, cliente thin ou API.

* **Console** do cliente: A principal interface de usuário do aplicativo é um aplicativo nativo (no Windows) que se comunica com o servidor de aplicativos Adobe Campaign com protocolos padrão de Internet (SOAP, HTTP etc.). O console do cliente Adobe Campaign oferece excelente facilidade de uso para produtividade, usa pouca largura de banda (por meio do uso de um cache local) e foi projetado para facilitar a implantação. Esse Console pode ser implantado a partir de um navegador da Internet, pode ser atualizado automaticamente e não requer nenhuma configuração de rede específica, pois gera apenas tráfego HTTP(S).

   ?? [Saiba mais sobre o Console do Cliente do Campaign](../start/connect.md).

* **Acesso** à Web: partes do aplicativo podem ser acessadas por um navegador da Web simples usando uma interface de usuário HTML, incluindo o módulo de relatório, estágios de aprovação de delivery, monitoramento de instância etc.

   ?? [Saiba mais sobre o Campaign Web Access](../start/connect.md).

* **APIs** do Campaign: Em certos casos, o sistema pode ser chamado de aplicativo externo usando as APIs de serviços da Web expostas por meio do protocolo SOAP.

   ?? [Saiba mais sobre as APIs do Campaign](../dev/api.md).

## Ambiente de desenvolvimento {#dev-env}

O Adobe Campaign é uma plataforma única com aplicativos diferentes para criar uma arquitetura aberta e escalável. A plataforma Adobe Campaign é gravada em uma camada de aplicativo flexível e pode ser facilmente configurada para atender às suas necessidades comerciais. A arquitetura distribuída garante a escalabilidade linear do sistema, de milhares de mensagens a milhões de mensagens.

Alguns módulos do Campaign operam continuamente, enquanto outros são iniciados ocasionalmente para executar tarefas administrativas (por exemplo, para configurar a conexão do banco de dados) ou para executar uma tarefa recorrente (por exemplo, consolidando informações de rastreamento).

Existem três tipos de módulos Adobe Campaign:

* **Módulos** de várias instâncias: um único processo é executado para todas as instâncias. Isso se aplica aos seguintes módulos: web, syslogd, trackinglogd e watchdog.
* **Módulos** de mono-instância: um processo é executado por instância. Isso se aplica aos seguintes módulos: mta, wfserver, inMail, sms e stat.
* **Módulos** do utilitário: são módulos executados ocasionalmente para executar operações ocasionais ou recorrentes (limpeza, configuração, download de logs de rastreamento etc.).

Os principais processos são:

**Servidor de aplicativos**  (nlserver web)

Esse processo expõe toda a gama de funcionalidades do Adobe Campaign por meio de APIs de serviços da Web (SOAP / HTTP + XML). Além disso, ele pode gerar dinamicamente as páginas da Web usadas para acesso baseado em HTML (relatórios, formulários Web etc.). Para isso, esse processo inclui um servidor JSP Apache Tomcat. Esse é o processo ao qual o Console se conecta.

**Mecanismo de fluxo de trabalho**  (nlserver wfserver)

Ele executa os processos de workflow definidos no aplicativo.

Também lida com workflows técnicos executados periodicamente, incluindo:

* **Rastreamento**: Recuperação e consolidação de logs de rastreamento. Ele permite recuperar os logs do servidor de redirecionamento e criar os indicadores agregados usados pelo módulo de relatórios.
* **Limpeza**: Limpeza do banco de dados. Usado para limpar registros antigos e evitar o crescimento exponencial do banco de dados.
* **Faturamento**: Envio automático de um relatório de atividade para a plataforma (tamanho do banco de dados, número de ações de marketing etc.).

**Servidor de entrega**  (nlserver mta)

A Adobe Campaign tem funcionalidade nativa de transmissão de email. Esse processo funciona como um agente de transferência de email SMTP (MTA). Ele executa a personalização &quot;um para um&quot; de mensagens e manipula sua entrega física. Ele é executado usando tarefas de delivery e lida com tentativas automáticas. Além disso, quando o rastreamento é ativado, ele substitui automaticamente os URLs para que apontem para o servidor de redirecionamento.

Esse processo pode lidar com a personalização e o envio automático para um roteador de terceiros para SMS, fax e mala direta.

**Servidor de redirecionamento**  (nlserver webmdl)

Para email, o Adobe Campaign trata automaticamente o rastreamento de cliques e aberturas (o rastreamento transacional no nível do site é uma outra possibilidade). Para isso, os URLs incorporados nas mensagens de email são reescritos para apontar para esse módulo, que registra a passagem do usuário da Internet antes de redirecioná-los para o URL necessário.

Para garantir a maior disponibilidade, esse processo é totalmente independente do banco de dados: os outros processos de servidor se comunicam com ele usando chamadas SOAP (HTTP, HTTP(S) e XML) somente. Tecnicamente, essa funcionalidade é implementada em um módulo de extensão de um servidor HTTP (extensão ISAPI no IIS, um módulo DSO Apache etc.) e está disponível somente no Windows.

Outros processos mais técnicos também estão disponíveis:

**Gestão de emails de devolução**  (nlserver inMail)

Esse processo permite que você selecione automaticamente emails de caixas de correio configuradas para receber mensagens devolvidas em caso de falha de delivery. Essas mensagens passam por um processamento com base em regras para determinar os motivos para não entrega (recipient desconhecido, cota excedida, etc.) e para atualizar o status do delivery no banco de dados.

Todas essas operações são totalmente automáticas e pré-configuradas.

**Status do delivery de SMS**  (nlserver sms)

Esse processo pesquisa o roteador SMS para coletar o status de progresso e atualizar o banco de dados.

**Gravando mensagens de log**  (nlserver syslogd)

Esse processo técnico captura mensagens de log e rastreamentos gerados pelos outros processos e as grava no disco rígido. Isso disponibiliza amplas informações para diagnóstico em caso de problemas.

**Gravação de logs de rastreamento**  (nlserver trackinglogd)

Esse processo salva em disco os logs de rastreamento gerados pelo processo de redirecionamento.

**Gravação de eventos de entrada**  (nlserver interactiond)

Esse processo garante o registro no disco de eventos de entrada, dentro da estrutura de Interação.

**Supervisão de módulos**  (nlserver watchdog)

Este processo técnico funciona como um processo principal que cria os outros. Ele também os monitora e reinicializa automaticamente em caso de incidentes, mantendo assim o tempo máximo de atividade do sistema.

**Servidor**  de Estatísticas (nlserver stat)

Esse processo mantém estatísticas sobre o número de conexões, as mensagens enviadas para cada servidor de email para o qual as mensagens são enviadas, bem como suas limitações (o maior número de conexões simultâneas, mensagens por hora/e ou conexão). Também permite federar várias instâncias ou máquinas se elas compartilharem os mesmos endereços IP públicos.

## Contêineres de banco de dados {#db-containers}

O banco de dados da Adobe Campaign Cloud depende de [!DNL Snowflake], que contém os dados funcionais (perfis, assinaturas, conteúdo etc.), os dados técnicos (trabalhos e logs de delivery, logs de rastreamento etc.) e os dados de trabalho (compras, clientes em potencial) da solução, e todos os componentes do Adobe Campaign se comunicam com o banco de dados para executar suas tarefas específicas.

Os clientes podem implantar o Adobe Campaign usando o banco de dados e os esquemas predefinidos e, se necessário, esse ambiente predefinido pode ser estendido. Todos os dados no data mart são acessados pela Adobe Campaign através de chamadas SQL. A Adobe Campaign também fornece um complemento completo das ferramentas Extrair transformação e carregamento (ETL) para executar a importação e exportação de dados para dentro e para fora do sistema.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Com o **Campaign Managed Cloud Services**, o ambiente e a configuração inicial foram definidos pela Adobe, de acordo com os termos do contrato de licença. Você não tem permissão para modificar pacotes incorporados instalados, esquemas ou relatórios incorporados.
>
>Se precisar usar um complemento do Campaign ou um recurso específico que não foi fornecido para você, entre em contato com o **Atendimento ao cliente da Adobe**.