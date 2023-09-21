---
title: Migrar a infraestrutura de envio do Campaign para o Amazon Web Services (AWS)
description: Migrar a infraestrutura de envio do Campaign para o Amazon Web Services (AWS)
hide: true
hidefromtoc: true
source-git-commit: 9401e3564b53b920dd6a640ca6d00531992a2f21
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 6%

---


# Campanha de migração de infraestrutura de envio para o Amazon Web Services (AWS) {#migrate-infra-to-aws}

## O que mudou?{#aws-changes}

Como parte de nosso esforço contínuo para fornecer o serviço de delivery de email de mais alta qualidade, a infraestrutura de envio de email do Campaign está sendo transferida de data centers hospedados no Adobe para o Amazon Web Services (AWS).

Essa mudança garantirá alta disponibilidade, throughput ideal e capacidade de expansão para atender às necessidades de nossos clientes.

## Você será afetado?{#aws-impact}

Essa alteração afeta:

* Clientes hospedados e híbridos do Campaign Classic v7
* Clientes do Campaign Managed Services
* Todos os clientes do Campaign v8
* clientes do Campaign Standard

## Quando ocorrerá essa migração?{#aws-timeline}

A migração de ambientes de desenvolvimento e de preparo ocorrerá em **Outubro de 2023**.

A migração de ambientes de produção está programada para começar em **Janeiro de 2024**. Mais detalhes serão fornecidos à medida que a data se aproximar.

Como cliente do Campaign, você receberá uma notificação adicional, pois as ondas de migração estão programadas. As notificações serão enviadas pelo menos 7 dias antes da migração para ambientes de preparo e pelo menos 30 dias antes da migração para ambientes de produção.

## Qual é o impacto?{#impact}

Essa mudança será transparente para os clientes:

* A duração de cada onda de migração pode variar dependendo do número de instâncias do Campaign afetadas. Quando uma onda de migração é programada, a notificação incluirá a duração esperada.

* As instâncias do Campaign não poderão enviar emails durante a janela de migração. Nenhuma outra função do Campaign será afetada.


## Perguntas frequentes {#aws-faq}

* **Por que esta é uma atualização obrigatória?**

  O Adobe planeja desativar o data center herdado, as instâncias do Adobe Campaign em execução devem ser transferidas para o novo data center de referência, o Amazon Web Services (AWS).

  A nuvem do Adobe Managed Services é hospedada no Amazon Web Services (AWS), um ambiente moderno, seguro e otimizado. [Saiba mais sobre o Amazon Web Services](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}.

* **Quais clientes são direcionados para essa migração?**

  Todos os clientes do Campaign v8 e o Campaign Classic v7 híbrido, hospedado e o Campaign Managed Services terão seus ambientes migrados. Os clientes do Campaign Standard também são afetados.

* **Qual é o tempo de inatividade esperado?**

  A migração deve levar entre 30 min e 60 min, mas a duração de cada onda de migração pode variar dependendo do número de instâncias do Campaign afetadas. Quando uma onda de migração é programada, a notificação incluirá a duração esperada.

* **O cliente precisa realizar alguma ação para a migração?**

  Nenhuma ação é necessária, pois a migração será executada automaticamente pelo Adobe.

* **Quais validações precisam ser executadas pelos clientes?**

  Nenhum teste específico é necessário para essa migração. Caso algum problema seja observado, entre em contato com [Atendimento ao cliente Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **Posso solicitar uma alteração na Data/Hora para o slot de atualização de segurança programado?**

  Como essa é uma migração obrigatória, não podemos acomodar modificações na programação existente.

Para qualquer outra pergunta, entre em contato com o [Atendimento ao cliente da Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
