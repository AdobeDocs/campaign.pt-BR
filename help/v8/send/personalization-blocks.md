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

Para acessar blocos de conteúdo personalizados, navegue até o **[!UICONTROL Resources > Campaign Management > Personalization blocks]** nó do explorador. Os blocos de personalização incorporados estão listados em [nesta seção](#ootb-personalization-blocks).

Você também pode definir novos blocos para otimizar a personalização dos deliveries. [Saiba mais](#create-custom-personalization-blocks).

## Inserir blocos de personalização {#insert-personalization-blocks}

Para inserir um bloco de personalização em uma mensagem, siga as etapas abaixo:

1. No editor de conteúdo do assistente de delivery, clique no ícone de personalização e selecione o **[!UICONTROL Include]** menu.
1. Selecione um bloco de personalização na lista ou clique no botão **[!UICONTROL Other...]** para acessar a lista completa.

   ![](assets/perso-content-block.png)

1. O bloco de personalização é então inserido como um script. Ele é adaptado automaticamente ao perfil do destinatário quando a personalização é gerada.
1. Navegue até o **[!UICONTROL Preview]** e selecione um recipient para exibir o conteúdo deste bloco para um recipient específico.

Você pode incluir o código-fonte de um bloco de personalização no conteúdo da entrega. Para fazer isso, selecione **[!UICONTROL Include the HTML source code of the block]** ao selecioná-lo.

## Blocos de personalização incorporados {#ootb-personalization-blocks}

Os blocos de personalização incorporados são:

* **[!UICONTROL Enabled by Adobe Campaign]**: insere o logotipo &quot;Ativado pelo Adobe Campaign&quot;.
* **[!UICONTROL Formatting function for proper nouns]**: gera o **[!UICONTROL toSmartCase]** Função JavaScript, que coloca a primeira letra de cada palavra em maiúscula.
* **[!UICONTROL Greetings]**: insere saudações com o nome completo do destinatário, seguido por uma vírgula. Exemplo: “Olá, fulano,”.
* **[!UICONTROL Insert logo]**: insere um logotipo definido nas configurações de instância.
* **[!UICONTROL Link to mirror page]**: insere um link para o [mirror page](mirror-page.md). O formato padrão é: &quot;Caso não consiga visualizar esta mensagem corretamente, clique aqui.&quot;
* **[!UICONTROL Mirror page URL]**: insere o URL da mirror page, permitindo que os designers de delivery verifiquem o link.
* **[!UICONTROL Offer acceptance URL in unitary mode]**: insere um URL que permite definir uma oferta para **[!UICONTROL Accepted]**. (Este bloco estará disponível se o módulo Interação estiver habilitado)
* **[!UICONTROL Registration confirmation]**: insere um link que permite confirmar a subscrição.
* **[!UICONTROL Registration link]**: insere um link de subscrição. Esse link é definido nas configurações da instância. O conteúdo padrão é: &quot;Para se registrar, clique aqui&quot;.
* **[!UICONTROL Registration link (with referrer)]**: insere um link de subscrição, permitindo identificar o visitante e o delivery. Esse link é definido nas configurações da instância.
* **[!UICONTROL Registration page URL]**: insere um URL de subscrição
* **[!UICONTROL Style of content emails]** e **[!UICONTROL Notification style]**: gerar um código que formata um email com estilos de HTML predefinidos.
* **[!UICONTROL Unsubscription link]**: insere um link que permite cancelar a inscrição de todos os deliveries (incluir na lista de bloqueios). O conteúdo padrão associado é: &quot;Você está recebendo esta mensagem porque esteve em contato com ***nome da organização*** ou um afiliado. Para não receber mais mensagens de ***nome da organização*** clique aqui.&quot;

## Criar blocos de personalização personalizados {#create-custom-personalization-blocks}

Você pode definir novos blocos de conteúdo personalizado a serem inseridos no ícone de personalização.

Para criar um bloco de personalização, siga as etapas abaixo:

1. Navegue até o **[!UICONTROL Resources > Campaign Management > Personalization blocks]** pasta do explorador do Campaign.
1. Acima da lista de blocos incorporados, clique em **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. Preencha as configurações do bloco de personalização:

   ![](assets/perso-custom-block.png)

   * Insira o rótulo do bloco. Esse rótulo é exibido na janela de inserção do campo de personalização.
   * Selecione um **Entrega** tipo de conteúdo.
   * Ativar o **[!UICONTROL Visible in the customization menus]** opção para tornar esse bloco acessível a partir do ícone de inserção do campo de personalização.
   * Se necessário, ative a opção **[!UICONTROL The content of the personalization block depends upon the format]** opção, para definir dois blocos diferentes para emails de HTML e Texto.
   * Insira o conteúdo (em HTML, texto, JavaScript, etc.) do bloco de personalização e clique em **[!UICONTROL Save]**.

Depois de salvo, o novo bloco de personalização fica disponível no editor de delivery.

## Tutorial em vídeo {#personalization-blocks-video}

Saiba como criar blocos de conteúdo dinâmico e como usá-los para personalizar o conteúdo de sua entrega de email no vídeo a seguir.

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)
