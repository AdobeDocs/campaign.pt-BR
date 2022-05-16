---
title: Configurações do canal de email do Campaign
description: Configurações do canal de email do Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '289'
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

* Você só pode usar **one** Endereço de email CCO.

* Somente emails enviados com êxito são considerados, as rejeições não são.

![](../assets/do-not-localize/speech.png)  Como um usuário do Managed Cloud Services, [Adobe de contato](../start/campaign-faq.md#support) para ativar Email Cco no Campaign. O endereço de email CCO de sua escolha deve ser fornecido à equipe do Adobe que o configurará para você.

Depois que o CCO de email estiver configurado, verifique se o recurso está ativado no template do delivery ou no delivery por meio da **Email Cco** opção.

![](assets/email-bcc.png)


**Tópicos relacionados** na documentação do Campaign Classic v7:


* [Gerar a mirror page](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

* [Selecionar formato do email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

* [Selecionar codificação de caractere](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

* [Definir o endereço de email de devolução](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

* [Usar templates de delivery de email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=pt-BR){target=&quot;_blank&quot;}

* [Entender as falhas do delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
