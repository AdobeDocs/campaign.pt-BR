---
title: Gerenciar assinaturas e cancelamentos de assinaturas no Campaign
description: Saiba mais sobre como gerenciar assinaturas e cancelamentos de assinaturas no Campaign v8.
feature: Subscriptions
role: User
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: b0150b38b50b04c08b10ed73b3be3064a09d7b88
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 33%

---

# Gerenciar assinaturas e cancelamentos de assinaturas{#optin-optout}

Use o Adobe Campaign para criar e monitorar seus serviços de informações, como boletins informativos, e gerenciar as assinaturas/cancelamentos de assinaturas desses serviços. Vários serviços podem ser definidos em paralelo, por exemplo: boletins informativos especializados para determinadas categorias de produtos, temas ou áreas de um site, subscrições a vários tipos de mensagens de alerta e notificações em tempo real.

![](../assets/do-not-localize/book.png) Saiba como criar um serviço de informação, enviar informativo e gerenciar a aceitação e a recusa no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target="_blank"}

Para assinar (aceitar) um perfil para um serviço, as opções disponíveis são:

* Adicionar manualmente o serviço ao perfil do recipient: para fazer isso, no **[!UICONTROL Subscriptions]** do perfil, clique em **[!UICONTROL Add]** e selecione o serviço de informação desejado.

  ![](assets/subscribe-to-a-service.png)

  ![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html#deliveries-tab){target="_blank"}

* Subscrever automaticamente um conjunto de recipients ao serviço. A lista de recipients pode vir de uma operação de filtragem, grupo, pasta, importação ou seleção manual direta. Para inscrever esses recipients, selecione os perfis e clique com o botão direito do mouse. Selecione **[!UICONTROL Actions > Subscribe selection to a service...]**.

  ![](assets/subscribe-selection.png)

  Selecione o serviço desejado e inicie a operação.

  ![](assets/subscribe-confirm.png)

  ![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html#deliveries-tab){target="_blank"}


* Importar recipients e inscrevê-los automaticamente em um serviço de informação. Para fazer isso, selecione o serviço na última etapa do assistente de importação.

  ![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html#step-5---additional-step-when-importing-recipients){target="_blank"}

* Usar um formulário da Web para que os recipients possam subscrever-se a um serviço.

  ![](assets/opt-in-webapp.png)

  O Campaign vem com um formulário web padrão para gerenciar a aceitação. Você pode personalizar e mapear os dados do perfil.

  ![](assets/web-app.png)

  ![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html#create-a-subscription--form-with-double-opt-in){target="_blank"}


* Criar um fluxo de trabalho de direcionamento e usar um **[!UICONTROL Subscription service]** atividade.

  ![](assets/wf-subscription.png)

  Saiba mais [nesta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/subscription-services.html).

Para cancelar a subscrição (recusa) de um perfil de um serviço, as opções disponíveis são:

**Cancelamento de assinatura manual**

* Link de cancelamento de subscrição ou formulário web personalizado
* Exclusão manual de um serviço de informação
* Exclusão manual de recipients de um serviço de assinatura específico

**Cancelamento automático de subscrição**

* Especifique um limite de duração do serviço de informação: a subscrição dos recipients será cancelada automaticamente quando o período de validade expirar. Este período é especificado na guia Edit das propriedades do serviço. Ele é expresso em dias.
* Configure um workflow de cancelamento de subscrição para uma população.

![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html#unsubscribing-a-recipient-from-a-service){target="_blank"}


>[!CAUTION]
>
>No contexto de um [Implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), assinaturas e unsubscriptions são **assíncrono** processos. As solicitações de aceitação e recusa são processadas a cada hora. [Saiba mais](../architecture/new-apis.md#sub-apis)

<!--
You can also enable your delivery recipients to forward messages to a friend. To do this, insert the relevant links into your delivery. You may then track this sharing process as well as the number of visits to the concerned pages. 

![](../assets/do-not-localize/book.png) For more on this capability, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html#viral-marketing--forward-to-a-friend){target="_blank"}
-->
