---
product: Adobe Campaign
title: Configurações do canal de email do Campaign
description: Configurações do canal de email do Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 8%

---

# Configurações do canal de email do Campaign

## CCO de email

Você pode configurar o Adobe Campaign para manter uma cópia dos emails enviados da sua plataforma.

>[!NOTE]
>O recurso Cco de email é opcional. Verifique o contrato de licença.

A Adobe Campaign em si não gerencia arquivos arquivados. Ele permite enviar as mensagens de sua escolha para um endereço dedicado, de onde elas podem ser processadas e arquivadas usando um sistema externo.

Para fazer isso, os arquivos .eml correspondentes aos emails enviados são transferidos para um servidor remoto, como um servidor de email SMTP. O destino do arquivamento é um endereço de email CCO (invisível para os recipients do delivery) que você deve especificar.

Observe que:

* Você só pode usar **um** endereço de email CCO.

* Somente emails enviados com êxito são considerados, as rejeições não são.

?? Como um usuário do Managed Cloud Services, [entre em contato com o Adobe](../start/campaign-faq.md#support) para ativar o Email Cco no Campaign. O endereço de email CCO de sua escolha deve ser fornecido à equipe do Adobe que o configurará para você.

Depois que o Cco de email estiver configurado, verifique se o recurso está ativado no template do delivery ou no delivery por meio da opção **Email Cco**.

![](assets/email-bcc.png)


**Tópicos relacionados** na documentação do Campaign Classic v7:


↗️ [Gerar a mirror page](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

↗️ [Selecione o formato de email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

↗️ [Selecionar codificação de caractere](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

↗️ [Defina o endereço de email de devolução](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

↗️ [Use templates de delivery de email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=pt-BR){target=&quot;_blank&quot;}

↗️ [Entender falhas de delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
