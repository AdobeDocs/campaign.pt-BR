---
title: Introdução à arquitetura do Campaign
description: Descubra ambientes e noções básicas de implantação, incluindo como criar relatórios sobre um ambiente de campanha.
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 618e45b6948070c6b791d2bcefa8296b297bf25e
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 13%

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

## Split delivery execution {#split}

>[!AVAILABILITY]
>
>Esse recurso está disponível somente para clientes com configurações de várias instâncias da MID.

Dependendo do seu pacote do Campaign v8, você é provisionado com um número específico de instâncias de mid-sourcing responsáveis pela execução de deliveries.

Por padrão, as contas externas de todos os canais usam um **[!UICONTROL Alternate]** modo de roteamento, o que significa que um delivery é enviado de cada instância mid de cada vez de forma alternada.

Para garantir melhor desempenho em termos de velocidade e escala, você pode permitir que os deliveries sejam divididos automaticamente em suas instâncias de mid-sourcing para serem entregues mais rapidamente aos recipients. Essa operação é transparente ao executar o delivery a partir da instância de marketing: depois que o delivery for enviado, todos os logs serão consolidados, antes de serem enviados de volta à instância de marketing em um único objeto de delivery.

Para fazer isso, contas externas adicionais com a variável **[!UICONTROL Split]** os modos de roteamento são criados no provisionamento de cada canal:

* Entrega dividida - Email (splitDeliveryEmail)
* Entrega dividida - SMS (splitDeliverySMS)
* Entrega dividida - iOS (splitDeliveryIOS)
* Entrega dividida - Android (splitDeliveryAndroid)

![](assets/splitted-delivery.png)

>[!IMPORTANT]
>
>O modo de roteamento dividido é ativado por padrão para a conta &quot;Split Delivery - Email&quot;. Para todos os outros canais de contas externas, entre em contato com o Atendimento ao cliente para ativar a opção .
>
>Por padrão, o valor do tamanho limite para dividir um delivery entre várias mids é de 100 mil. Você pode alterar esse valor na opção &quot;NmsDelivery_MultiMidSplitThreshold&quot; na **[!UICONTROL Administration]** / **[!UICONTROL Platform]** / **[!UICONTROL Options]** menu.

Para fazer contas externas divididas como a conta padrão para enviar deliveries, é necessário alterar o provedor de roteamento nos templates do delivery. Para fazer isso, siga estes passos:

1. Navegue até o **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Delivery templates]** e abra o template do delivery desejado. Neste exemplo, queremos editar o template do delivery de email.

   ![](assets/split-default-list.png)

1. Clique no botão **[!UICONTROL Properties]** e altere o provedor de roteamento para a conta externa de delivery dividida correspondente.

   ![](assets/split-default-delivery.png)

1. Salve as alterações. Todos os deliveries enviados usando o template agora usarão o modo de roteamento dividido por padrão.

<!--In addition, you can select split external accounts as the default routing provider for all future delivery templates. To do this, change the value of the **[!UICONTROL xtkoption NmsBroadcast_DefaultProvider]** option to the name of the split account.

![](assets/split-default-options.png) -->

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
