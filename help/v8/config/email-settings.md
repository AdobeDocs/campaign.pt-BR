---
title: Configurações do canal de email do Campaign
description: Configurações do canal de email do Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 13%

---

# Configurações do canal de email do Campaign

## CCO de email {#email-bcc}

>[!NOTE]
>
>Esse recurso está disponível a partir do Campaign v8.3. Para verificar sua versão, consulte [esta seção](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

Você pode configurar o Adobe Campaign para manter uma cópia dos emails enviados da sua plataforma.

A Adobe Campaign em si não gerencia arquivos arquivados. Ele permite enviar as mensagens de sua escolha para um endereço de email CCO (cópia cega de carbono) dedicado, de onde podem ser processadas e arquivadas usando um sistema externo. Os arquivos .eml correspondentes aos emails enviados podem ser transferidos para um servidor remoto, como um servidor de email SMTP.

>[!CAUTION]
>
>Por motivos de privacidade, os emails CCO devem ser processados por um sistema de arquivamento capaz de armazenar informações de identificação pessoal (PII) seguras.

O destino de arquivamento é o endereço de email CCO de sua escolha, que permanecerá invisível para os recipients do delivery.

![](../assets/do-not-localize/speech.png)  Como um usuário do Managed Cloud Services, [Adobe de contato](../start/campaign-faq.md#support){target=&quot;_blank&quot;} para comunicar o endereço de email CCO a ser usado para arquivamento.

Depois que o endereço de email CCO for definido, você deverá ativar a opção dedicada no nível de delivery.

>[!CAUTION]
>
>Ao criar um novo delivery ou template do delivery, **[!UICONTROL Email BCC]** não está habilitado por padrão. Você precisa ativá-lo manualmente no delivery de email ou no template do delivery.


Para fazer isso, siga as etapas abaixo:

1. Ir para **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]** ou **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Selecione o delivery de sua escolha ou duplique os **[!UICONTROL Email delivery]** e, em seguida, selecione o modelo duplicado.
1. Clique no botão **[!UICONTROL Properties]**.
1. Selecione a guia **[!UICONTROL Delivery]**.
1. Marque a opção **[!UICONTROL Email BCC]**.

   ![](assets/email-bcc.png)

1. Selecione **[!UICONTROL Ok]**.

Uma cópia de todas as mensagens enviadas para cada delivery com base nesse template será enviada para o endereço Cco de email que foi configurado.

Observe as seguintes especificidades e recomendações:

* Você só pode usar um endereço de email CCO.

* Verifique se o endereço CCO tem capacidade de recepção suficiente para arquivar todos os emails enviados.

* Email Cco <!--with Enhanced MTA--> O entrega para o endereço de email CCO antes do delivery aos recipients, o que pode resultar no envio de mensagens CCO mesmo que os deliveries originais tenham retornado. Para obter mais informações sobre devoluções, consulte [Entender as falhas do delivery](../send/delivery-failures.md).

* Se os emails enviados para o endereço CCo forem abertos e clicados, isso será considerado no **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** da análise de envio, o que poderá causar alguns erros de cálculo.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Saiba mais na documentação do Campaign Classic v7**

* [Gerar a mirror page](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

* [Selecionar formato do email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

* [Selecionar codificação de caractere](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

* [Definir o endereço de email de devolução](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

* [Usar templates de delivery de email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=pt-BR){target=&quot;_blank&quot;}

* [Entender as falhas do delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
