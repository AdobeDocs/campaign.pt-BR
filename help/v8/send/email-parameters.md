---
title: Parâmetros de email no Adobe Campaign
description: Saiba mais sobre as opções e configurações específicas do delivery de email no Adobe Campaign.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 63%

---

# Parâmetros de email {#email-parameters}

Esta seção apresenta as opções e os parâmetros disponíveis nas propriedades de delivery específicas para delivery de email.

## Usar Email Cco {#email-bcc}

Você pode configurar o Adobe Campaign para manter uma cópia dos emails enviados da sua plataforma. Esta opção está detalhada em [esta página](email-bcc.md).

## Selecionar formatos de mensagem {#selecting-message-formats}

Você pode alterar o formato das mensagens de email enviadas. Para fazer isso, edite as propriedades da entrega e clique na guia **[!UICONTROL Delivery]**.

![](assets/email-message-format.png)

Selecione o formato do email na seção inferior da janela:

* **[!UICONTROL Use recipient preferences]** (modo padrão)

  O formato da mensagem é definido de acordo com os dados armazenados no perfil do destinatário e armazenado por padrão no campo **[!UICONTROL email format]** (@emailFormat). Se um destinatário deseja receber mensagens em determinado formato, esse será o formato enviado. Se o campo não estiver preenchido, uma mensagem multipart-alternative será enviada (veja abaixo).

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  A mensagem contém os dois formatos: texto e HTML. O formato exibido no recebimento depende da configuração do software de email do destinatário (multipart-alternative).

  >[!IMPORTANT]
  >
  >Essa opção inclui ambas as versões do documento. Portanto, reduz a taxa de transferência do delivery, pois o tamanho da mensagem é maior.

* **[!UICONTROL Send all messages in text format]**

  A mensagem é enviada em formato de texto. O formato HTML não será enviado, mas usado somente para a mirror page quando o destinatário clicar na mensagem.

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## Definir codificação de caracteres {#character-encoding}

Na guia **[!UICONTROL SMTP]** dos parâmetros da entrega, a seção **[!UICONTROL Character encoding]** permite definir uma codificação específica.

A codificação padrão é UTF-8. Se alguns dos provedores de email de seus destinatários não oferecerem suporte à codificação padrão UTF-8, você pode definir uma codificação específica para exibir corretamente os caracteres especiais aos destinatários dos seus emails.

Por exemplo, você deseja enviar um email contendo caracteres japoneses. Para garantir que todos os caracteres sejam exibidos corretamente para seus destinatários no Japão, é possível usar uma codificação que ofereça suporte aos caracteres japoneses em vez do padrão UTF-8.

Para fazer isso, selecione a opção **[!UICONTROL Force the encoding used for messages]** na seção **[!UICONTROL Character encoding]** e escolha uma codificação na lista suspensa que é exibida.

![](assets/email-smtp-encoding.png)

## Gerenciar emails rejeitados {#managing-bounce-emails}

A guia **[!UICONTROL SMTP]** das propriedades de entrega também permite configurar a gestão de emails devolvidos.

* **[!UICONTROL Errors-to-address]**: por padrão, os emails devolvidos são recebidos na caixa de erro padrão da plataforma, mas você pode definir um endereço de erro específico para uma entrega.

* **[!UICONTROL Bounce address]**: você também pode definir outro endereço para o qual os emails devolvidos não processados são encaminhados. Esse endereço permite investigar os motivos para a rejeição quando os emails não puderam ser qualificados automaticamente pelo aplicativo.

Cada um desses campos pode ser personalizado usando o ícone dedicado. Saiba mais sobre campos de personalização em [esta seção](personalization-fields.md).

![](assets/email-smtp-bounce.png)

Para obter mais informações sobre gerenciamento de rejeição de emails, consulte [esta seção](delivery-failures.md#bounce-mail-management).

## Adicionar cabeçalhos SMTP {#adding-smtp-headers}

É possível adicionar cabeçalhos SMTP às entregas Para fazer isso, use a seção relevante da guia **[!UICONTROL SMTP]** na entrega.

O script inserido nessa janela deve referenciar um cabeçalho por linha no seguinte formulário: **name:value**.

Os valores são codificados automaticamente se necessário.

>[!IMPORTANT]
>
>Adicionar um script para inserir cabeçalhos SMTP adicionais é apenas para usuários avançados.
>
>A sintaxe desse script deve estar em conformidade com os requisitos desse tipo de conteúdo: não há espaço não utilizado, nenhuma linha vazia, etc.

![](assets/email-smtp-headers.png)


## Gerar mirror page {#generating-mirror-page}

A mirror page é uma página HTML acessível online através de um navegador da Web. Seu conteúdo é idêntico ao email. Pode ser útil se seus recipients estiverem enfrentando problemas de renderização ou imagens com falha ao tentar exibir seu email na caixa de entrada.

Saiba como inserir um link para a mirror page em [esta seção](mirror-page.md)
