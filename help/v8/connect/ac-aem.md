---
title: Trabalhar com o Campaign e o Adobe Experience Manager
description: Saiba como trabalhar com o Campaign e o Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 15%

---

# Trabalhar com o Campaign e o Adobe Experience Manager {#ac-aem}

A integração entre o Adobe Campaign e o Adobe Experience Manager permite gerenciar o conteúdo dos deliveries de email, bem como seus formulários diretamente no Adobe Experience Manager. Você tem a opção de importar seu **Adobe Experience Manager** conteúdo no Campaign ou conecte seu **Adobe Experience Manager as a Cloud Service** conta, permitindo editar o conteúdo diretamente na interface da Web.

[Saiba como editar o conteúdo do Adobe Experience Manager as Cloud Service na interface da Web do Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-content.html){target="_blank"}.

[Saiba mais sobre o Adobe Experience Manager neste documento](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html#aem-and-adobe-campaign-integration-workflow){target="_blank"}.


>[!NOTE]
>
>Como usuário do Managed Cloud Service, [Adobe de contato](../start/campaign-faq.md#support) para integrar o Adobe Experience Manager ao Campaign.

## Importar conteúdo do Adobe Experience Manager {#integrating-with-aem}

Essa integração pode ser usada para criar um boletim informativo no Adobe Experience Manager que será usado no Adobe Campaign como parte de uma campanha de email.

**No Adobe Experience Manager:**

1. Navegue até o [!DNL Adobe Experience Manager] instância do autor e clique em Experiência Adobe no canto superior esquerdo da página. Escolher **[!UICONTROL Sites]** no menu.

   ![](assets/aem_authoring_1.png)

1. Access **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. Clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Page]** no menu suspenso.

   ![](assets/aem_authoring_2.png)

1. Selecione o modelo **[!UICONTROL Adobe Campaign Email]** e nomeie o informativo.

1. Depois de criar a página, acesse o **[!UICONTROL Page information]** e clique em **[!UICONTROL Open Properties]**.

   ![](assets/aem_authoring_3.png)

1. Personalize seu conteúdo de email adicionando componentes, como campos de personalização do Adobe Campaign. Saiba mais em [Documentação do Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html#editing-email-content){target="_blank"}.

1. Quando o email estiver pronto, navegue até o **[!UICONTROL Page information]** e clique em **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_4.png)

1. Na primeira lista suspensa, selecione **[!UICONTROL Approve Adobe Campaign]** como modelo de workflow e clique em **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_5.png)

1. Um aviso de isenção de responsabilidade será exibido na parte superior da página informando: `This page is subject to the workflow Approve for Adobe Campaign`. Clique em **[!UICONTROL Complete]** ao lado do aviso para confirmar a revisão e clique em **[!UICONTROL Ok]**.

1. Clique em **[!UICONTROL Complete]** novamente e selecione **[!UICONTROL Newsletter approval]** no **[!UICONTROL Next Step]** menu suspenso.

   ![](assets/aem_authoring_6.png)

Seu boletim informativo agora está pronto e sincronizado no Adobe Campaign.

**No Adobe Campaign:**

1. Na guia **[!UICONTROL Campaigns]**, clique em **[!UICONTROL Deliveries]** e em **[!UICONTROL Create]**.

1. Escolha o **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** modelo do **[!UICONTROL Delivery template]** menu suspenso.

   ![](assets/aem_authoring_7.png)

1. Adicione um **[!UICONTROL Label]** à entrega e clique em **[!UICONTROL Continue]**.

1. Clique em **[!UICONTROL Synchronize]** para acessar seus deliveries de AEM.

   Se o botão não estiver visível na interface, navegue até a **[!UICONTROL Properties]** e acesse o botão **[!UICONTROL Advanced]** guia. Certifique-se de que o **[!UICONTROL Content editing mode]** O campo está configurado para **[!UICONTROL AEM]** e insira os detalhes da instância do AEM no campo **[!UICONTROL AEM account]** campo.

   ![](assets/aem_authoring_8.png)

1. Selecione o delivery de AEM criado anteriormente no [!DNL Adobe Experience Manager] e confirme clicando em **[!UICONTROL Ok]**.

   ![](assets/aem_authoring_11.png)

1. Clique no link **[!UICONTROL Refresh content]** sempre que modificações forem feitas no delivery de AEM.

   ![](assets/aem_authoring_12.png)

1. Para remover a vinculação entre o Experience Manager e o Campaign, clique em **[!UICONTROL Desynchronize]**.

O email agora está pronto para ser enviado ao seu público-alvo.

## Importar ativos da biblioteca do Adobe Experience Manager Assets {#assets-library}

Você também pode inserir ativos diretamente da sua [!DNL Adobe Experience Manager Assets Library] ao editar um email ou uma landing page no Adobe Campaign. Essa funcionalidade é detalhada em [Documentação do Adobe Experience Manager Assets](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html){target="_blank"}.

**No Adobe Experience Manager:**

1. Navegue até o [!DNL Adobe Experience Manager] instância do autor e clique em Experiência Adobe no canto superior esquerdo da página. Escolher **[!UICONTROL Assets]** `>` **[!UICONTROL Files]** no menu.

   ![](assets/aem_assets_1.png)

1. Clique em **Criar** depois **Arquivos** para importar o ativo para o **Biblioteca da Adobe Experience Manager Assets**. Saiba mais em [Documentação do Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html#uploading-assets){target="_blank"}.

   ![](assets/aem_assets_2.png)

1. Renomeie o ativo se necessário e selecione **Carregar**.

Seu ativo agora está carregado no **Biblioteca da Adobe Experience Manager Assets**.

**No Adobe Campaign:**

1. No Adobe Campaign, crie um novo delivery navegando até o **Campanhas** clique em **Entregas** e clique no link **Criar** acima da lista de deliveries existentes.

   ![](assets/aem_assets_3.png)

1. Selecione um **Modelo de entrega**, nomeie o delivery.

1. Defina e personalize o conteúdo da mensagem. [Saiba mais](../send/email.md)

1. Para usar o **Biblioteca do Adobe Experience Manager Assets**, acesse o **[!UICONTROL Properties]** do seu delivery de AEM e selecione o **[!UICONTROL Advanced]** guia.

   Escolha o seu **Conta do AEM** e habilite o **[!UICONTROL Use above AEM instance as shared asset library]** opção.

   ![](assets/aem_authoring_9.png)

1. No **Imagem** ícone, acesse o **[!UICONTROL Select a shared asset]** menu.

   ![](assets/aem_assets_4.png)

1. Na janela de seleção, selecione uma imagem da sua **Biblioteca do Adobe Experience Manager Assets**, depois **Selecionar**.

   ![](assets/aem_assets_5.png)

Seu ativo agora é carregado para o delivery de email. Agora você pode especificar o público-alvo, confirmar o delivery e continuar com o envio.
