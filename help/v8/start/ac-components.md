---
title: Entender os processos e componentes do Campaign
description: Entender os processos e componentes do Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: b54a39ee6d106d68446878815c068571e310aaa3
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 1%

---

# Entender os processos e componentes do Campaign {#components-and-processes}

O Adobe Campaign é uma solução de marketing entre canais que automatiza campanhas de email, móveis, sociais e offline. O Adobe Campaign fornece um local central para acessar os dados e perfis de seus clientes. Use o Adobe Campaign para orquestrar experiências consistentes para seus clientes, projetar, executar e personalizar seu marketing em canais, melhorando as experiências dos clientes em cada dispositivo e ponto de contato. Com o Adobe Campaign, você pode gerenciar várias fontes de dados, definir segmentos de público-alvo e planejar e executar campanhas multicanal e entre canais por meio de uma interface visual de fluxo de trabalho de arrastar e soltar.

Saiba mais sobre os principais recursos do Campaign em [esta página](../start/get-started.md).

## Componentes da campanha {#ac-components}

Os componentes do Adobe Campaign e a arquitetura global estão descritos abaixo.

![](assets/ac-components.png)

### Camada de apresentação{#presentation-layer}

Você pode acessar o Adobe Campaign por meio de um cliente avançado, um cliente fino ou integração de API.

* Cliente avançado

   O Campaign Rich client é um aplicativo nativo que se comunica com o servidor de aplicativos do Adobe Campaign, por meio de protocolos padrão de Internet, como SOAP e HTTP.

   O console do Campaign Client centraliza todos os recursos e configurações, e requer largura de banda mínima, pois depende de um cache local. Projetado para fácil implantação, o console do Campaign Client pode ser implantado a partir de um navegador da Internet, atualizado automaticamente e não requer nenhuma configuração de rede específica, pois gera apenas tráfego HTTP(S).

   ![](../assets/do-not-localize/glass.png) [Saiba mais sobre o Console do Cliente do Campaign](../start/connect.md).

* Cliente fino

   Os recursos de acesso à Web do Adobe Campaign permitem acessar um subconjunto de recursos do Campaign com um navegador da Web, usando uma interface de usuário do HTML. Use essa interface da Web para acessar relatórios, controlar e validar mensagens, acessar painéis de monitoramento e muito mais.

   ![](../assets/do-not-localize/glass.png) [Saiba mais sobre o Campaign Web Access](../start/connect.md).

* Aplicativos externos com APIs

   Em certos casos, o sistema pode ser chamado de aplicativos externos usando as APIs de serviços da Web expostas por meio do protocolo SOAP.

   ![](../assets/do-not-localize/glass.png) [Saiba mais sobre APIs do Campaign](../dev/api.md).

### Camada de persistência{#persistance-layer}

Os bancos de dados do Campaign são usados como camadas de persistência e contêm quase todas as informações e dados gerenciados pelo Adobe Campaign. Isso inclui: dados funcionais, como perfis, assinaturas, conteúdo; dados técnicos, como trabalhos de delivery e logs, logs de rastreamento; e dados de trabalho (compras, clientes em potencial).

A confiabilidade do banco de dados é de extrema importância, pois a maioria dos componentes do Adobe Campaign requer acesso ao banco de dados para executar suas tarefas (com exceção do módulo de redirecionamento).

### Camada de aplicativo lógico{#logical-app-layer}

A camada de aplicativo lógico do Campaign é facilmente configurável para atender às necessidades complexas de negócios. Você pode usar o Campaign como uma plataforma única com diferentes aplicativos que se combinam para criar uma arquitetura aberta e escalável. Cada instância do Campaign é uma coleção de processos na camada do aplicativo, alguns dos quais são compartilhados e alguns são dedicados.

## Managed Services do Campaign{#ac-managed-services}

Adobe Campaign v8 é implantado as a Managed Service: todos os componentes do Adobe Campaign, incluindo a interface do usuário, o mecanismo de gerenciamento de execução e os bancos de dados do Campaign são totalmente hospedados pelo Adobe, incluindo execução de email, mirror pages, servidor de rastreamento e componentes da Web voltados para o exterior, como cancelar a assinatura da página/centro de preferências e landing pages.

## Processos de campanha

O servidor Web do Campaign controla o acesso aos processos Web do Campaign. O Javascript é a linguagem do lado do servidor usada para recursos e personalização de produtos principais. O Tomcat é o mecanismo de back-end e está incorporado ao produto do Campaign como parte do processo da Web. O JavaScript é usado, por exemplo, em páginas JSP ou JSSP para renderizar conteúdo dinâmico.

![](assets/ac-processes.png)

O console do Campaign Client se conecta ao servidor da Web usando SOAP XML via HTTP. O servidor da Web fornece a camada de segurança, transmite as solicitações para a camada Aplicativo usando o Javascript e o Campaign interno processa o acesso ao banco de dados usando SQL.

A comunicação geral entre os processos do Campaign é descrita no seguinte diagrama de implantação independente: todos os componentes do Campaign são instalados na mesma máquina.

![](assets/ac-standalone.png)

O usuário se conecta ao servidor de aplicativos do Campaign usando HTTP. Todos os dados e informações são gerenciados no banco de dados do Campaign. Se um desenvolvedor do Campaign executar qualquer alteração de configuração, ele será capturado no banco de dados. Se um profissional de marketing criar uma nova campanha, todas as informações e dados relacionados a essa nova campanha também serão gerenciados no banco de dados. Quando um comerciante executa uma campanha, os deliveries de email são enviados a perfis do servidor do Campaign por meio do servidor SMTP. À medida que os perfis interagem com os deliveries de email, como a abertura do email, esses dados de rastreamento são enviados de volta ao servidor de rastreamento.

![](../assets/do-not-localize/glass.png) [Saiba mais sobre os processos do Campaign](../dev/general-architecture.md#dev-env).
