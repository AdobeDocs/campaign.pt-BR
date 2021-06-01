---
product: Adobe Campaign
title: Operadores de interação de campanha
description: Criar operadores de Gerenciamento de ofertas
feature: Visão geral
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 43%

---

# Ambientes Live and Design{#live-design-environments}

O Interaction opera com dois tipos de ambientes de oferta:

* Os ambientes de oferta **[!UICONTROL Design]** que incluem ofertas que estão sendo editadas e podem ser alteradas. Essas ofertas não foram feitas pelo ciclo de aprovação e não são entregues aos contatos.
* Os ambientes de oferta **[!UICONTROL Live]** que incluem ofertas aprovadas conforme são apresentadas aos contatos. As ofertas neste ambiente são somente leitura.

![](assets/offer_environments_overview_001.png)

Cada ambiente **[!UICONTROL Design]** está vinculado a um ambiente **[!UICONTROL Live]**. Quando uma oferta é concluída, suas regras de conteúdo e qualificação estão sujeitas a um ciclo de aprovação. Depois que este ciclo for concluído, a oferta relacionada será implantada automaticamente no ambiente **[!UICONTROL Live]**. A partir deste momento, ele estará disponível para delivery.

Por padrão, o Campaign vem com um ambiente **[!UICONTROL Design]** e um ambiente **[!UICONTROL Live]** vinculado a ele. Ambos os ambientes são pré-configurados para direcionar a [tabela de recipient incorporada](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>Para direcionar a tabela de recipients, você precisa usar o assistente de target mapping para criar os ambientes. [Saiba mais](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Os gerentes de delivery só podem visualizar o ambiente **[!UICONTROL Live]** e aproveitar as ofertas para entregá-las. Os gerentes de oferta podem visualizar e usar o ambiente **[!UICONTROL Design]** e visualizar o ambiente **[!UICONTROL Live]**. [Saiba mais](interaction-operators.md).

## Criar um ambiente de oferta {#creating-an-offer-environment}

Por padrão, o Campaign vem com um ambiente integrado para direcionar à tabela de recipients (ofertas identificadas). Para direcionar outra tabela, siga as etapas abaixo:

1. Navegue até **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**, clique com o botão direito do mouse no target mapping que deseja usar e selecione **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. Clique em **[!UICONTROL Next]**, selecione a opção **[!UICONTROL Generate a storage schema for propositions]** e clique em **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Se a opção já estiver marcada, desmarque-a e depois a marque novamente.

1. O Adobe Campaign cria dois ambientes - **[!UICONTROL Design]** e **[!UICONTROL Live]** - com informações de direcionamento do target mapping habilitado anteriormente. O ambiente é pré-configurado com as informações de definição de metas.
