---
title: Gerenciar solicitações de privacidade no Campaign
description: Saiba como gerenciar solicitações de privacidade no Campaign
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 0f81d318-dbfd-45c8-b391-b1d14d23e9c8
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: ht
source-wordcount: '1050'
ht-degree: 100%

---

# Gerenciar solicitações de privacidade no Campaign {#privacy}

<!--Adobe Campaign is a powerful tool for collecting and processing large volume of data, including personal information and sensitive data. It is therefore essential that you receive and monitor consent from your recipients.-->

>[!NOTE]
>
>Esse recurso está disponível a partir do Campaign v8.3. Para verificar sua versão, consulte [esta seção](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

Para facilitar a conformidade com a privacidade, o Adobe Campaign permite manipular solicitações de Acesso e Exclusão.

Para executar essas solicitações, é necessário usar a integração do **Privacy Core Service**. As solicitações de privacidade transmitidas pelo Privacy Core Service para todas as soluções da Experience Cloud são tratadas automaticamente pelo Campaign, por meio de um fluxo de trabalho específico. [Saiba mais](#create-privacy-request)

A Adobe oferece ferramentas aos controladores de dados para criar e processar solicitações de privacidade de dados armazenados no Campaign. No entanto, é sua responsabilidade, como controlador de dados, verificar a identidade do titular dos dados que faz a solicitação e confirmar que os dados retornados ao solicitante pertencem ao titular dos dados. Saiba mais sobre dados pessoais e as diferentes entidades que gerenciam dados na [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=pt-BR#personal-data){target=&quot;_blank&quot;}.

![](../assets/do-not-localize/speech.png) Saiba mais sobre **Direito de acesso** e **Direito ao esquecimento** (solicitação de exclusão) na [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=pt-BR#right-access-forgotten){target=&quot;_blank&quot;}.

## Definir um namespace {#namespaces}

Antes de criar uma solicitação de privacidade, é necessário **definir o namespace** que você usará. O namespace é a chave que será usada para identificar o Titular de dados no banco de dados do Adobe Campaign.

>[!NOTE]
>
>Para saber mais sobre namespaces de identidade, consulte a [documentação da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=pt-BR){target=&quot;_blank&quot;}.

Atualmente, o Adobe Campaign não oferece suporte à importação de namespaces do serviço de namespace de identidade da Experience Platform. Portanto, depois de criar um namespace no serviço de namespace de identidade, você deve criar manualmente o namespace correspondente na interface do Adobe Campaign. Para fazer isso, siga as etapas abaixo.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. Criar um namespace no [serviço de namespace de identidade](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace){target=&quot;_blank&quot;}.

1. Ao [listar os namespaces de identidade](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target=&quot;_blank&quot;} disponíveis para sua organização, você obterá o namespace seguido dos detalhes; por exemplo:

   ```
   {
           "updateTime": 1632903236731,
           "code": "lumanamespace",
           "status": "ACTIVE",
           "description": "new namespace for Luma privacy requests",
           "id": 10998717,
           "createTime": 1632903236731,
           "idType": "Email",
           "namespaceType": "Custom",
           "name": "Luma Namespace",
           "custom": true
   }
   ```

1. No Adobe Campaign, acesse **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]** e selecione **[!UICONTROL New]**.

   ![](assets/privacy-namespaces-new.png)

1. Insira um **[!UICONTROL Label]**.

1. Preencha os novos detalhes do namespace para corresponder ao que foi criado no serviço de namespace de identidade:

   * o **[!UICONTROL AEC Namespace ID]** deve corresponder ao atributo “id”;
   * o **[!UICONTROL Internal name]** deve corresponder ao atributo “code”;
   * o **[!UICONTROL Reconciliation key]** deve corresponder ao atributo “idType”.

   ![](assets/privacy-namespaces-details.png)

   O campo **[!UICONTROL Reconciliation key]** será usado para identificar o titular dos dados no banco de dados do Adobe Campaign.

1. Selecione um target mapping <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)--> para especificar como o namespace será reconciliado no Adobe Campaign.

   >[!NOTE]
   >
   >    Se quiser usar vários target mappings, crie um namespace para cada um deles.

1. Salve as alterações.

Agora você pode criar solicitações de privacidade com base em seu novo namespace. Se você usa vários namespaces, crie uma solicitação de privacidade por namespace para o mesmo valor de reconciliação.

## Criar uma solicitação de privacidade {#create-privacy-request}

A integração do **Privacy Core Service** permite automatizar suas solicitações de privacidade em um contexto com várias soluções por meio de uma única chamada de API JSON. O Adobe Campaign manipula automaticamente as solicitações enviadas pelo Privacy Core Service por meio de um fluxo de trabalho dedicado.

>[!CAUTION]
>
>Para que as solicitações de privacidade sejam processadas, você deve criar um namespace na instância do Adobe Campaign que corresponda ao que foi criado no serviço de namespace de identidade da Experience Platform.

Consulte a documentação do [Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=pt-BR){target=&quot;_blank&quot;} para saber como criar solicitações de privacidade pelo Privacy Core Service.

Cada tarefa do Privacy Core Service é dividida em várias solicitações de privacidade no Adobe Campaign, com base no número de namespaces utilizados, onde cada solicitação corresponde a um namespace.

Além disso, um trabalho pode ser executado em múltiplas instâncias. Portanto, vários arquivos são criados para uma tarefa. Por exemplo, se uma solicitação tiver dois namespaces e estiver em execução em três instâncias, então será enviado um total de seis arquivos. Um arquivo por namespace e instância.

O padrão para um nome de arquivo é: `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: nome da instância do Campaign
* **NamespaceId**: identificação de namespace do serviço de identidade do namespace utilizado
* **Chave de reconciliação**: chave de reconciliação criptografada

>[!CAUTION]
>
>Para enviar uma solicitação usando o tipo de namespace personalizado, utilize o [método JSON](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=pt-BR#json){target=&quot;_blank&quot;} e adicione o namespaceId à solicitação, ou use a [Chamada de API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html?lang=br#access-delete){target=&quot;_blank&quot;} para fazer a solicitação.
>
>Use somente a [Interface do usuário de privacidade](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=br#request-builder){target=&quot;_blank&quot;} para enviar solicitações usando o tipo de namespace padrão.

### Tabelas pesquisadas ao processar solicitações {#list-of-tables}

Ao executar uma solicitação de privacidade de exclusão ou acesso, o Adobe Campaign pesquisa todos os dados do Titular dos dados com base em **[!UICONTROL Reconciliation value]** em todas as tabelas que tenham um link para a tabela do recipient (tipo próprio). 

Esta é a lista de recursos prontos para utilização que são considerados ao executar solicitações de privacidade:

* Recipients (recipient)
* Log de delivery de recipient (broadLogRcp)
* Log de rastreamento de recipient (trackingLogRcp)
* Log de delivery de evento arquivado (broadLogEventHisto)
* Conteúdo da lista de recipient (rcpGrpRel)
* Apresentação da oferta do visitante (propositionVisitor)
* Visitantes (visitante)
* Histórico de inscrições (subHisto)
* Inscrições (inscrição)
* Apresentação da oferta do recipient (propositionRcp)

Se você criou tabelas personalizadas que tenham um link para a tabela do recipient (tipo próprio), elas também serão consideradas. Por exemplo, se você tiver uma tabela de transações vinculada à tabela do recipient e uma tabela de detalhes da transação vinculada à tabela de transações, ambas serão consideradas.
<!--
>[!CAUTION]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.-->

### Status de solicitação de privacidade {#privacy-request-statuses}

Estes são os diferentes status para solicitações de privacidade no Adobe Campaign:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: em andamento, o workflow ainda não processou a solicitação.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: o workflow está processando a solicitação.
* **[!UICONTROL Delete pending]**: o workflow identificou todos os dados do recipient que serão excluídos.
* **[!UICONTROL Delete in progress]**: workflow está processando a exclusão.
* **[!UICONTROL Complete]**: o processamento da solicitação foi concluído sem erros.
* **[!UICONTROL Error]**: o workflow encontrou um erro. O motivo é exibido na lista de solicitações de acesso a dados pessoais na coluna **[!UICONTROL Request status]**. Por exemplo, **[!UICONTROL Error data not found]** significa que nenhum dado de recipient correspondente ao **[!UICONTROL Reconciliation value]** do titular dos dados foi encontrado no banco de dados.

**Tópicos relacionados na documentação do Campaign Classic v7:**

* [Privacidade e consentimento](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=pt-BR){target=&quot;_blank&quot;}

* [Introdução ao gerenciamento de privacidade](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=pt-BR){target=&quot;_blank&quot;}

* [Regulamentos sobre gestão de privacidade](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=pt-BR#privacy-management-regulations){target=&quot;_blank&quot;} (GDPR, CCPA, PDPA e LGPD)

* [Opção de não participação na venda de informações pessoais](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html?lang=pt-BR){target=&quot;_blank&quot;} (específico da CCPA)