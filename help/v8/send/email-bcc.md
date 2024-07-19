---
title: Enviar uma cópia de suas mensagens para um endereço CCo
description: Saiba como ativar o email Cco no Adobe Campaign
feature: Email
role: User
level: Beginner
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# Enviar uma cópia de suas mensagens para um endereço CCo {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## Sobre email Cco {#gs-bcc}

Você pode configurar o Adobe Campaign para manter uma cópia dos emails enviados da sua plataforma. Essa opção permite enviar mensagens para um endereço de email CCO dedicado (Cópia oculta), de onde elas podem ser processadas e arquivadas usando um sistema externo.
O próprio Adobe Campaign não gerencia arquivos arquivados. Os arquivos .eml correspondentes aos emails enviados podem ser transferidos para um servidor remoto, como um servidor de email SMTP.

O destino do arquivamento é o endereço de email CCO de sua escolha, que permanecerá invisível para os recipients do delivery. Depois que o endereço de email de CCO for definido, você deverá habilitar a opção dedicada no nível do [modelo de entrega](create-templates.md).

>[!NOTE]
>
>Como usuário do Managed Cloud Service, [contate o Adobe](../start/campaign-faq.md#support){target="_blank"} para informar o endereço de email CCO a ser usado para arquivamento.

>[!CAUTION]
>
>Por motivos de privacidade, os emails com CCO devem ser processados por um sistema de arquivamento capaz de armazenar informações de identificação pessoal (PII) seguras.


## Habilitar email Cco {#enable-bcc}

Para habilitar o CCO para um [modelo de entrega](create-templates.md) específico, siga as etapas abaixo:

1. No explorador do Campaign, navegue até a pasta de templates do delivery. Por padrão, os modelos de entrega são armazenados na pasta **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Edite o template do delivery a ser atualizado com Cco.
1. Clique no botão **[!UICONTROL Properties]**.
1. Na guia **[!UICONTROL Delivery]**, marque a opção **[!UICONTROL Email BCC]**.

   ![](assets/email-bcc.png)

1. Clique em **[!UICONTROL Ok]** para confirmar.

Uma cópia de todas as mensagens enviadas para cada delivery com base nesse modelo será enviada para o endereço Cco de email que foi configurado para sua plataforma.

## Medidas de proteção e recomendações {#recommendations-bcc}

Ao usar o Cco de email com o Adobe Campaign, as seguintes medidas de proteção e recomendações se aplicam:

* Você só pode usar um endereço de email CCO.

* Verifique se o endereço CCo tem capacidade de recepção suficiente para arquivar todos os emails enviados.

* A Cco de email <!--with Enhanced MTA--> é entregue ao endereço de email de CCO antes de ser entregue aos destinatários, o que pode resultar no envio de mensagens de CCO, mesmo que as entregas originais possam ter sido rejeitadas. Para obter mais informações sobre rejeições, consulte [Entender as falhas de entrega](delivery-failures.md).

* Emails enviados para o endereço CCo não devem ser abertos nem clicados, pois essas atividades são consideradas no **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** da análise de envio, o que pode causar erros de cálculo.

<!--Only successfully sent emails are taken in account, bounces are not.-->
