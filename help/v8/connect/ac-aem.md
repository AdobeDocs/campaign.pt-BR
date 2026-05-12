---
title: Trabalhar com o Campaign e o Adobe Experience Manager
description: Saiba como trabalhar com o Campaign e o Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
TQID: https://experienceleague.adobe.com/LM635Kjl7bucy1SMcEPuhCElUI7MNrO4B3fwo9fpyFQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: d5ef99fa-df0c-4153-bf94-105ad0724167
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 651
ht-degree: 19%

---

# Trabalhar com o Campaign e o Adobe Experience Manager {#ac-aem}

A integração entre o Adobe Campaign e o Adobe Experience Manager (AEM) permite gerenciar o conteúdo das entregas de email, bem como seus formulários diretamente no Adobe Experience Manager.

[Saiba como editar o conteúdo do Adobe Experience Manager as Cloud Service na Interface da Web do Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-content.html){target="_blank"}.

[Saiba mais sobre o Adobe Experience Manager neste documento](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html#aem-and-adobe-campaign-integration-workflow){target="_blank"}.


>[!NOTE]
>
>Como usuário do Managed Cloud Services, [contate a Adobe](../start/campaign-faq.md#support) para integrar o Adobe Experience Manager ao Campaign.

## Importar conteúdo do Adobe Experience Manager {#integrating-with-aem}

Essa integração pode ser usada para criar um boletim informativo no Adobe Experience Manager que será usado no Adobe Campaign como parte de uma campanha de email.

**No Adobe Experience Manager:**

1. Navegue até a instância do autor [!DNL Adobe Experience Manager] e clique em Adobe Experience no canto superior esquerdo da página. Escolha **[!UICONTROL Sites]** no menu.

   ![](assets/aem_authoring_1.png)

1. Acessar **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. Clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Page]** no menu suspenso.

   ![](assets/aem_authoring_2.png)

1. Selecione o modelo **[!UICONTROL Adobe Campaign Email]** e nomeie o informativo.

1. Depois de criar sua página, acesse o menu **[!UICONTROL Page information]** e clique em **[!UICONTROL Open Properties]**.

   ![](assets/aem_authoring_3.png)

1. Personalize seu conteúdo de email adicionando componentes, como campos de personalização do Adobe Campaign. Saiba mais em [documentação do Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html#editing-email-content){target="_blank"}.

1. Quando o email estiver pronto, navegue até o menu **[!UICONTROL Page information]** e clique em **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_4.png)

1. Na primeira lista suspensa, selecione **[!UICONTROL Approve Adobe Campaign]** como modelo de fluxo de trabalho e clique em **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_5.png)

1. Um aviso de isenção de responsabilidade será exibido na parte superior da página informando, `This page is subject to the workflow Approve for Adobe Campaign`. Clique em **[!UICONTROL Complete]** ao lado do aviso de isenção de responsabilidade para confirmar a revisão e clique em **[!UICONTROL Ok]**.

1. Clique novamente em **[!UICONTROL Complete]** e selecione **[!UICONTROL Newsletter approval]** no menu suspenso **[!UICONTROL Next Step]**.

   ![](assets/aem_authoring_6.png)

Seu boletim informativo agora está pronto e sincronizado no Adobe Campaign.

**No Adobe Campaign:**

1. Na guia **[!UICONTROL Campaigns]**, clique em **[!UICONTROL Deliveries]** e em **[!UICONTROL Create]**.

1. Escolha o modelo **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** no menu suspenso **[!UICONTROL Delivery template]**.

   ![](assets/aem_authoring_7.png)

1. Adicione um **[!UICONTROL Label]** à entrega e clique em **[!UICONTROL Continue]**.

1. Clique em **[!UICONTROL Synchronize]** para acessar suas entregas do AEM.

   Se o botão não estiver visível na interface, navegue até o botão **[!UICONTROL Properties]** e acesse a guia **[!UICONTROL Advanced]**. Verifique se o campo **[!UICONTROL Content editing mode]** está configurado para **[!UICONTROL AEM]** e insira os detalhes da instância do AEM no campo **[!UICONTROL AEM account]**.

   ![](assets/aem_authoring_8.png)

1. Selecione a entrega do AEM criada anteriormente em [!DNL Adobe Experience Manager] e confirme clicando em **[!UICONTROL Ok]**.

   ![](assets/aem_authoring_11.png)

1. Certifique-se de clicar no botão **[!UICONTROL Refresh content]** sempre que forem feitas modificações na entrega do AEM.

   ![](assets/aem_authoring_12.png)

1. Para remover a vinculação entre o Experience Manager e o Campaign, clique em **[!UICONTROL Desynchronize]**.

O email agora está pronto para ser enviado ao seu público-alvo.

## Importar ativos da biblioteca do Adobe Experience Manager Assets {#assets-library}

Você também pode inserir ativos diretamente do [!DNL Adobe Experience Manager Assets Library] ao editar um email ou uma página de aterrissagem no Adobe Campaign. Esta funcionalidade é detalhada na [documentação do Adobe Experience Manager Assets](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html){target="_blank"}.

**No Adobe Experience Manager:**

1. Navegue até a instância do autor [!DNL Adobe Experience Manager] e clique em Adobe Experience no canto superior esquerdo da página. Escolha **[!UICONTROL Assets]** `>` **[!UICONTROL Files]** no menu.

   ![](assets/aem_assets_1.png)

1. Clique em **Criar** e depois em **Arquivos** para importar seu ativo para a **Biblioteca da Adobe Experience Manager Assets**. Saiba mais em [documentação do Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html#uploading-assets){target="_blank"}.

   ![](assets/aem_assets_2.png)

1. Renomeie o ativo, se necessário, e selecione **Carregar**.

Seu ativo foi carregado para sua **Biblioteca da Adobe Experience Manager Assets**.

**No Adobe Campaign:**

1. No Adobe Campaign, crie uma nova entrega navegando até a guia **Campanhas**, clique em **Entregas** e no botão **Criar** acima da lista de entregas existentes.

   ![](assets/aem_assets_3.png)

1. Selecione um **Modelo de entrega** e nomeie a entrega.

1. Defina e personalize o conteúdo da mensagem. [Saiba mais](../send/email.md)

1. Para usar sua **biblioteca Adobe Experience Manager Assets**, acesse o **[!UICONTROL Properties]** da entrega do AEM e selecione a guia **[!UICONTROL Advanced]**.

   Escolha sua **conta do AEM** e habilite a opção **[!UICONTROL Use above AEM instance as shared asset library]**.

   ![](assets/aem_authoring_9.png)

1. No ícone **Imagem**, acesse o menu **[!UICONTROL Select a shared asset]**.

   ![](assets/aem_assets_4.png)

1. Na janela de seleção, selecione uma imagem da sua **biblioteca Adobe Experience Manager Assets** e **Selecione**.

   ![](assets/aem_assets_5.png)

Seu ativo agora é carregado para o delivery de email. Agora você pode especificar o público-alvo, confirmar o delivery e continuar com o envio.
