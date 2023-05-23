---
product: campaign
title: Introdução às tipologias de campanha
description: Saiba como configurar e implementar tipologias de campanha
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 55%

---

# Introdução às tipologias de campanha{#about-campaign-typologies}

**Otimização de Campanha é o módulo do Adobe Campaign que permite controlar, filtrar e monitorar o envio de deliveries.** Para evitar conflitos entre campanhas, o Adobe Campaign pode testar várias combinações aplicando regras de restrição específicas. Isso garante que as mensagens enviadas atendam melhor às necessidades e expectativas dos clientes, de acordo com as políticas de comunicação da empresa.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#typologies-video)

>[!NOTE]
>
>Dependendo da sua oferta, a Otimização de Campanha pode estar incluída ou ser um complemento. Verifique o contrato de licença.

## Regras de tipologia e tipologias {#typology-rules}

Por padrão, o Campaign vem com tipologias e regras de tipologia integradas.

Uma tipologia é um conjunto de regras de verificação aplicadas a todas as mensagens durante a análise da entrega.

Uma tipologia de campanha pode conter várias regras de tipologia, mas uma entrega só pode fazer referência a uma tipologia.

As regras de tipologia e tipologias integradas estão disponíveis no **[!UICONTROL Administration > Campaign management > Typology management]** pasta do explorador do Campaign.

Para cada tipologia, a variável **[!UICONTROL Rules]** permite adicionar, excluir ou exibir as regras de tipologia a serem aplicadas.

![](assets/campaign_opt_rules_tab.png)

Depois de criadas, as regras de tipologia são agrupadas em campanhas **tipologias** que são referenciados nas entregas. [Saiba mais](#apply-typologies).


O Campaign vem com um conjunto de **Filtragem** e **Controle** regras:

* **Filtragem** as regras são usadas para excluir parte do público alvo com base em critérios. [Saiba mais](filtering-rules.md).
* **Controle** as regras permitem verificar a validade das mensagens antes de serem enviadas. [Saiba mais](control-rules.md).

O complemento Otimização de campanha fornece dois tipos adicionais de **regras de tipologia**:

* Regras de **Pressão**, que permitem controlar a fadiga da marca. [Saiba mais](pressure-rules.md).
* Regras de **Capacidade**, que permitem limitar cargas para garantir condições de processamento ideais. [Saiba mais](consistency-rules.md#controlling-capacity).


>[!NOTE]
>
>Se você estiver usando o **Interação** para gerenciar ofertas, você também pode criar **Apresentação da oferta** regras de tipologia para controlar o fluxo de apresentações de oferta usando regras de apresentação. [Saiba mais](../../v8/interaction/interaction-offer.md#offer-presentation).


## Etapas principais para criar e usar tipologias {#apply-typologies}

Para criar e usar uma tipologia para seus deliveries, siga as etapas abaixo:

1. Crie regras de tipologia e crie uma tipologia para referenciá-las nela.
As etapas detalhadas estão listadas na seguinte seção:

   * [Regras de filtro](filtering-rules.md)
   * [Regras de controle](control-rules.md)
   * [Regras de pressão](pressure-rules.md)
   * [Regras de capacidade](consistency-rules.md)

1. Configure seu delivery para usar a tipologia que você criou. [Saiba mais](apply-rules.md#apply-a-typology-to-a-delivery).
1. Teste e controle o comportamento por meio de simulações de campanha. [Saiba mais](campaign-simulations.md).

Durante a preparação do delivery, os recipients são excluídos quando o critério é atingido. Você pode verificar os logs para monitorar exclusões.

Casos de uso de exemplo das regras de tipologia de pressão estão disponíveis [nesta página](pressure-rules.md#use-cases-on-pressure-rules).

## Tutoriais em vídeo {#typologies-video}

### Configurar o gerenciamento de fadiga usando regras de tipologia

Este vídeo explica como implementar o gerenciamento de fadiga no Adobe Campaign utilizando regras de tipologia.

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### Configurar o gerenciamento de fadiga usando filtros predefinidos

O gerenciamento de fadiga controla a frequência e a quantidade de mensagens para evitar a solicitação excessiva de recipients. Se você não tiver o módulo de otimização de campanha na instância da campanha, poderá configurar um filtro predefinido que irá filtrar a população do público-alvo pelo número de mensagens recebidas
Este vídeo ensina a implementar o gerenciamento de fadiga no Adobe Campaign usando filtros.

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)
