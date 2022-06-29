---
title: Enviar emails com o Adobe Campaign
description: Introdução aos emails no Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Criar e enviar emails

Os deliveries de email permitem enviar emails personalizados para a população do target.

![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html){target=&quot;_blank&quot;}

## Criar seu primeiro delivery de email

Crie emails personalizados e contextualmente relevantes que sejam consistentes com o restante da experiência do cliente.

![](assets/new-email-content.png)


No exemplo a seguir, você aprenderá as etapas para criar um delivery de email no Adobe Campaign que contenha dados personalizados, links para um URL externo e um link para a mirror page.

1. **Criar o delivery**

   Para criar um novo delivery, navegue até o **Campanhas** clique em **Deliveries** e clique no botão **Criar** acima da lista de deliveries existentes.

   ![](assets/delivery_step_1.png)

1. **Selecionar o modelo**

   Selecione um template do delivery e nomeie o delivery. Esse nome só será visível para os usuários do console do Adobe Campaign e não por seus recipients, no entanto, esse título será exibido na lista de deliveries. Clique em **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importe seu conteúdo**

   Clique no botão **Origem** para colar o conteúdo do HTML.

   ![](assets/paste-content.png)


1. **Personalizar sua mensagem**


   * Adicione o nome e o sobrenome dos recipients

      Para inserir o nome e o sobrenome dos perfis segmentados no conteúdo da mensagem, coloque o cursor onde deseja inseri-los e clique no último ícone na barra de ferramentas, em seguida, clique em **[!UICONTROL Include]** e selecione **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      Navegue até a guia Preview para verificar a personalização selecionando um recipient.

      ![](assets/perso-check.png)

   * Inserir um link rastreado

      Para levar os recipients do delivery para um endereço externo por meio de uma imagem ou um texto, selecione-o e clique no botão **[!UICONTROL Add a link]** na barra de ferramentas.

      Insira a URL do link no campo **URL** usando o seguinte formato **https://www.myURL.com** e, em seguida, confirme.

      ![](assets/add-a-link.png)

   * Adicionar uma mirror page

      Para permitir que seus recipients visualizem o conteúdo do delivery em um navegador da Web, adicione um link à mirror page da mensagem.

      Coloque o cursor onde deseja inserir este link, clique no último ícone na barra de ferramentas e clique em **[!UICONTROL Include]** e selecione **[!UICONTROL link to mirror page]**.
   Quando o conteúdo estiver pronto, clique em **Salvar**: agora ele será exibido na lista de deliveries, no **[!UICONTROL Campaigns > Deliveries]** guia . Seu primeiro delivery de email está pronto. Agora é necessário definir o público-alvo, validar o delivery e enviá-lo.


Saiba mais nestas seções da documentação do Campaign Classic v7:

* Criar um email no Campaign
   ![](../assets/do-not-localize/book.png) [Saiba como criar um email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html){target=&quot;_blank&quot;}
* Importar conteúdo de email
   ![](../assets/do-not-localize/book.png) [Caso de uso: Criar um workflow para carregar um conteúdo de delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html){target=&quot;_blank&quot;}
* Criar e usar um modelo de email
   ![](../assets/do-not-localize/book.png) [Saiba mais sobre modelos de e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=pt-BR){target=&quot;_blank&quot;}
* Selecione o público do seu email
   ![](../assets/do-not-localize/book.png) [Saiba como definir a população do target](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}
* Validar um delivery e enviar provas
   ![](../assets/do-not-localize/book.png) [Saiba mais sobre as principais etapas para validar um delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* Adicionar [seed addresses](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## Testar e validar seus emails

O Campaign oferece várias maneiras de testar e validar seus emails antes de enviá-los para seus públicos.

![](../assets/do-not-localize/book.png) [Aplicar práticas recomendadas listadas na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html){target=&quot;_blank&quot;}

Você pode:

* Verificar logs de análise do delivery
* Enviar provas
* Adicionar seed addresses
* Usar grupos de controle
* Verificar renderização de email

![](../assets/do-not-localize/book.png) [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
