---
product: campaign
title: Configurações de execução
description: Configurações de execução
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: simulating-offers
exl-id: e2dea4a0-9ed8-47b6-a16b-eeee653d2290
TQID: 'https://experienceleague.adobe.com/k2-e-laXDXtVyBJnoiyKAdNHKiS3nB-t1X1cEaqeudM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 75%
---
# Configurações de execução{#execution-settings}



Ao criar uma simulação, é possível especificar as configurações de execução, se necessário. Essas configurações permitem executar a simulação durante um período de pouca atividade, dependendo da prioridade, ou registrar queries SQL no log. Esta etapa é opcional.

Essas configurações podem ser alteradas posteriormente na guia **[!UICONTROL General]** da janela de simulação.

![Guia Geral de uma simulação com configurações de execução: agendamento de baixa atividade, log SQL e lista de Prioridades.](assets/offer_simulation_008.png)

* **[!UICONTROL Schedule execution for a time of low activity]** : permite agendar a simulação com base na prioridade escolhida (baixa, média ou alta) para otimizar o desempenho do Adobe Campaign.
* **[!UICONTROL Priority]**: este é o nível aplicado à simulação para o agendá-la. Quando a opção **[!UICONTROL Schedule execution for a time of low activity]** é marcada, o fluxo de trabalho de processamento de campanha seleciona um momento de baixa atividade para iniciar a campanha.
* **[!UICONTROL Log SQL queries in the journal]**: essa funcionalidade destina-se somente a usuários especializados. Ela permite adicionar uma guia ao log exibindo queries SQL para detectar possíveis defeitos se a simulação terminar com erros.
