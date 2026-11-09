---
product: campaign
title: Exemplo de extensão
description: Exemplo de extensão
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: advanced-parameters
exl-id: d4acf99b-cef4-48f7-b4cd-c032ec12592f
TQID: 'https://experienceleague.adobe.com/TQZaYrJop03HAw47XPFqgmoxb073iC-xztTp-f-5dEk'
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
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
source-git-commit: 936b7519d13ab54d94df9305ef05d4ceb6d6742d
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 100%
---
# Exemplo de extensão{#extension-example}



No caso de um contato de entrada (call center ou site da Web), as ofertas mais relevantes são sugeridas para um determinado contato usando um conjunto de regras de elegibilidade. Para enriquecer os critérios de elegibilidade de suas ofertas, estenda o esquema **nms:interaction**.

* Para adicionar um novo contexto de interação, estenda o esquema **nms:interaction** e crie quantos elementos de **atributo** forem necessários no esquema.

  No exemplo a seguir, os critérios adicionados são o código do país e a última página visitada.

  ![](assets/s_ncs_configuration_offer_schemas.png)

* Em seguida, é possível usar os atributos criados anteriormente ao definir a definição dos critérios de elegibilidade.

  No exemplo a seguir, podemos criar critérios de elegibilidade para exibir uma oferta com base no país do usuário ou na última página da Web que eles visualizaram.

  ![](assets/s_ncs_configuration_offer_context.png)

* Ao configurar chamadas SOAP, insira o elemento XML do **contexto** para fazer referência às informações de contexto adicionadas no esquema de interação. Para obter mais informações, consulte [Integração via SOAP (lado do servidor)](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/offers/inbound/interaction-integration){target="_blank"} (documentação do Campaign v8).
