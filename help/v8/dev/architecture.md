---
solution: Campaign v8
product: Adobe Campaign
title: Introdução à arquitetura do Campaign
description: Introdução à arquitetura do Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 6%

---

# Introdução à arquitetura do Campaign{#gs-ac-archi}

## Ambientes

A campanha é disponibilizada como instâncias individuais, com cada instância representando um ambiente completo do Campaign.

Três tipos de ambientes disponíveis com o Campaign Cloud Service:

* **Ambiente** de produção: hospeda os aplicativos para os profissionais de negócios.

* **Ambiente** de preparo: usado para vários testes de desempenho e qualidade antes que as alterações no aplicativo sejam enviadas para o ambiente de produção.

* **Ambiente** de desenvolvimento: O permite que os desenvolvedores implementem o Campaign nas mesmas condições de tempo de execução que os ambientes stage e production.

É possível exportar e importar pacotes de um ambiente para outro.

:[!DNL :arrow_upper_right:]: Saiba mais sobre pacotes na documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## Implantação Mid-sourcing{#mid-sourcing-deployment}

A comunicação geral entre servidores e processos é realizada de acordo com o seguinte schema:

![](assets/architecture.png)

* Os módulos de gerenciamento de execução e rejeição estão desabilitados na instância.

* O aplicativo é configurado para executar a execução de mensagens em um servidor remoto &quot;mid-sourcing&quot;, que é orientado por chamadas SOAP (via HTTP ou HTTPS).

>[!NOTE]
>
> O Campaign v8 depende de uma arquitetura híbrida. Se estiver fazendo a transição do Campaign Classic v7, observe que todos os deliveries passam pelo servidor mid-sourcing.
> Como consequência, o roteamento interno é **not possible** no Campaign v8 e a conta externa foi desabilitada adequadamente.

## Arquitetura do Centro de Mensagens{#transac-msg-archi}

As mensagens transacionais (Centro de Mensagens) são o módulo do Campaign criado para gerenciar mensagens por disparo.

[!DNL :bulb:] Saiba como enviar mensagens transacionais  [nesta seção](../send/transactional.md).

Em resposta a uma ação de um cliente em um site, um evento é enviado ao Campaign por meio de uma API REST e o modelo de mensagem é preenchido com as informações ou os dados fornecidos por meio da chamada da API, e uma mensagem transacional é enviada em tempo real ao cliente. Essas mensagens podem ser enviadas individualmente ou em batches por email, SMS ou notificações por push.

Nesta arquitetura específica, a célula de execução é separada da instância de controle para garantir alta disponibilidade e gerenciamento de carga.

* O **Control instance** (ou Marketing instance) é usado por profissionais de marketing e equipes de TI para criar, configurar e publicar templates de mensagem. Essa instância também centraliza o monitoramento e o histórico do evento.

   [!DNL :bulb:] Saiba como criar e publicar modelos de mensagem  [nesta seção](../send/transactional.md).

* O **Execution instance** recupera eventos recebidos (redefinição de senha ou pedidos de um site, por exemplo) e envia mensagens personalizadas. Pode haver mais de uma instância de execução para processar mensagens por meio do balanceador de carga e dimensionar o número de eventos a serem processados para proporcionar disponibilidade máxima.

>[!CAUTION]
>
>A instância de controle e a instância de execução devem ser instaladas em máquinas diferentes. Elas não podem compartilhar a mesma instância do Campaign.

![](assets/messagecenter_diagram.png)

:[!DNL :arrow_upper_right:]: A arquitetura do Centro de mensagens é descrita na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=en#transactional-messaging)

### Autenticação

Para usar esses recursos, os usuários do Adobe Campaign fazem logon na instância de controle para criar templates de mensagem transacional, gerar a pré-visualização da mensagem usando uma lista de propagação, exibir relatórios e monitorar as instâncias de execução.

* Instância de execução única
Ao interagir com uma instância de execução do Centro de Mensagens hospedada pelo Adobe, um sistema externo pode primeiro recuperar um token de sessão (que por padrão expira em 24 horas), fazendo uma chamada de api para o método de logon da sessão, usando um login de conta e uma senha fornecidos.
Em seguida, com o sessionToken fornecido pela instância de execução em resposta à chamada acima, o aplicativo externo pode fazer invocações de api SOAP (rtEvents ou batchEvents) para enviar comunicações, sem a necessidade de incluir em cada chamada SOAP o logon da conta e a senha.

* Várias instâncias de execução
Em uma arquitetura de execução de várias células com várias instâncias de execução atrás de um balanceador de carga, o método logon chamado pelo aplicativo externo está passando pelo balanceador de carga: por esse motivo, não é possível usar uma autenticação baseada em token. É necessária uma autenticação baseada em usuário/senha.

:[!DNL :arrow_upper_right:]: Saiba mais sobre eventos de mensagens transacionais na documentação do [Campaign Classic v7](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)