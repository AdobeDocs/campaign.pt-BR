---
product: campaign
title: Configurar pesquisas online
description: Saiba como configurar pesquisas online
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 387bc362-4064-4181-9385-8e0c3423ba3e
TQID: 'https://experienceleague.adobe.com/1BTkZ--FyHkp7u0eya-lmuELDu8AMmeC96eGsonYcVM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: 2ac66c0844ec361de9a1658f666c190fcfac8ffa
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 93%
---
# Configurar pesquisas online{#configuring-surveys}

>[!AVAILABILITY]
>
>As pesquisas não estão disponíveis para [implantações do FFDA do Campaign](../../architecture/enterprise-deployment.md).



## Propriedades da pesquisa {#survey-properties}

As pesquisas online são totalmente configuráveis e personalizáveis para atender aos seus requisitos. Os parâmetros devem ser inseridos na janela de propriedades.

Os parâmetros disponíveis são detalhados [neste documento](../web/defining-web-forms-properties.md).

![](assets/s_ncs_admin_survey_properties_general.png)

## Armazenamento de dados de pesquisa {#survey-data-storage}

Por padrão, os campos de formulário web são armazenados na tabela de destinatários. Para usar outra tabela, selecione-a no campo **[!UICONTROL Document type]**. O ícone **[!UICONTROL Zoom]** permite visualizar o conteúdo da tabela selecionada.

Respostas das pesquisas fornecidas por usuários que não são armazenados nos campos (mas em variáveis locais) são armazenadas nas tabelas **Respostas das pesquisas** . É possível alterar o esquema usado com base no campo **[!UICONTROL Library]**. Este campo está disponível somente para **pesquisas**.
