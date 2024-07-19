---
title: Usar blocos de personalização
description: Saiba como usar blocos de personalização integrados no conteúdo da mensagem
feature: Personalization
role: User
level: Beginner
exl-id: 214ad693-d456-47ec-a9c8-199ba23c3d9c
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 34%

---

# Usar blocos de personalização{#personalization-blocks}

Os blocos de personalização são conteúdos dinâmicos que contêm uma renderização específica que pode ser inserida em seus deliveries. Por exemplo, você pode adicionar um logotipo, uma mensagem de saudação ou um link para uma mirror page.

Para acessar blocos de conteúdo personalizados, navegue até o nó **[!UICONTROL Resources > Campaign Management > Personalization blocks]** do explorador. Os blocos de personalização internos estão listados em [esta seção](#ootb-personalization-blocks).

Você também pode definir novos blocos para otimizar a personalização dos deliveries. [Saiba mais](#create-custom-personalization-blocks).

## Inserir blocos de personalização {#insert-personalization-blocks}

Para inserir um bloco de personalização em uma mensagem, siga as etapas abaixo:

1. No editor de conteúdo do assistente de entrega, clique no ícone de personalização e selecione o menu **[!UICONTROL Include]**.
1. Selecione um bloco de personalização na lista ou clique no menu **[!UICONTROL Other...]** para acessar a lista completa.

   ![](assets/perso-content-block.png)

1. O bloco de personalização é então inserido como um script. Ele é adaptado automaticamente ao perfil do destinatário quando a personalização é gerada.
1. Navegue até a guia **[!UICONTROL Preview]** e selecione um destinatário para exibir o conteúdo deste bloco para um destinatário específico.

Você pode incluir o código-fonte de um bloco de personalização no conteúdo da entrega. Para fazer isso, selecione **[!UICONTROL Include the HTML source code of the block]** ao selecioná-lo.

## Blocos de personalização incorporados {#ootb-personalization-blocks}

Os blocos de personalização incorporados são:

* **[!UICONTROL Enabled by Adobe Campaign]**: insere o logotipo &quot;Habilitado pela Adobe Campaign&quot;.
* **[!UICONTROL Formatting function for proper nouns]**: gera a função JavaScript **[!UICONTROL toSmartCase]**, que coloca a primeira letra de cada palavra em maiúscula.
* **[!UICONTROL Greetings]**: insere saudações com o nome completo do destinatário, seguido por vírgula. Exemplo: “Olá, fulano,”.
* **[!UICONTROL Insert logo]**: insere um logotipo que é definido nas configurações de instância.
* **[!UICONTROL Link to mirror page]**: insere um link para a [mirror page](mirror-page.md). O formato padrão é: &quot;Caso não consiga visualizar esta mensagem corretamente, clique aqui.&quot;
* **[!UICONTROL Mirror page URL]**: insere a URL da mirror page, permitindo que os designers de entrega verifiquem o link.
* **[!UICONTROL Offer acceptance URL in unitary mode]**: insere uma URL que permite definir uma oferta para **[!UICONTROL Accepted]**. (Este bloco estará disponível se o módulo Interação estiver habilitado)
* **[!UICONTROL Registration confirmation]**: insere um link que permite confirmar a assinatura.
* **[!UICONTROL Registration link]**: insere um link de assinatura. Esse link é definido nas configurações da instância. O conteúdo padrão é: &quot;Para se registrar, clique aqui&quot;.
* **[!UICONTROL Registration link (with referrer)]**: insere um link de assinatura, permitindo identificar o visitante e a entrega. Esse link é definido nas configurações da instância.
* **[!UICONTROL Registration page URL]**: insere uma URL de assinatura
* **[!UICONTROL Style of content emails]** e **[!UICONTROL Notification style]**: geram um código que formata um email com estilos de HTML predefinidos.
* **[!UICONTROL Unsubscription link]**: insere um link que permite cancelar a inscrição de todas as entregas (incluir na lista de bloqueios). O conteúdo padrão associado é: &quot;Você está recebendo esta mensagem porque esteve em contato com ***nome da organização*** ou um afiliado. Para não receber mais mensagens de ***nome da organização*** clique aqui.&quot;

## Criar blocos de personalização personalizados {#create-custom-personalization-blocks}

Você pode definir novos blocos de conteúdo personalizado a serem inseridos no ícone de personalização.

Para criar um bloco de personalização, siga as etapas abaixo:

1. Navegue até a pasta **[!UICONTROL Resources > Campaign Management > Personalization blocks]** do explorador do Campaign.
1. Acima da lista de blocos internos, clique em **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. Preencha as configurações do bloco de personalização:

   ![](assets/perso-custom-block.png)

   * Insira o rótulo do bloco. Esse rótulo é exibido na janela de inserção do campo de personalização.
   * Selecione um tipo de conteúdo de **Entrega**.
   * Habilite a opção **[!UICONTROL Visible in the customization menus]** para tornar esse bloco acessível a partir do ícone de inserção do campo de personalização.
   * Se necessário, habilite a opção **[!UICONTROL The content of the personalization block depends upon the format]** para definir dois blocos diferentes para emails de HTML e Texto.
   * Insira o conteúdo (em HTML, texto, JavaScript, etc.) do bloco de personalização e clique em **[!UICONTROL Save]**.

Depois de salvo, o novo bloco de personalização fica disponível no editor de delivery.

## Tutorial em vídeo {#personalization-blocks-video}

Saiba como criar blocos de conteúdo dinâmico e como usá-los para personalizar o conteúdo de sua entrega de email no vídeo a seguir.

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)
