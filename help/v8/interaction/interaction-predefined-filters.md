---
title: Filtros predefinidos da oferta de interação de campanha
description: Saiba como criar filtros predefinidos
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 092262c7-768c-4e86-9b2b-c52516f6a030
TQID: 'https://experienceleague.adobe.com/XWkWbgrMASz-9FfrXC23tTwiw54oQH5U4iWM9fa2FDQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 26%
---
# Criar filtros predefinidos{#creating-pre-defined-filters}

Crie filtros predefinidos para definir regras de qualificação para o público-alvo que podem ser facilmente reutilizados durante a criação da oferta. Eles são específicos para cada ambiente e consideram os parâmetros de oferta.

>[!NOTE]
>
>A interface do usuário da Web do Adobe Campaign oferece uma interface simples para gerenciar e personalizar facilmente filtros predefinidos para atender às suas necessidades específicas. Crie uma vez e salve para uso futuro. Para saber mais sobre os Filtros predefinidos para a interface do usuário da Web, consulte a [documentação da interface do usuário da Web do Adobe Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/predefined-filters){target=_blank}.


Para criar um filtro predefinido, siga o seguinte processo:

1. Navegue até a pasta **[!UICONTROL Administration]** e selecione **[!UICONTROL Pre-defined offer filters]**.

   ![Ofertas - criar árvore com o nó Filtros de oferta predefinidos selecionado em Administração](assets/offer_filter_create_005.png)

1. Clique em **[!UICONTROL New]**.

   ![Lista de filtros de oferta predefinidos com o botão Novo realçado e um filtro de Idade listado](assets/offer_filter_create_001.png)

1. Altere o rótulo para poder identificar o filtro mais tarde.

   ![Caixa de diálogo de filtro de aplicativo com o campo Rótulo definido como Canal de email](assets/offer_filter_create_002.png)

1. Selecione o campo que a condição do filtro abordará.

   ![Selecione uma caixa de diálogo de expressão com o campo Email escolhido nos campos Destinatário](assets/offer_filter_create_003.png)

1. Selecione um operador e um valor se necessário, então salve a consulta.

   ![A condição de filtro na expressão Email com o operador definido como não está vazia](assets/offer_filter_create_004.png)

1. Clique em **[!UICONTROL Preview]** para visualizar o resultado do filtro.

   ![Guia Visualizar do filtro de canal de email listando os destinatários que correspondem ao filtro](assets/offer_filter_create_006.png)
