---
title: Enviar emails com o Adobe Campaign
description: Introdução aos emails no Adobe Campaign. Envie emails personalizados para uma população de público alvo.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: cf292ecd7d30862d7d195536ecc5be709fe037b3
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 21%

---

# Criar e enviar emails

Os deliveries de email permitem enviar emails personalizados para a população do target. [Saiba mais](../send/send.md)

Saiba mais sobre as principais etapas para criar e configurar uma entrega em [esta página](../start/create-message.md).

## Criar o primeiro delivery de email

Crie emails personalizados e contextualmente relevantes que sejam consistentes com o restante da experiência do cliente.

![](assets/new-email-content.png)


No exemplo a seguir, você aprenderá as etapas para criar um delivery de email no Adobe Campaign que contenha dados personalizados, links para um URL externo e um link para a mirror page.

1. **Criar a entrega**

   Para criar uma nova entrega, navegue até a guia **Campanhas**, clique em **Entregas** e clique no botão **Criar** acima da lista de entregas existentes.

   ![](assets/delivery_step_1.png)

1. **Selecione o modelo**

   Selecione um template da entrega e nomeie a entrega. Esse nome só será visível para os usuários do console do Adobe Campaign e não por seus destinatários, no entanto, esse título será exibido na lista de entregas. Clique em **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importar seu conteúdo**

   Clique na guia **Source** para colar o conteúdo em HTML.

   ![](assets/paste-content.png)

   >[!NOTE]
   >
   >Para evitar problemas de desempenho, as imagens incluídas nos emails não podem exceder 100 KB.

1. **Personalizar sua mensagem**

   * Adicione o nome e o sobrenome dos recipients

     Para inserir o nome e o sobrenome dos perfis direcionados no conteúdo da mensagem, coloque o cursor onde deseja inseri-los, clique no último ícone na barra de ferramentas, clique em **[!UICONTROL Include]** e selecione **[!UICONTROL Greetings]**.

     ![](assets/include-greetings.png)

     Navegue até a guia de visualização para verificar a personalização selecionando um recipient.

     ![](assets/perso-check.png)

     Saiba mais sobre opções de personalização em [esta seção](personalize.md).

   * Inserir um link rastreado

     Para levar os destinatários do delivery para um endereço externo por meio de uma imagem ou texto, selecione-o e clique no ícone **[!UICONTROL Add a link]** na barra de ferramentas.

     Insira a URL do link no campo **URL** usando o seguinte formato **https://www.myURL.com** e, em seguida, confirme.

     ![](assets/add-a-link.png)

   * Adicionar uma mirror page

     Para permitir que seus destinatários exibam o conteúdo da entrega em um navegador da Web, adicione um link à [mirror page](mirror-page.md) de sua mensagem.

     Coloque o cursor onde deseja inserir este link, clique no último ícone na barra de ferramentas, clique em **[!UICONTROL Include]** e selecione **[!UICONTROL link to mirror page]**.

     Saiba mais sobre como gerenciar a mirror page em [esta seção](mirror-page.md#link-to-mirror-page).

1. Você pode definir parâmetros adicionais para o email, como enviar uma cópia das mensagens para um endereço BBC, alterar o formato da mensagem, definir uma codificação específica etc. Saiba mais [nesta seção](email-parameters.md).

1. Quando o conteúdo estiver pronto, clique em **Salvar**: ele será exibido na lista de entregas, na guia **[!UICONTROL Campaigns > Deliveries]**.

Seu primeiro delivery de email está pronto. Agora é necessário definir o público-alvo, validar o delivery e enviá-lo.

Saiba como importar um conteúdo de email neste [caso de uso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html){target="_blank"}.

Saiba mais nas seguintes seções:

<!--[Design an email in Campaign]-->
* [Criar e usar um modelo de email](../send/create-templates.md)
* [Selecionar a audiência do seu email](../audiences/gs-audiences.md)
* [Validar um delivery e enviar provas](preview-and-proof.md)
* [Configurar e enviar a entrega](configure-and-send.md)

## Testar e validar seus emails

O Campaign oferece várias maneiras de testar e validar seus emails antes de enviá-los para seus públicos. Saiba como visualizar e testar seu conteúdo de email [nesta seção](../send/preview-and-proof.md).

Você pode:

* [Enviar provas](preview-and-proof.md)
* [Adicionar seed addresses](../audiences/test-profiles.md)
* [Verificar logs de análise de entrega](delivery-analysis.md)

