---
solution: Campaign
product: Adobe Campaign
title: Configurações do canal de email do Campaign
description: Configurações do canal de email do Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 4%

---

# Configurações do canal de email do Campaign

## CCO de email

Você pode configurar o Adobe Campaign para manter uma cópia dos emails enviados da sua plataforma.

No entanto, o Adobe Campaign em si não gerencia arquivos arquivados. Ele permite enviar as mensagens de sua escolha para um endereço dedicado, de onde elas podem ser processadas e arquivadas usando um sistema externo.

Para fazer isso, os arquivos .eml correspondentes aos emails enviados são transferidos para um servidor remoto, como um servidor de email SMTP. O destino do arquivamento é um endereço de email CCO (invisível para os recipients do delivery) que você deve especificar.

Observe que:

* Você só pode usar um endereço de email CCO.

* Somente emails enviados com êxito são considerados, as rejeições não são.

Depois que o Cco de email estiver configurado, verifique se o recurso está ativado no template do delivery ou no delivery por meio da opção **Email Cco**.

:seta_upper_right: Para obter mais informações, consulte a [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=en#email-bcc)

**Observação**: O recurso Cco de email é opcional. Verifique o contrato de licença.

:voice_balloon: Como um usuário do Managed Cloud Services, [entre em contato com o Adobe](../start/support.md#support) para ativar o Email Cco no Campaign. O endereço de email CCO de sua escolha deve ser fornecido à equipe do Adobe que o configurará para você.