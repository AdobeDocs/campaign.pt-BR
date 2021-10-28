---
title: Operadores de interação de campanha
description: Criar operadores de Gerenciamento de ofertas
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
source-git-commit: a02d47f172a2c3021a30834adaeb5170a9801b5c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 53%

---

# Trabalhar com ambientes{#work-with-environments}

## Ambientes Live and Design{#live-design-environments}

O Interaction opera com dois tipos de ambientes de oferta:

* Os ambientes de oferta **[!UICONTROL Design]** que incluem ofertas que estão sendo editadas e podem ser alteradas. Essas ofertas não foram feitas pelo ciclo de aprovação e não são entregues aos contatos.
* Os ambientes de oferta **[!UICONTROL Live]** que incluem ofertas aprovadas conforme são apresentadas aos contatos. As ofertas neste ambiente são somente leitura.

![](assets/offer_environments_overview_001.png)

Cada ambiente **[!UICONTROL Design]** está vinculado a um ambiente **[!UICONTROL Live]**. Quando uma oferta é concluída, suas regras de conteúdo e qualificação estão sujeitas a um ciclo de aprovação. Depois que este ciclo for concluído, a oferta relacionada será implantada automaticamente no ambiente **[!UICONTROL Live]**. A partir deste momento, ele estará disponível para delivery.

Por padrão, o Campaign vem com uma **[!UICONTROL Design]** ambiente e **[!UICONTROL Live]** ambiente vinculado a ele. Ambos os ambientes são pré-configurados para direcionar o [tabela de recipient integrada](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>Para direcionar a tabela de recipients, você precisa usar o assistente de target mapping para criar os ambientes. [Saiba mais](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Os gerentes de delivery só podem visualizar o **[!UICONTROL Live]** ambiente e aproveitar as ofertas para entregá-las. Os gerentes de oferta podem visualizar e usar o **[!UICONTROL Design]** e visualize o **[!UICONTROL Live]** ambiente. [Saiba mais](interaction-operators.md)

## Criar um ambiente para interações anônimas{#create-an-offer-environment}

Por padrão, o Campaign vem com um ambiente integrado para direcionar à tabela de recipients (ofertas identificadas). Para direcionar outra tabela, como perfis anônimos que visitam seu site para interações de entrada, é necessário atualizar sua configuração.

Siga as etapas abaixo:

1. Navegue até **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**, clique com o botão direito do mouse no target mapping que deseja usar e selecione **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. Clique em **[!UICONTROL Next]**, selecione o **[!UICONTROL Generate a storage schema for propositions]** e clique em **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Se a opção já estiver marcada, desmarque-a e depois a marque novamente.

1. O Adobe Campaign cria dois ambientes - **[!UICONTROL Design]** e **[!UICONTROL Live]** - com informações de direcionamento do target mapping habilitado anteriormente. O ambiente é pré-configurado com as informações de definição de metas.

Se ativado o mapeamento **[!UICONTROL Visitor]**, a caixa **[!UICONTROL Environment dedicated to incoming anonymous interactions]** é automaticamente marcada na guia **[!UICONTROL General]** do ambiente.

Essa opção permite ativar funções específicas de interação anônima, especialmente quando configurar espaços de oferta de ambiente. Também é possível configurar opções que permitem alternar de um ambiente &quot;identificado&quot; para um ambiente &quot;anônimo&quot;.

Por exemplo, é possível vincular um espaço de oferta de ambiente de recipient (contato identificado) com um espaço de oferta que corresponda a um ambiente de visitante (contato não identificado). Dessa forma, diferentes ofertas serão disponibilizadas para o contato, dependendo se esse contato for identificado ou não. Para obter mais informações, consulte [Criação de espaços de oferta](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>Para obter mais informações sobre interações anônimas em um canal de entrada, consulte [Interações anônimas](anonymous-interactions.md).
