---
title: Trabalhar com o Campaign e seu CRM
description: Saiba como trabalhar com o Campaign e seu CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
version: Campaign v8, Campaign Classic v7
TQID: 'https://experienceleague.adobe.com/gYGdySWZC1j2VkvAkL9rVBes7iQvRkRjNjm-dvFsHBM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: f09afca2-2160-4624-bedb-639c4f4c236f
    internal-label: Salesforce integration
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
    internal-label: Email marketing
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 35%
---
# Conectar seu CRM ao Campaign {#gs-crm}

O Adobe Campaign fornece vários conectores de CRM para vincular sua plataforma a sistemas de terceiros. Esses conectores de CRM permitem sincronizar contatos, contas, compras, etc. Eles facilitam a integração de seu aplicativo com vários aplicativos de terceiros e corporativos.

Esses conectores permitem uma integração de dados rápida e fácil: o Adobe Campaign fornece um assistente dedicado para coletar e selecionar entre as tabelas disponíveis no CRM. Isso garante a sincronização bidirecional para assegurar que os dados estejam sempre atualizados em todos os sistemas.

Os principais benefícios são:

* Mensagens consistentes entre vendas e marketing: a integração do Adobe Campaign com seu CRM fornece aos dois sistemas acesso ao insight do cliente e ao histórico de marketing por email, permitindo que todas as mensagens para o cliente compartilhem a mesma mensagem consistente.

* Visualização integral de todos os dados de clientes potenciais e de clientes: ao integrar o Adobe Campaign ao seu CRM, é possível compartilhar e acessar o histórico de marketing por email em cada contato de dentro do sistema de CRM.

* Ativar os dados do CRM em qualquer canal: com dados de contato sincronizados com o Adobe Campaign, as comunicações podem ser enviadas em qualquer canal online ou offline com o Campaign, incluindo push móvel, no aplicativo, email ou correspondência direta.


>[!NOTE]
>
>Esse recurso está disponível no Adobe Campaign através dos **conectores dedicados do CRM**.

## Sistemas compatíveis {#compatible-crm-systems-and-limitations}

O CRM e as versões compatíveis estão detalhados na [Matriz de compatibilidade](../start/compatibility-matrix.md) do Campaign.

>[!CAUTION]
>
> Os conectores CRM do Campaign funcionam somente com um URL seguro (https).

## Etapas de implementação {#crm-implementation-steps}

Saiba mais sobre o procedimento passo a passo para conectar o Campaign e o Microsoft Dynamics nesta [página](ac-ms-dyn.md).

Saiba mais sobre o procedimento passo a passo para conectar Campaign e Salesforce.com nesta [página](ac-sfdc.md).

A sincronização de dados entre o Adobe Campaign e o CRM é realizada por meio de uma atividade dedicada de fluxo de trabalho. Crie seus workflows para automatizar a sincronização entre o Campaign e o CRM. Você pode criar um workflow que importa contatos por meio do Microsoft Dynamics, sincroniza com os dados existentes do Adobe Campaign, exclui os contatos duplicados e atualiza o banco de dados do Adobe Campaign. Saiba mais [nesta página](crm-data-sync.md).
