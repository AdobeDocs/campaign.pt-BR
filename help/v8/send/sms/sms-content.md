---
title: Definir e personalizar o conteúdo do SMS
description: Saiba como definir e personalizar o conteúdo de uma entrega de SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
TQID: https://experienceleague.adobe.com/N4C8Rkg-Kl-82FCZAvJ12KofuRObW170ySJaCHgW5wM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 254
ht-degree: 31%

---

# Definir o conteúdo do SMS {#sms-content}

Para configurar o conteúdo do delivery de SMS:

1. Insira o conteúdo da mensagem na guia **[!UICONTROL Text content]**.

   ![](assets/sms_content.png){zoomable="yes"}

1. Você pode personalizar a mensagem inserindo campos de personalização (por exemplo, adicionando o nome) ou inserindo um bloco de personalização predefinido (por exemplo, adicionando saudações). Clique no botão de personalização para adicionar estes:

   ![](assets/sms_perso.png){zoomable="yes"}

   Por exemplo, depois de clicar em **[!UICONTROL Recipient]** > **[!UICONTROL First name]**, o conteúdo do SMS é atualizado com o campo de personalização, conforme abaixo:

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

   Saiba mais sobre a personalização no Adobe Campaign em [esta seção](../personalize.md).

1. Você pode visualizar o conteúdo da entrega na guia **[!UICONTROL Preview]**. Para verificar suas configurações de personalização, clique na lista suspensa **[!UICONTROL Test personalization]** e selecione um recipient.

   ![](assets/sms_preview.png){zoomable="yes"}

   Você pode verificar a pré-visualização do SMS com a personalização:

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* As mensagens SMS são limitadas a um comprimento de 160 caracteres, se a página de código Latin-1 (ISO-8859-1) for usada. Se a mensagem for gravada em Unicode, não deverá exceder 70 caracteres. Alguns caracteres especiais podem afetar o comprimento da mensagem. Para obter mais informações sobre comprimento de mensagem, consulte a seção [Transliteração de caracteres SMS](smpp-external-account.md#smpp-channel-settings).
>
>* Quando campos de personalização ou campos de conteúdo condicional estão presentes, o tamanho da mensagem varia de um destinatário para outro. O comprimento da mensagem deve ser avaliado quando a personalização for realizada.
>
>*Quando você inicia a análise, o comprimento das mensagens é verificado e um aviso é exibido no caso de excedente.

Depois de criar o conteúdo da sua entrega, você pode [selecionar seu público-alvo](sms-audience.md).
