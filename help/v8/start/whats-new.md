---
title: Novidades do Campaign v8
description: Descubra os principais recursos do Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 100%

---

# Quais são as novidades do Adobe Campaign v8? {#ac-gs-what-is-new}

O Adobe Campaign v8 oferece aprimoramentos significativos em infraestrutura, segurança, capacidade de entrega e monitoramento. Utilizando o [[!DNL Snowflake]](https://www.snowflake.com/), uma tecnologia de banco de dados em nuvem, o Adobe Campaign melhora consideravelmente sua escala e velocidade, com a capacidade de gerenciar um número muito maior de perfis de clientes, bem como taxas de entrega e transações por hora muito mais altas.

## Principais recursos{#key-capabilities}

Os principais recursos incluem:

* **Velocidade e escala**. O Adobe Campaign v8 aproveita o Cloud Database Manager, resultando em consultas com desempenho até 200 vezes mais rápido, escala de vários petabytes, maior número de mensagens por hora, com até 20 M/hora ou 1 M/hora para mensagens transacionais, e gerencia até 200 M perfis ativos com potencial para atingir 1 B.

* **Conexões com a Adobe Experience Platform**. O Adobe Campaign v8 oferece suporte a conectores de dados com Adobe Experience Platform/RT-CDP, perfil unificado do cliente e integração nativa com o Journey Orchestration. Esses investimentos otimizarão a experiência do cliente do Adobe Campaign e desbloquearão novos casos de uso, como a capacidade de adicionar jornadas do cliente individualizadas em tempo real às campanhas.

* **Cloud Services gerenciados**. O Adobe Campaign v8 está disponível como o melhor Cloud Services gerenciado do setor, fornecendo supervisão proativa, alerta em tempo hábil e governança de serviços. O valor para o profissional de marketing é o gerenciamento de campanhas entre canais mais ágil e escalável.

>[!CAUTION]
>
>Por enquanto, o Campaign v8 está disponível **apenas** como um serviço na nuvem gerenciado e não pode ser implantado em um ambiente local ou híbrido.
>
>A migração de um ambiente do Campaign Classic v7 existente ainda não está disponível.
>
>Se não tiver certeza do modelo de implantação ou se tiver dúvidas, entre em contato com a equipe de conta.

![](assets/home-page.png)

## Escala{#scale}

O Campaign v8 traz uma escala completa em qualquer etapa do processo, desde o direcionamento até os relatórios finais:

* Dimensione o volume de dados que você pode manipular (até 8 TB)
* Dimensione o desempenho das consultas para segmentação e direcionamento, mas também a assimilação e a saída de dados
* Dimensionar a preparação da entrega (de horas a minutos)

## Interface de administrador do autoatendimento{#self-service-admin}

Como administrador de produto, você pode gerenciar as configurações e rastrear o uso de cada uma das instâncias do Campaign v8 com o **Painel de controle do Campaign**.

Por meio de uma interface intuitiva, os administradores podem monitorar o uso dos principais ativos e realizar tarefas avançadas, como listar permissões de endereços IP, monitorar o armazenamento SFTP, gerenciar chaves e muito mais. Essa interface de autoatendimento oferece mais flexibilidade e ajuda a:

* Fazer alterações rápidas nas configurações por conta própria sem precisar entrar em contato com o Suporte da Adobe
* Defina as configurações de acordo com as diferentes necessidades da sua empresa em momentos diferentes
* Aumente a segurança controlando as configurações de acesso conforme a necessidade

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Saiba mais sobre o Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=pt-BR){target=&quot;_blank&quot;}



## Simplificação e aumento de desempenho{#simplification-and-perf-increase}

O Campaign v8 traz o conceito de **Full Federated Data Access** (FFDA): agora, todos os dados são disponíveis remotamente no banco de dados da nuvem.

Com essa nova arquitetura, o Campaign v8 simplifica o gerenciamento de dados: nenhum índice é necessário no banco de dados da nuvem. Basta criar as tabelas, copiar os dados e iniciar.

[!DNL Snowflake] é o banco de dados na nuvem do Campaign e trará velocidade e resistência: não há pico de sobrecarga da atividade do sistema.

A tecnologia de banco de dados da nuvem não requer manutenção específica para garantir o nível de desempenho.

## ecossistema integrado

É possível integrar o Campaign a um conjunto de soluções avançadas da Adobe, como: Adobe Analytics, Adobe Journey Orchestration, CDP em tempo real, e muito mais.

Também é possível configurar a otimização preditiva do tempo de envio e a pontuação preditiva do envolvimento com a IA de jornada, além de aumentar as taxas de abertura, cliques e receitas.

![](../assets/do-not-localize/glass.png) [Saiba mais sobre integrações do Campaign](../connect/integration.md)

