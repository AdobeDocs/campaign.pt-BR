---
title: Entender os componentes e processos do Campaign
description: Entender os componentes e processos do Campaign
feature: Overview, Architecture, Configuration
role: User
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Entender os componentes e processos do Campaign {#components-and-processes}

O Adobe Campaign é uma solução de marketing entre canais que automatiza campanhas por email, móveis, sociais e offline. A Adobe Campaign fornece um local central para acessar os dados e perfis do cliente. Use o Adobe Campaign para orquestrar experiências consistentes para seus clientes, projetar, executar e personalizar seu marketing entre canais, enquanto melhora as experiências do cliente em cada dispositivo e ponto de contato. Com o Adobe Campaign, você pode gerenciar várias fontes de dados, definir segmentos de público-alvo e planejar e executar campanhas em várias etapas e entre canais por meio de uma interface de fluxo de trabalho visual arrastar e soltar.

Saiba mais sobre os principais recursos do Campaign em [esta página](../start/get-started.md).

## Componentes do Campaign {#ac-components}

Os componentes do Adobe Campaign e a arquitetura global estão descritos abaixo.

![](assets/do-not-localize//ac-components.png)



### Camada de persistência{#persistance-layer}

Os bancos de dados do Campaign são usados como camadas de persistência e contêm quase todas as informações e dados gerenciados pelo Adobe Campaign. Isso inclui: dados funcionais, como perfis, assinaturas, conteúdo; dados técnicos, como tarefas de entrega e logs, logs de rastreamento; e dados de trabalho (compras, leads).

A confiabilidade do banco de dados é de extrema importância porque a maioria dos componentes do Adobe Campaign requer acesso ao banco de dados para executar suas tarefas (com exceção do módulo de redirecionamento).

### Camada de aplicativo lógica{#logical-app-layer}

A camada de aplicativo lógico do Campaign é facilmente configurável para atender a necessidades complexas dos negócios. Você pode usar o Campaign como uma única plataforma com diferentes aplicativos que se combinam para criar uma arquitetura aberta e escalável. Cada instância do Campaign é uma coleção de processos na camada de aplicativo, alguns dos quais são compartilhados e outros são dedicados.

## Cloud Service gerenciados por campanha{#ac-managed-services}

O Adobe Campaign v8 é implantado de forma as a Managed Service: todos os componentes do Adobe Campaign, incluindo a interface do usuário, o mecanismo de gerenciamento de execução e os bancos de dados do Campaign, são totalmente hospedados pelo Adobe, incluindo execução de email, mirror pages, servidor de rastreamento e componentes da Web voltados para o exterior, como página de cancelamento de inscrição/centro de preferências e páginas de aterrissagem.

## Processos de campanha

O servidor Web do Campaign controla o acesso aos processos da Web do Campaign. Javascript é a linguagem do lado do servidor usada para personalização e recursos de produtos principais. O Tomcat é o mecanismo de back-end e está incorporado ao produto do Campaign como parte do processo da Web. O Javascript é usado, por exemplo, em páginas JSP ou JSSP para renderizar conteúdo dinâmico.

![](assets/do-not-localize/ac-processes.png)

O console do cliente do Campaign se conecta ao servidor Web usando XML SOAP por HTTP. O servidor Web fornece a camada de segurança, transmite as solicitações para a camada do Aplicativo usando Javascript e os processos internos do Campaign acessam o banco de dados usando SQL.

A comunicação geral entre os processos do Campaign é descrita no seguinte diagrama de implantação independente: todos os componentes do Campaign são instalados na mesma máquina.

![](assets/do-not-localize//ac-standalone.png)

O usuário se conecta ao servidor de aplicativos do Campaign usando o HTTP. Todos os dados e informações são gerenciados no banco de dados do Campaign. Se um desenvolvedor do Campaign executar qualquer alteração de configuração, ela será capturada no banco de dados. Se um profissional de marketing criar uma nova campanha, todas as informações e dados relacionados a essa nova campanha também serão gerenciados no banco de dados. Quando um profissional de marketing executa uma campanha, os deliveries de email são enviados aos perfis do servidor do Campaign por meio do servidor SMTP. Conforme os perfis interagem com deliveries de email, como a abertura do email, esses dados de rastreamento são enviados de volta ao servidor de rastreamento.

[Saiba mais sobre os processos do Campaign](../architecture/general-architecture.md#dev-env).
