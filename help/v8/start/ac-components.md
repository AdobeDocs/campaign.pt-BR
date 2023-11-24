---
title: Entender os componentes e processos do Campaign
description: Entender os componentes e processos do Campaign
feature: Overview, Architecture, Configuration
role: User
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 7deb5e8f646b086adec2e0652538a187e68adbee
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 1%

---

# Entender os componentes e processos do Campaign {#components-and-processes}

O Adobe Campaign é uma solução de marketing entre canais que automatiza campanhas por email, móveis, sociais e offline. A Adobe Campaign fornece um local central para acessar os dados e perfis do cliente. Use o Adobe Campaign para orquestrar experiências consistentes para seus clientes, projetar, executar e personalizar seu marketing entre canais, enquanto melhora as experiências do cliente em cada dispositivo e ponto de contato. Com o Adobe Campaign, você pode gerenciar várias fontes de dados, definir segmentos de público-alvo e planejar e executar campanhas em várias etapas e entre canais por meio de uma interface de fluxo de trabalho visual arrastar e soltar.

Saiba mais sobre os principais recursos do Campaign em [esta página](../start/get-started.md).

## Componentes do Campaign {#ac-components}

Os componentes do Adobe Campaign e a arquitetura global estão descritos abaixo.

![](assets/ac-components.png)

### Camada de apresentação{#presentation-layer}

Você pode acessar o Adobe Campaign por meio de um cliente avançado, um cliente fino ou uma integração de API.

* Cliente avançado

  O Campaign Rich Client é um aplicativo nativo que se comunica com o servidor de aplicativos do Adobe Campaign, por meio de protocolos padrão de Internet, como SOAP e HTTP. [Saiba mais sobre o Console do Cliente do Campaign](../start/connect.md).

* Thin client

  Os recursos de acesso à web do Adobe Campaign permitem acessar um subconjunto de recursos do Campaign com um navegador da web, usando uma interface de usuário HTML. Use essa interface da Web para acessar relatórios, controlar e validar mensagens, acessar painéis de monitoramento e muito mais.  [Saiba mais sobre o Campaign Web Access](../start/connect.md).

* Aplicativos externos com APIs

  Em certos casos, o sistema pode ser chamado de aplicativos externos usando as APIs de serviços da Web expostas por meio do protocolo SOAP. [Saiba mais sobre as APIs do Campaign](../dev/api.md).

### Camada de persistência{#persistance-layer}

Os bancos de dados do Campaign são usados como camadas de persistência e contêm quase todas as informações e dados gerenciados pelo Adobe Campaign. Isso inclui: dados funcionais, como perfis, assinaturas, conteúdo; dados técnicos, como tarefas de entrega e logs, logs de rastreamento; e dados de trabalho (compras, leads).

A confiabilidade do banco de dados é de extrema importância porque a maioria dos componentes do Adobe Campaign requer acesso ao banco de dados para executar suas tarefas (com exceção do módulo de redirecionamento).

### Camada de aplicativo lógica{#logical-app-layer}

A camada de aplicativo lógico do Campaign é facilmente configurável para atender a necessidades complexas dos negócios. Você pode usar o Campaign como uma única plataforma com diferentes aplicativos que se combinam para criar uma arquitetura aberta e escalável. Cada instância do Campaign é uma coleção de processos na camada de aplicativo, alguns dos quais são compartilhados e outros são dedicados.

## Cloud Service gerenciados por campanha{#ac-managed-services}

O Adobe Campaign v8 é implantado de forma as a Managed Service: todos os componentes do Adobe Campaign, incluindo a interface do usuário, o mecanismo de gerenciamento de execução e os bancos de dados do Campaign, são totalmente hospedados pelo Adobe, incluindo execução de email, mirror pages, servidor de rastreamento e componentes da Web voltados para o exterior, como página de cancelamento de inscrição/centro de preferências e páginas de aterrissagem.

## Processos de campanha

O servidor Web do Campaign controla o acesso aos processos da Web do Campaign. Javascript é a linguagem do lado do servidor usada para personalização e recursos de produtos principais. O Tomcat é o mecanismo de back-end e está incorporado ao produto do Campaign como parte do processo da Web. O Javascript é usado, por exemplo, em páginas JSP ou JSSP para renderizar conteúdo dinâmico.

![](assets/ac-processes.png)

O console do cliente do Campaign se conecta ao servidor Web usando XML SOAP por HTTP. O servidor Web fornece a camada de segurança, transmite as solicitações para a camada do Aplicativo usando Javascript e os processos internos do Campaign acessam o banco de dados usando SQL.

A comunicação geral entre os processos do Campaign é descrita no seguinte diagrama de implantação independente: todos os componentes do Campaign são instalados na mesma máquina.

![](assets/ac-standalone.png)

O usuário se conecta ao servidor de aplicativos do Campaign usando o HTTP. Todos os dados e informações são gerenciados no banco de dados do Campaign. Se um desenvolvedor do Campaign executar qualquer alteração de configuração, ela será capturada no banco de dados. Se um profissional de marketing criar uma nova campanha, todas as informações e dados relacionados a essa nova campanha também serão gerenciados no banco de dados. Quando um profissional de marketing executa uma campanha, os deliveries de email são enviados aos perfis do servidor do Campaign por meio do servidor SMTP. Conforme os perfis interagem com deliveries de email, como a abertura do email, esses dados de rastreamento são enviados de volta ao servidor de rastreamento.

![](../assets/do-not-localize/glass.png) [Saiba mais sobre os processos do Campaign](../architecture/general-architecture.md#dev-env).
