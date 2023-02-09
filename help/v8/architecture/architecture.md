---
title: Introdução à arquitetura do Campaign
description: Descubra ambientes e noções básicas de implantação, incluindo como criar relatórios sobre um ambiente de campanha.
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 507f30d16eecf5400ee88a4d29913e4cdaca9cba
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 17%

---

# Introdução à arquitetura do Campaign{#gs-ac-archi}

## Ambientes {#environments}

A campanha é disponibilizada como instâncias individuais, com cada instância representando um ambiente completo do Campaign.

Dois tipos de ambientes estão disponíveis:

* **Ambiente de produção**: hospeda os aplicativos para os profissionais de negócios.

* **Ambiente não relacionado à produção**: usado para vários testes de desempenho e qualidade antes que as alterações no aplicativo sejam enviadas para o ambiente de produção.

É possível exportar e importar pacotes de um ambiente para outro.

![](../assets/do-not-localize/book.png) Saiba mais sobre pacotes em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target="_blank"}

## Modelos de implantação{#ac-deployment}

Dois modelos de implantação estão disponíveis:

* **FDA da campanha [!DNL Snowflake] implantação**

   Na [[!DNL Snowflake] Implantação FDA](fda-deployment.md), [!DNL Adobe Campaign] v8 está conectado a [!DNL Snowflake] para acessar dados por meio do recurso Federated Data Access: você pode acessar e processar dados externos e informações armazenadas em [!DNL Snowflake] banco de dados sem alterar a estrutura dos dados do Adobe Campaign. O PostgreSQL é o banco de dados principal e o Snowflake é o banco de dados secundário. Você pode estender seu modelo de dados e armazenar seus dados no Snowflake. Posteriormente, é possível executar ETL, segmentação e relatórios em um grande conjunto de dados com desempenho excepcional.

* **Implantação do Campaign Enterprise (FDA)**

   No contexto de um [Implantação empresarial (FDA)](enterprise-deployment.md), [!DNL Adobe Campaign] O v8 funciona com dois bancos de dados: um local [!DNL Campaign] banco de dados para a interface do usuário, mensagens em tempo real e consultas unitárias e gravação por meio de APIs, e uma nuvem [!DNL Snowflake] banco de dados para execução da campanha, consultas em lote e execução do workflow.

   O Campaign v8 Enterprise traz o conceito de **Full Federated Data Access** (FFDA): agora, todos os dados estão disponíveis remotamente no banco de dados da nuvem. Com essa nova arquitetura, a implantação corporativa (FFDA) do Campaign v8 simplifica o gerenciamento de dados: nenhum índice é necessário no banco de dados da nuvem. Basta criar as tabelas, copiar os dados e iniciar. A tecnologia de banco de dados da nuvem não requer manutenção específica para garantir o nível de desempenho.


## Arquitetura do Centro de mensagens{#transac-msg-archi}

O envio de mensagens transacionais (Centro de mensagens) é o módulo do Campaign criado para gerenciar mensagens de acionador.

![](../assets/do-not-localize/glass.png) Saiba como enviar mensagens transacionais em [esta seção](../send/transactional.md).

Em resposta a uma ação de um cliente em um site, um evento é enviado ao Campaign por meio de uma API REST e o modelo de mensagem é preenchido com as informações ou os dados fornecidos por meio da chamada da API, e uma mensagem transacional é enviada em tempo real ao cliente. Essas mensagens podem ser enviadas individualmente ou em lotes por email, SMS ou notificações por push.

Nesta arquitetura específica, a célula de execução é separada da instância de controle para garantir alta disponibilidade e gerenciamento de carga.

* O **Instância de controle** (ou Instância de marketing) é usada por profissionais de marketing e equipes de TI para criar, configurar e publicar modelos de mensagem. Essa instância também centraliza o monitoramento e o histórico do evento.

   ![](../assets/do-not-localize/glass.png) Saiba como criar e publicar modelos de mensagem em [esta seção](../send/transactional.md).

* O **Instância de execução** recupera eventos recebidos (redefinição de senha ou pedidos de um site, por exemplo) e envia mensagens personalizadas. Pode haver mais de uma instância de execução para processar mensagens por meio do balanceador de carga e dimensionar o número de eventos a serem processados para proporcionar disponibilidade máxima.

>[!CAUTION]
>
>A instância de controle e a instância de execução devem ser instaladas em máquinas diferentes. Elas não podem compartilhar a mesma instância do Campaign.

![](assets/messagecenter_diagram.png)

### Autenticação

Para usar esses recursos, os usuários do Adobe Campaign fazem logon na instância de controle para criar templates de mensagem transacional, gerar a pré-visualização da mensagem usando uma lista de propagação, exibir relatórios e monitorar as instâncias de execução.

* Instância de execução única Ao interagir com uma instância de execução do Centro de mensagens hospedada pelo Adobe, um sistema externo pode primeiro recuperar um token de sessão (que por padrão expira em 24 horas), fazendo uma chamada de api para o método de logon da sessão, usando um login de conta e uma senha fornecidos.
Em seguida, com o sessionToken fornecido pela instância de execução em resposta à chamada acima, o aplicativo externo pode fazer invocações de api SOAP (rtEvents ou batchEvents) para enviar comunicações, sem a necessidade de incluir em cada chamada SOAP o logon da conta e a senha.

* Várias instâncias de execução Em uma arquitetura de execução de várias células com várias instâncias de execução atrás de um balanceador de carga, o método de logon chamado pelo aplicativo externo está passando pelo balanceador de carga: por esse motivo, não é possível usar uma autenticação baseada em token. É necessária uma autenticação baseada em usuário/senha.

![](../assets/do-not-localize/book.png) Saiba mais sobre eventos de mensagens transacionais em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel){target="_blank"}
