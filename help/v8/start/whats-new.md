---
title: Novidades do Campaign v8
description: Descubra os principais recursos do Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 30%

---

# Quais são as novidades do Adobe Campaign v8? {#ac-gs-what-is-new}

O Adobe Campaign v8 foi projetado para profissionais de marketing de vários canais que precisam da melhor solução em nuvem do setor para o gerenciamento de campanhas em vários canais com escala corporativa. Ele oferece recursos avançados de ETL e gerenciamento de dados para ajudar a criar e preparar a campanha perfeita. Seu mecanismo de orquestração fornece programas de marketing multitoque avançados com foco principal em jornadas orientadas por lote. Ele também vem junto com um servidor de mensagens em tempo real escalável que permite que as equipes de marketing enviem mensagens predefinidas com base em uma carga abrangente de qualquer sistema de TI para coisas como redefinição de senha, confirmação de pedido, e-receipt&#39;s e muito mais.

O Adobe Campaign v8 oferece aprimoramentos significativos em infraestrutura, segurança, capacidade de entrega e monitoramento.

![](assets/home-page.png)

## Principais recursos{#key-capabilities}

Os principais recursos incluem:

* **Gerenciamento de fluxo de trabalho central**. Melhore a velocidade e a escala de cada aspecto de suas campanhas de marketing, desde a criação de segmentos e a preparação de mensagens até o delivery.

   O Adobe Campaign facilita a sincronização dos canais, com uma interface única e fácil de usar para orquestração de campanhas. Assim, seus canais online — como email, web, celular e social — correspondem aos seus canais offline, incluindo mala direta, call center, na loja e assim por diante. Ele permite que você forneça aos clientes uma experiência consistente e contextual nos canais digitais e tradicionais. O Adobe Campaign facilita o fornecimento de conteúdo para todos os caminhos que seus clientes podem tomar — em qualquer canal.

   ![](../assets/do-not-localize/glass.png) [Saiba mais sobre workflows do Campaign](../config/workflows.md)

* **Marketing personalizado por email**. Crie emails personalizados e relevantes contextualmente que sejam consistentes com o resto da experiência do cliente.

   Com o Adobe Campaign, você pode tornar seus emails melhores, mais personalizados e mais lucrativos. Emails são simples de criar e entregar. O Campaign v8 oferece a flexibilidade de projetar, personalizar, testar, refinar e melhorar todas as mensagens enviadas.

   ![](../assets/do-not-localize/glass.png) [Saiba mais sobre recursos de personalização](create-message.md)

* **Gerenciamento de dados do cliente**. Veja toda a imagem dos clientes para criar campanhas personalizadas rapidamente em escala corporativa.

   O Adobe Campaign ajuda você a criar perfis de clientes a partir de dados coletados em todos os canais. Com esse perfil, você pode orquestrar campanhas em canais. Ao conectar todos os seus canais de marketing, você pode personalizar a jornada diferente que cada cliente fará da maneira que fizer sentido para eles.

   ![](../assets/do-not-localize/glass.png) [Saiba mais sobre o gerenciamento de dados do cliente](audiences.md)

* **Melhor gerenciamento de campanha**. O Adobe Campaign v8 fornece aos profissionais de marketing os melhores recursos do setor para planejar, lançar e medir campanhas em todos os canais.

   Os recursos incluem um perfil integrado que fornece uma visão única do cliente. Gerenciamento e segmentação de dados para a criação de público-alvo de campanha em escala. Gerenciamento de fluxos de trabalho entre canais para automatizar campanhas de multicanal e de várias ondas. E-mail integrado, reduzindo a dependência de ESPs dispendiosos. Relatórios e análises para entender o comportamento do cliente e o desempenho da campanha.

   ![](../assets/do-not-localize/glass.png) [Saiba mais sobre gestão de campanha](campaigns.md)


* **Conexões com o Adobe Experience Platform**. O Adobe Campaign v8 oferece suporte a conectores de dados com a Real-Time CDP e a Adobe Experience Platform, para que as organizações possam aproveitar o Perfil de cliente unificado em tempo real.

   Além disso, o Adobe Campaign v8 é nativamente integrado aos recursos de orquestração de jornadas em tempo real, para que os profissionais de marketing possam reutilizar os mesmos modelos e recursos de entrega no Adobe Campaign para se envolver com os clientes em tempo real. Esses investimentos otimizarão a experiência do cliente do Adobe Campaign e desbloquearão novos casos de uso, como a capacidade de adicionar jornadas do cliente individualizadas em tempo real às campanhas.

   Também é possível configurar a otimização preditiva do tempo de envio e a pontuação preditiva do envolvimento com a IA de jornada, além de aumentar as taxas de abertura, cliques e receitas.

   ![](../assets/do-not-localize/glass.png) [Saiba mais sobre integrações do Campaign](../connect/integration.md)


* **Cloud Services gerenciados**. O Adobe Campaign v8 está disponível como um Cloud Service gerenciado, fornecendo supervisão pró-ativa, alerta em tempo hábil e controle de serviços.

   O Adobe Managed Cloud Service oferece aos profissionais de marketing uma solução de gerenciamento de campanha em vários canais mais ágil, segura e escalável, com baixo custo total de propriedade. A nova oferta combina serviços com supervisão pró-ativa e alerta em tempo hábil.

* **Velocidade e escala**. A Adobe Campaign agora pode aproveitar as tecnologias de banco de dados em escala de nuvem para melhorar consideravelmente sua escala e velocidade.

   [Campanha v8 Enterprise](../architecture/enterprise-deployment.md) traz o conceito de **Acesso completo a dados federados** (FFDA): todos os dados agora são remotos no banco de dados da nuvem. Com essa nova oferta, o Campaign v8 simplifica o gerenciamento de dados: nenhum índice é necessário no banco de dados da nuvem. Basta criar as tabelas, copiar os dados e iniciar. [!DNL Snowflake] é o banco de dados na nuvem do Campaign e trará velocidade e resistência: não há pico de sobrecarga da atividade do sistema. A tecnologia de banco de dados da nuvem não requer manutenção específica para garantir o nível de desempenho.

   ![](../assets/do-not-localize/glass.png) [Saiba mais sobre a implantação do Enterprise (FDA)](../architecture/enterprise-deployment.md)


>[!CAUTION]
>
>* A Campanha v8 é **only** disponível como Cloud Service gerenciado e não pode ser implantado em ambientes locais ou híbridos.
>
>* A migração de um ambiente do Campaign Classic v7 existente ainda não está disponível.




## Interface de administrador do autoatendimento{#self-service-admin}

Como administrador de produto, você pode gerenciar as configurações e rastrear o uso de cada uma das instâncias do Campaign v8 com o **Painel de controle do Campaign**.

Por meio de uma interface intuitiva, os administradores podem monitorar o uso dos principais ativos e realizar tarefas avançadas, como listar permissões de endereços IP, monitorar o armazenamento SFTP, gerenciar chaves e muito mais. Essa interface de autoatendimento oferece mais flexibilidade e ajuda a:

* Fazer alterações rápidas nas configurações por conta própria sem precisar entrar em contato com o Suporte da Adobe
* Defina as configurações de acordo com as diferentes necessidades da sua empresa em momentos diferentes
* Aumente a segurança controlando as configurações de acesso conforme a necessidade

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Saiba mais sobre o Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=pt-BR){target=&quot;_blank&quot;}


