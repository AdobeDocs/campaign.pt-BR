---
title: Usar blocos de personalização
description: Saiba como usar blocos de personalização integrados no conteúdo da sua mensagem
feature: Personalization
role: User
level: Beginner
exl-id: 214ad693-d456-47ec-a9c8-199ba23c3d9c
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 31%

---

# Usar blocos de personalização{#personalization-blocks}

Os blocos de personalização são conteúdo dinâmico que contém uma renderização específica que pode ser inserida nos deliveries. Por exemplo, você pode adicionar um logotipo, uma mensagem de saudação ou um link para uma mirror page.

Para acessar blocos de conteúdo personalizado, navegue até o **[!UICONTROL Resources > Campaign Management > Personalization blocks]** nó do explorador. Os blocos de personalização incorporados são listados em [esta seção](#ootb-personalization-blocks).

Você também pode definir novos blocos para otimizar a personalização de seus deliveries. [Saiba mais](#create-custom-personalization-blocks).

## Inserir blocos de personalização {#insert-personalization-blocks}

Para inserir um bloco de personalização em uma mensagem, siga as etapas abaixo:

1. No editor de conteúdo do assistente de delivery, clique no ícone de personalização e selecione o **[!UICONTROL Include]** menu.
1. Selecione um bloco de personalização na lista ou clique no botão **[!UICONTROL Other...]** para acessar a lista completa.

   ![](assets/perso-content-block.png)

1. O bloco de personalização é então inserido como um script. Ele é adaptado automaticamente ao perfil do recipient quando a personalização é gerada.
1. Navegue até o **[!UICONTROL Preview]** e selecione um recipient para exibir o conteúdo desse bloco para um recipient específico.

Você pode incluir o código-fonte de um bloco de personalização no conteúdo do delivery. Para fazer isso, selecione **[!UICONTROL Include the HTML source code of the block]** ao selecioná-lo.

## Blocos de personalização incorporados {#ootb-personalization-blocks}

Os blocos de personalização incorporados são:

* **[!UICONTROL Enabled by Adobe Campaign]**: insere o logotipo &quot;Ativado pela Adobe Campaign&quot;.
* **[!UICONTROL Formatting function for proper nouns]**: gera a função JavaScript **[!UICONTROL toSmartCase]**, que coloca a primeira letra de cada palavra em maiúscula.
* **[!UICONTROL Greetings]**: insere saudações com o nome completo do recipient, seguido de uma vírgula. Exemplo: “Olá, John Doe”.
* **[!UICONTROL Insert logo]**: insere um logotipo que é definido nas configurações de instância.
* **[!UICONTROL Link to mirror page]**: insere um link para o [mirror page](mirror-page.md). O formato padrão é: &quot;Se não conseguir exibir esta mensagem corretamente, clique aqui&quot;.
* **[!UICONTROL Mirror page URL]**: insere o URL da mirror page, permitindo que os designers de delivery verifiquem o link.
* **[!UICONTROL Offer acceptance URL in unitary mode]**: insere um URL que permite definir uma oferta para **[!UICONTROL Accepted]**. (Este bloco estará disponível se o módulo Interaction estiver habilitado)
* **[!UICONTROL Registration confirmation]**: insere um link que permite confirmar a subscrição.
* **[!UICONTROL Registration link]**: insere um link de subscrição. Esse link é definido nas configurações da instância. O conteúdo padrão é: &quot;Para registrar, clique aqui.&quot;
* **[!UICONTROL Registration link (with referrer)]** : insere um link de subscrição, permitindo identificar o visitante e o delivery. Esse link é definido nas configurações da instância.
* **[!UICONTROL Registration page URL]**: insere um URL de subscrição
* **[!UICONTROL Style of content emails]** e **[!UICONTROL Notification style]**: gere um código que formate um email com estilos de HTML predefinidos.
* **[!UICONTROL Unsubscription link]**: insere um link que permite cancelar a inscrição de todos os deliveries (lista de bloqueios). O conteúdo associado padrão é: &quot;Você está recebendo esta mensagem porque esteve em contato com ***nome da organização*** ou um afiliado. Para não receber mais mensagens de ***nome da organização*** clique aqui.&quot;

## Criar blocos de personalização customizados {#create-custom-personalization-blocks}

Você pode definir novos blocos de conteúdo personalizado a serem inseridos no ícone de personalização.

Para criar um bloco de personalização, siga as etapas abaixo:

1. Navegue até o **[!UICONTROL Resources > Campaign Management > Personalization blocks]** pasta do explorador do Campaign.
1. Acima da lista de blocos incorporados, clique em **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. Preencha as configurações do bloco de personalização:

   ![](assets/perso-custom-block.png)

   * Insira o rótulo do bloco. Esse rótulo é exibido na janela de inserção do campo de personalização.
   * Selecione um **Delivery** tipo de conteúdo.
   * Ative o **[!UICONTROL Visible in the customization menus]** para tornar esse bloco acessível a partir do ícone de inserção do campo de personalização.
   * Se necessário, ative a **[!UICONTROL The content of the personalization block depends upon the format]** para definir dois blocos diferentes para emails de HTML e Texto.
   * Insira o conteúdo (em HTML, texto, JavaScript, etc.) do bloco de personalização e clique em **[!UICONTROL Save]**.

Depois de salvo, o novo bloco de personalização está disponível no editor de delivery.

## Tutorial em vídeo {#personalization-blocks-video}

Saiba como criar blocos de conteúdo dinâmico e como usá-los para personalizar o conteúdo do delivery de email no vídeo a seguir.

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)
