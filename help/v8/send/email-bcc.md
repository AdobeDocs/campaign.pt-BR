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

O destino do arquivamento é o endereço de email CCO de sua escolha, que permanecerá invisível para os recipients do delivery. Depois que o endereço de email de CCO for definido, você deverá ativar a opção dedicada no [template do delivery](create-templates.md) nível.

>[!NOTE]
>
>Como usuário do Managed Cloud Service, [Adobe de contato](../start/campaign-faq.md#support){target="_blank"} para comunicar o endereço de email CCO que será usado para arquivamento.

>[!CAUTION]
>
>Por motivos de privacidade, os emails com CCO devem ser processados por um sistema de arquivamento capaz de armazenar informações de identificação pessoal (PII) seguras.


## Habilitar email Cco {#enable-bcc}

Para ativar o CCO para um [template do delivery](create-templates.md), siga as etapas abaixo:

1. No explorador do Campaign, navegue até a pasta de templates do delivery. Por padrão, os templates do delivery são armazenados no **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** pasta.
1. Edite o template do delivery a ser atualizado com Cco.
1. Clique no botão **[!UICONTROL Properties]**.
1. No **[!UICONTROL Delivery]** , marque a **[!UICONTROL Email BCC]** opção.

   ![](assets/email-bcc.png)

1. Clique em **[!UICONTROL Ok]** para confirmar.

Uma cópia de todas as mensagens enviadas para cada delivery com base nesse modelo será enviada para o endereço Cco de email que foi configurado para sua plataforma.

## Medidas de proteção e recomendações {#recommendations-bcc}

Ao usar o Cco de email com o Adobe Campaign, as seguintes medidas de proteção e recomendações se aplicam:

* Você só pode usar um endereço de email CCO.

* Verifique se o endereço CCo tem capacidade de recepção suficiente para arquivar todos os emails enviados.

* Email Cco <!--with Enhanced MTA--> O envia para o endereço de email CCO antes de entregar aos recipients, o que pode resultar no envio de mensagens com CCO, mesmo que os deliveries originais possam ter sido rejeitados. Para obter mais informações sobre rejeições, consulte [Entender as falhas de delivery](delivery-failures.md).

* Emails enviados para o endereço CCo não devem ser abertos nem clicados, pois essas atividades são consideradas no **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** na análise de envio, pode causar erros de cálculo.

<!--Only successfully sent emails are taken in account, bounces are not.-->
