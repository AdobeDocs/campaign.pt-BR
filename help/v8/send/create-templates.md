---
product: campaign
title: Trabalho com modelos de entrega
description: Saiba como criar e usar templates de delivery no Campaign
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 48%

---

# Trabalhar com o template de delivery{#work-with-delivery-template}

Use templates do delivery para padronizar a aparência criativa, a fim de ser mais rápido na execução e na inicialização de campanhas.

Um modelo pode incluir:

* Tipologias
* Endereços de remetente e de resposta
* Básico [blocos de personalização](../send/personalization-blocks.md)
* Links para [mirror pages](../send/mirror-page.md) e links de unsubscription
* Conteúdo, logotipo da empresa ou assinatura
* Outras propriedades de delivery, como validade de recursos, parâmetros de nova tentativa ou configurações de quarentena.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#delivery-template-video)


## Criar um modelo{#create-a-delivery-template}

Para criar um template de delivery, você pode duplicar um template incorporado, converter um delivery existente em um template ou criar um template de delivery do zero.

### Duplicação de um template existente{#copy-an-existing-template}

O Campaign vem com um conjunto de modelos incorporados para cada canal: email, push, SMS, mala direta e muito mais.

A maneira mais fácil de criar um template do delivery é duplicar e personalizar um template incorporado.

Para duplicar um template de delivery, siga as etapas abaixo:

1. Navegue até **[!UICONTROL Resources > Templates > Delivery templates]** no Adobe Campaign Explorer.
1. Selecione um template do delivery incorporado. Os modelos incorporados estão em negrito na lista.
1. Clique com o botão direito do mouse e selecione **[!UICONTROL Duplicate]**.

   ![](assets/duplicate-built-in-template.png)

1. Defina as configurações do modelo e salve o novo modelo.

   ![](assets/delivery-template-new.png)

O template é adicionado à lista de templates do delivery. Agora é possível selecioná-lo ao criar um novo delivery.

![](assets/select-the-new-template.png)

### Converter um delivery existente em um template {#convert-an-existing-delivery}

Uma entrega pode ser convertida em um modelo para novas ações de entrega repetidas.

Para converter um delivery em um template, siga as etapas abaixo:

1. Selecione o delivery na lista de delivery, acessível por meio do **[!UICONTROL Campaign management]** nó do explorador do Campaign.

1. Clique com o botão direito do mouse e selecione **[!UICONTROL Actions > Save as template...]**.

   ![](assets/save-as-template.png)

1. Edite as propriedades do delivery e selecione a pasta onde o novo template deve ser salvo (na **[!UICONTROL Folder]** ) e a pasta onde os deliveries criados com base nesse template devem ser criados (na **[!UICONTROL Execution folder]** campo ).

   ![](assets/template-select-folders.png)

### Criar um novo modelo {#create-a-new-template}

>[!NOTE]
>
>Para evitar erros de configuração, o Adobe recomenda que você [duplicar um template incorporado](#copy-an-existing-template) e personalize suas propriedades em vez de criar um novo modelo.

Para configurar um template de delivery do zero, siga as etapas abaixo:

1. Navegue até o **Recursos** no explorador do Campaign e selecione **Modelos** then **Templates de delivery**.
1. Clique em **New** na barra de ferramentas para criar um novo template de delivery.
1. Defina as **Rótulo** e **Nome interno** da pasta.
1. Salve seu template e abra-o novamente.
1. No **Propriedades** , adapte as configurações.
1. Na guia **General**, confirme ou altere os locais selecionados nos menus suspensos **Execution folder**, **Folder**, e **Routing.**
1. Complete a categoria **Email parameters** com o assunto do email e o público alvo.
1. Adicione seu **HTML** content para personalizar seu template, você pode exibir um link de mirror page e um link de unsubscription.[](../send/mirror-page.md)
1. Selecione a guia **Preview.** No menu suspenso **Test personalization**, selecione **Recipient** para visualizar seu template como o perfil escolhido.
1. Clique em **Save**. Seu template está pronto para ser usado em uma entrega.


## Usar modelos{#use-a-delivery-template}

### Criar um delivery a partir de um modelo{#create-a-delivery-from-a-template}

Para criar uma entrega com base em um modelo existente, selecione um modelo disponível na lista..

![](assets/select-the-new-template.png)

Se não conseguir ver seu modelo, clique no botão **[!UICONTROL Select link]** à direita do campo para procurar pastas do Campaign.

![](assets/browse-templates.png)

Selecione o diretório desejado no campo **[!UICONTROL Folder]** ou clique no ícone **[!UICONTROL Display sub-levels]** para exibir o conteúdo dos diretórios nas subárvores do diretório atual.

Selecione o template de delivery a ser usado e clique em **[!UICONTROL Ok]**.

### Executar um modelo {#execute-a-template}

Você pode iniciar a execução de um template diretamente da lista de templates sem criar um delivery primeiro.

Para fazer isso, selecione o template a ser executado e clique com o botão direito do mouse. Selecione **[!UICONTROL Actions>Execute the delivery template...]**.

Você também pode usar **[!UICONTROL File>Actions>Execute the delivery template...]**.

![](assets/execute-delivery-template.png)

Insira os parâmetros de delivery e clique em **[!UICONTROL Send]**.

Essa ação gera um delivery na pasta associada ao template. O nome desse delivery é o nome do template de delivery do qual foi criado.


## Tutoriais em vídeo {#delivery-template-video}

### Como configurar um template de entrega

O vídeo a seguir mostra como configurar um modelo para uma entrega ad hoc.

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### Como configurar propriedades de templates de entrega

O vídeo a seguir mostra como definir as propriedades do template de entrega e explica em detalhes cada propriedade.

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### Como implantar um template de entrega ad-hoc

Este vídeo explica como implantar um template de entrega de email ad-hoc, bem como a diferença entre uma entrega de email e um workflow de entrega.

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

Vídeos explicativos extras sobre o Campaign estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
