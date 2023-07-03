---
title: Enviar emails com o Adobe Campaign
description: Introdução aos emails no Adobe Campaign. Envie emails personalizados para uma população de público alvo.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 500de76853772313b1aac655da2f1b3562de2c55
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 22%

---

# Criar e enviar emails

Os deliveries de email permitem enviar emails personalizados para a população do target. [Saiba mais](../send/send.md)

## Criar o primeiro delivery de email

Crie emails personalizados e contextualmente relevantes que sejam consistentes com o restante da experiência do cliente.

![](assets/new-email-content.png)


No exemplo a seguir, você aprenderá as etapas para criar um delivery de email no Adobe Campaign que contenha dados personalizados, links para um URL externo e um link para a mirror page.

1. **Criar o delivery**

   Para criar um novo delivery, navegue até o **Campanhas** clique em **Entregas** e clique no link **Criar** acima da lista de deliveries existentes.

   ![](assets/delivery_step_1.png)

1. **Selecionar o modelo**

   Selecione um template do delivery e nomeie o delivery. Esse nome só será visível para os usuários do console do Adobe Campaign e não por seus recipients, no entanto, esse título será exibido na lista de deliveries. Clique em **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importar seu conteúdo**

   Clique em **Origem** para colar o conteúdo do HTML.

   ![](assets/paste-content.png)


1. **Personalizar sua mensagem**

   * Adicione o nome e o sobrenome dos recipients

     Para inserir o nome e o sobrenome dos perfis direcionados no conteúdo da mensagem, coloque o cursor onde deseja inseri-los e clique no último ícone na barra de ferramentas e, em seguida, clique em **[!UICONTROL Include]** e selecione **[!UICONTROL Greetings]**.

     ![](assets/include-greetings.png)

     Navegue até a guia de visualização para verificar a personalização selecionando um recipient.

     ![](assets/perso-check.png)

     Saiba mais sobre as opções de personalização no [nesta seção](personalize.md).

   * Inserir um link rastreado

     Para levar os recipients do delivery para um endereço externo por meio de uma imagem ou um texto, selecione-o e clique no link **[!UICONTROL Add a link]** na barra de ferramentas.

     Insira a URL do link no campo **URL** usando o seguinte formato **https://www.myURL.com** e, em seguida, confirme.

     ![](assets/add-a-link.png)

   * Adicionar uma mirror page

     Para permitir que seus destinatários visualizem o conteúdo do delivery em um navegador da Web, adicione um link à [mirror page](mirror-page.md) da sua mensagem.

     Coloque o cursor onde deseja inserir esse link, clique no último ícone na barra de ferramentas e clique em **[!UICONTROL Include]** e selecione **[!UICONTROL link to mirror page]**.

     Saiba mais sobre o gerenciamento da mirror page no [nesta seção](mirror-page.md#link-to-mirror-page).

1. Você pode definir parâmetros adicionais para o email, como enviar uma cópia das mensagens para um endereço BBC, alterar o formato da mensagem, definir uma codificação específica etc. Saiba mais [nesta seção](email-parameters.md).

1. Quando o conteúdo estiver pronto, clique em **Salvar**: agora ele será exibido na lista de deliveries, no **[!UICONTROL Campaigns > Deliveries]** guia.

Seu primeiro delivery de email está pronto. Agora é necessário definir o público-alvo, validar o delivery e enviá-lo.

Saiba como importar um conteúdo de email neste [caso de uso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html).

Saiba mais nas seguintes seções:

<!--[Design an email in Campaign]-->
* [Criar e usar um modelo de email](../send/create-templates.md)
* [Selecionar a audiência do seu email](../audiences/gs-audiences.md)
* [Validar um delivery e enviar provas](preview-and-proof.md)
* [Configurar e enviar o delivery](configure-and-send.md)

## Testar e validar seus emails

O Campaign oferece várias maneiras de testar e validar seus emails antes de enviá-los para seus públicos. Saiba como pré-visualizar e testar seu conteúdo de email no [nesta seção](../send/preview-and-proof.md).

Você pode:

* [Enviar provas](preview-and-proof.md)
* [Adicionar seed addresses](../audiences/test-profiles.md)
* [Verificar logs de análise de entrega](delivery-analysis.md)

