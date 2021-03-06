---
title: Gerenciar assinaturas e unsubscriptions no Campaign
description: Saiba mais sobre como gerenciar assinaturas e cancelamentos de assinaturas no Campaign v8
feature: Subscriptions
role: Data Engineer
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 35%

---

# Gerenciar assinaturas e unsubscriptions{#optin-optout}

Use o Adobe Campaign para criar e monitorar seus serviços de informações, como boletins informativos e gerenciar as assinaturas/unsubscriptions para esses serviços. Vários serviços podem ser definidos em paralelo, por exemplo: boletins informativos especializados para determinadas categorias de produtos, temas ou áreas de um site, subscrições a vários tipos de mensagens de alerta e notificações em tempo real. Consulte Gerenciar assinaturas.

![](../assets/do-not-localize/book.png) Saiba como criar um serviço de informações, enviar boletim informativo e gerenciar participação e não participação [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target=&quot;_blank&quot;}

Para assinar (aceitar) um perfil para um serviço, as opções disponíveis são:

* Adicionar manualmente o serviço ao perfil do recipient: para fazer isso, na **[!UICONTROL Subscriptions]** do perfil, clique em **[!UICONTROL Add]** e selecione o serviço de informação.

   ![](assets/subscribe-to-a-service.png)

   ![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}

* Subscrever automaticamente um conjunto de recipients ao serviço. A lista de recipients pode vir de uma operação de filtragem, grupo, pasta, importação ou seleção manual direta. Para inscrever esses recipients, selecione os perfis e clique com o botão direito do mouse. Selecione **[!UICONTROL Actions > Subscribe selection to a service...]**.

   ![](assets/subscribe-selection.png)

   Selecione o serviço desejado e inicie a operação.

   ![](assets/subscribe-confirm.png)

   ![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}


* Importar recipients e inscrevê-los automaticamente em um serviço de informação. Para fazer isso, selecione o serviço na última etapa do assistente de importação.

   ![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients){target=&quot;_blank&quot;}

* Usar um formulário da Web para que os recipients possam subscrever-se a um serviço.

   ![](assets/opt-in-webapp.png)

   O Campaign vem com um formulário da Web padrão para gerenciar a aceitação. Você pode personalizá-lo e mapear os dados do perfil.

   ![](assets/web-app.png)

   ![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in){target=&quot;_blank&quot;}


* Crie um workflow de direcionamento e use um **[!UICONTROL Subscription service]** atividade .

   ![](assets/wf-subscription.png)

   Saiba mais [nesta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/subscription-services.html).

Para cancelar a assinatura (recusa) de um perfil de um serviço, as opções disponíveis são:

**Cancelamento manual de subscrição**

* Link de cancelamento de subscrição personalizado ou formulário da Web
* Exclusão manual de um serviço de informação
* Exclusão manual de recipients de um serviço de assinatura específico

**Cancelamento automático de subscrição**

* Especifique um limite de duração do serviço de informação: os recipients serão cancelados automaticamente quando o período de validade expirar. Este período é especificado na guia Edit das propriedades do serviço. Ele é expresso em dias.
* Configure um workflow de unsubscription para uma população.

![](../assets/do-not-localize/book.png) Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service){target=&quot;_blank&quot;}


>[!CAUTION]
>
>No contexto de um [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), assinaturas e unsubscriptions são **assíncrono** processos. As solicitações de aceitação e recusa são processadas a cada hora. [Saiba mais](../architecture/new-apis.md#sub-apis)

Você também pode permitir que seus recipients de delivery encaminhem mensagens para um amigo. Para fazer isso, insira os links relevantes no seu delivery. Em seguida, você poderá controlar esse processo de compartilhamento, bem como o número de visitas às páginas relacionadas.

![](../assets/do-not-localize/book.png) Para obter mais informações sobre esse recurso, consulte [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend){target=&quot;_blank&quot;}
