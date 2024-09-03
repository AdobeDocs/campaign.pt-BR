---
title: SMS define o conteúdo
description: Saiba como configurar o conteúdo de uma entrega de SMS
feature: SMS
role: User
level: Beginner, Intermediate
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 33%

---


# Conteúdo de SMS {#sms-content}

Para configurar o conteúdo do delivery de SMS:

1. Insira o conteúdo da sua mensagem no assistente do **[!UICONTROL Text content]**

   ![](assets/sms_content.png){zoomable="yes"}

1. Você pode personalizar a mensagem inserindo campos de personalização (por exemplo, adicionando o nome) ou inserindo um bloco de personalização predefinido (por exemplo, adicionando saudações). Você pode clicar no botão de personalização para adicionar estes:

   ![](assets/sms_perso.png){zoomable="yes"}

   Depois de clicar em **[!UICONTROL Recipient]** > **[!UICONTROL First name]**, você terá a personalização como esta:

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

1. Você pode visualizar sua entrega acessando a guia **[!UICONTROL Preview]** e clicando na lista suspensa **[!UICONTROL Test personalization]** e escolhendo um destinatário na tabela **[!UICONTROL Recipient]**.

   ![](assets/sms_preview.png){zoomable="yes"}

   Você terá a pré-visualização do SMS com a personalização:

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* As mensagens SMS são limitadas a um comprimento de 160 caracteres, se a página de código Latin-1 (ISO-8859-1) for usada. Se a mensagem for gravada em Unicode, não deverá exceder 70 caracteres. Alguns caracteres especiais podem afetar o comprimento da mensagem. Para obter mais informações sobre comprimento de mensagem, consulte a seção [Transliteração de caracteres SMS](smpp-external-account.md#smpp-channel-settings).
>
>* Quando campos de personalização ou campos de conteúdo condicional estão presentes, o tamanho da mensagem varia de um destinatário para outro. O comprimento da mensagem deve ser avaliado quando a personalização for realizada.
>
>*Quando você inicia a análise, o comprimento das mensagens é verificado e um aviso é exibido no caso de excedente.

Depois de criar o conteúdo da sua entrega, você pode [selecionar seu público-alvo](sms-audience.md).