---
product: Adobe Campaign
title: Enviar emails com o Adobe Campaign
description: Introdução a emails no Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
source-git-commit: d1e96b1311d9de24ceb918230186cd3cad609ab2
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 51%

---

# Criar e enviar emails

Os deliveries de email permitem enviar emails personalizados para a população do target.

[!DNL :arrow_upper_right:] Saiba mais na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html).

## Criar seu primeiro delivery de email

Crie emails personalizados e relevantes contextualmente que sejam consistentes com o resto da experiência do cliente.

![](assets/new-email-content.png)

[!DNL :arrow_upper_right:] [Saiba como criar um delivery de email na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/use-case--creating-an-email-delivery.html)


No exemplo a seguir, você aprenderá as etapas para criar um delivery de email no Adobe Campaign que contenha dados personalizados, links para um URL externo, um link para a mirror page e um link para um formulário da Web.

1. Criar o delivery

   Para criar um novo delivery, navegue até a guia **Campaigns**, clique em **Deliveries** e clique no botão **Create** acima da lista de deliveries existentes.

   ![](assets/delivery_step_1.png)

1. Selecionar o modelo

   Selecione um template do delivery e nomeie o delivery. Esse nome só será visível para os usuários do console do Adobe Campaign e não por seus recipients, no entanto, esse título será exibido na lista de deliveries. Clique em **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. Importe seu conteúdo

   Clique na guia **Source** para colar seu conteúdo HTML.

   ![](assets/paste-content.png)


1. Personalizar sua mensagem


   * Exiba o nome e o sobrenome dos recipients

      Para inserir o nome e o sobrenome dos recipients em um campo de texto no delivery, clique no campo de texto escolhido e coloque o cursor onde deseja exibi-los. Clique no primeiro ícone na barra de ferramentas pop-up e, depois, em **[!UICONTROL Personalization block]**. Selecione **[!UICONTROL Greetings]** e clique em **[!UICONTROL OK]**.

   * Inserir um link em uma imagem

      Para levar os destinatários do delivery para um endereço externo por meio de uma imagem, clique na imagem relevante para exibir a barra de ferramentas pop-up, coloque o cursor no primeiro ícone e clique em **[!UICONTROL Link to an external URL]**.

      Insira a URL do link no campo **URL** usando o seguinte formato **https://www.myURL.com** e, em seguida, confirme.

      O link pode ser alterado a qualquer momento usando a seção à direita da janela.

   * Inserir um link no texto

      Para integrar um link externo ao texto no seu delivery, selecione um texto ou um bloco de texto e clique no primeiro ícone na barra de ferramentas pop-up. Clique em **[!UICONTROL Link to an external URL]** e digite o endereço do link no campo **[!UICONTROL URL]**.

      O link pode ser alterado a qualquer momento usando a seção à direita da janela.

   * Adicionar uma mirror page

      Para permitir que os recipients vejam o conteúdo do delivery em um navegador da Web, você pode integrar um link a uma mirror page no delivery.

      Clique no campo de texto em que você deseja ver o link publicado. Clique no primeiro ícone na barra de ferramentas pop-up, selecione **[!UICONTROL Personalization block]** e, então, **[!UICONTROL Link to Mirror Page (MirrorPage)]**. Clique em **[!UICONTROL Save]** para confirmar.

   * Integrar um link a uma aplicação web

      O Editor de conteúdo digital permite integrar links às aplicações web no console do Adobe Campaign, como uma landing page ou uma página de formulário. Para saber mais, consulte [Vincular a uma aplicação web](../../web/using/editing-content.md#link-to-a-web-application).

      Selecione um campo de texto para seu link para uma aplicação web e clique no primeiro ícone. Escolha **[!UICONTROL Link to a Web application]** e selecione a aplicação desejada clicando no ícone no final do campo **Web Application**.

1. Enviar mensagens

   Quando o conteúdo for integrado, salve o delivery clicando em **Salvar**. Agora ele será exibido na lista de deliveries, encontrada na guia **[!UICONTROL Campaigns > Deliveries]**.


## Criar conteúdo e selecionar o público

Você pode criar diretamente no Campaign ou importar seu público, bem como seu conteúdo de email. Use os links abaixo para saber como:

* Criar um email no Campaign
   [!DNL :arrow_upper_right:] [Saiba como criar um email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* Importar conteúdo de email
   [!DNL :arrow_upper_right:] [Caso de uso: Criar um workflow para carregar um conteúdo de delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* Criar e usar um modelo de email
   [!DNL :arrow_upper_right:] [Saiba mais sobre templates de email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* Selecione o público do seu email
   [!DNL :arrow_upper_right:] [Saiba como definir a população do target](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* Validar um delivery e enviar provas
   [!DNL :arrow_upper_right:] [Saiba mais sobre as principais etapas para validar um delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* Adicionar [seed addresses](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## Testar e validar seus emails

O Campaign oferece várias maneiras de testar e validar seus emails antes de enviá-los para seus públicos.

[!DNL :arrow_upper_right:] [Aplicar práticas recomendadas listadas na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

Você pode:

* Verificar logs de análise do delivery
* Enviar provas
* Adicionar seed addresses
* Usar grupos de controle
* Verificar renderização de email

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## Monitorar emails

Depois de enviado, verifique o status do delivery no Painel de delivery e acesse os logs do delivery e os relatórios para confirmar se as mensagens foram enviadas corretamente.

[!DNL :arrow_upper_right:] [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)

