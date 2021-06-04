---
product: Adobe Campaign
title: Trabalhar com o Campaign e o Adobe Analytics
description: Saiba como integrar o Campaign e o Analytics
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 6a22bdd563bb0be26df12ce8d2b6da266d16f2e3
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 31%

---

# Trabalhar com o Campaign e o Adobe Analytics

Você pode configurar o Adobe Analytics para integrar o Campaign e o Analytics.

Essa integração permite que o Adobe Campaign e o Adobe Analytics interajam por meio do complemento **Web Analytics connectors**. Essa integração envia indicadores e atributos de campanhas de email entregues pelo Adobe Campaign para a Adobe Analytics.

[!DNL :speech_balloon:] Como usuário do Managed Cloud Services,  [entre em contato com a ](../start/campaign-faq.md#support) Adobe para conectar o Campaign com os serviços e as soluções da Adobe Experience Cloud. O Adobe Identity Management Service (IMS) deve ser implementado para sua instância. [Saiba mais](../start/connect.md#connect-ims). O complemento do conector do Web Analytics deve ser instalado no ambiente, por meio do pacote dedicado.

Usando o Adobe Analytics Connector, o Adobe Campaign tem uma maneira de medir o público-alvo da Internet (Web Analytics). As ferramentas de análise da Web permitem que o Adobe Campaign encaminhe indicadores e atributos de campanha para o Analytics.

O perímetro de ação de cada ferramenta é o seguinte:

* **O Adobe** Analytics marca as campanhas de email iniciadas com o Adobe Campaign

* **O Adobe** Campaign envia os indicadores e os atributos da campanha para o conector, que, por sua vez, os encaminha para a ferramenta Web Analytics


>[!CAUTION]
>
>O Adobe Analytics Connector não é compatível com as mensagens transacionais (Centro de Mensagens).

Para configurar a conexão do Campaign com o Analytics, você deve executar as seguintes operações:

1. [Criar seu conjunto de relatórios no Adobe Analytics](#report-suite-analytics)
1. [Configurar as variáveis de conversão e os eventos bem-sucedidos](#configure-conversion-success)
1. [Configurar sua conta externa no Adobe Campaign](#external-account-ac)

## Crie seu conjunto de relatórios do Analytics {#report-suite-analytics}

Para criar seu **[!UICONTROL Report suite]** em [!DNL Adobe Analytics], siga as etapas abaixo:

1. Em [!DNL Adobe Analytics], selecione o **[!UICONTROL Admin tab]** e clique em **[!UICONTROL All admin]**.

   ![](assets/analytics_connnector_1.png)

1. Clique em **[!UICONTROL Report suites]**.

   ![](assets/analytics_connnector_2.png)

1. Na página **[!UICONTROL Report suite manager]** , clique em **[!UICONTROL Create new]** e em **[!UICONTROL Report suite]**.

   Para obter o procedimento detalhado sobre a criação de **[!UICONTROL Report suite]**, consulte esta [seção](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/t-create-a-report-suite.html?lang=en#prerequisites).

   ![](assets/analytics_connnector_3.png)

1. Selecione um modelo.

1. Configure seu novo conjunto de relatórios com as seguintes informações:

   * **[!UICONTROL Report Suite ID]**
   * **[!UICONTROL Site Title]**
   * **[!UICONTROL Time Zone]**
   * **[!UICONTROL Go Live Date]**
   * **[!UICONTROL Estimated Page Views Per Day]**

   ![](assets/analytics_connnector_4.png)

1. Quando configurado, clique em **[!UICONTROL Create report suite]**.

## Configurar as variáveis de conversão e os eventos bem-sucedidos {#configure-conversion-success}

Depois de criar seu **[!UICONTROL Report suite]**, você precisa configurar seus **[!UICONTROL Conversion variables]** e **[!UICONTROL Success events]** da seguinte maneira:

1. Selecione o **[!UICONTROL Report suite]** configurado anteriormente.

1. No botão **[!UICONTROL Edit settings]**, selecione **[!UICONTROL Conversion]** > **[!UICONTROL Conversion variables]**.

   ![](assets/analytics_connnector_5.png)

1. Clique em **[!UICONTROL Add new]** para criar os identificadores necessários para medir o impacto da campanha de email, ou seja, o nome da campanha interna (cid) e a ID da tabela iNmsBroadlog (bid).

   Para saber como editar **[!UICONTROL Conversion variables]**, consulte esta [seção](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/t-conversion-variables-admin.html?lang=en#admin-tools).

   ![](assets/analytics_connnector_6.png)

1. Clique em **[!UICONTROL Save]** quando terminar.

1. Em seguida, para criar seu **[!UICONTROL Success events]**, selecione **[!UICONTROL Conversion]** > **[!UICONTROL Success events]** no botão **[!UICONTROL Edit settings]**.

   ![](assets/analytics_connnector_7.png)

1. Clique em **[!UICONTROL Add new]** para configurar o seguinte **[!UICONTROL Success events]**:

   * **[!UICONTROL Clicked]**
   * **[!UICONTROL Opened]**
   * **[!UICONTROL Person clicks]**
   * **[!UICONTROL Processed]**
   * **[!UICONTROL Scheduled]**
   * **[!UICONTROL Sent]**
   * **[!UICONTROL Total bounces]**
   * **[!UICONTROL Unique Clicks]**
   * **[!UICONTROL Unique Opens]**
   * **[!UICONTROL Unsubscribed]**

   Para saber como configurar **[!UICONTROL Success events]**, consulte esta [seção](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/t-success-events.html?lang=en#admin-tools)

   ![](assets/analytics_connnector_8.png)

1. Clique em **[!UICONTROL Save]** quando terminar.

Quando seu conjunto de relatórios é configurado, é necessário configurar o **[!UICONTROL External accounts]** no Adobe Campaign.

## Configurar a conta externa do Campaign {#external-account-ac}

Agora é necessário configurar sua conta externa **[!UICONTROL Web Analytics]** no Adobe Campaign para habilitar a sincronização entre as duas soluções.

Observe que se um de seus **[!UICONTROL Report suite]**, **[!UICONTROL Conversion variables]** ou **[!UICONTROL Success events]** não estiver visível ao configurar sua conta externa, isso significa que você não tem uma permissão para esse componente recém-criado no **[!UICONTROL Product profile]** associado ao usuário.

Para obter mais informações, consulte a página [Product profiles for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=en#product-profile-admins) .

1. Vá para a pasta **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External accounts]** da árvore do Adobe Campaign e clique em **[!UICONTROL New]**.

   ![](assets/analytics_connnector_9.png)

1. Use a lista suspensa para selecionar o tipo **[!UICONTROL Web Analytics]** e **[!UICONTROL Adobe Analytics]** no menu suspenso **[!UICONTROL Integration]**.

   ![](assets/analytics_connnector_10.png)

1. Clique em **[!UICONTROL Configure]** ao lado do menu suspenso **[!UICONTROL Integration]**.

1. Na janela **[!UICONTROL Configure Analytics integration]**, mapeie sua conta externa com seu conjunto de relatórios criado anteriormente fornecendo as seguintes informações:

   * **[!UICONTROL E-Mail]**
   * **[!UICONTROL IMS Org]**
   * **[!UICONTROL Analytics Company]**
   * **[!UICONTROL Report Suite]**


1. Na categoria **[!UICONTROL eVars]**, mapeie os dois **[!UICONTROL Conversion variables]** configurados em [!DNL Adobe Analytics].

   ![](assets/analytics_connnector_11.png)

1. Na categoria **[!UICONTROL Events]** , mapeie os dez **[!UICONTROL Success events]** configurados em [!DNL Adobe Analytics].

1. Clique em **[!UICONTROL Submit]** quando terminar. O Adobe Campaign criará **[!UICONTROL Data source]**, **[!UICONTROL Calculated metrics]**, **[!UICONTROL Remarketing segments]** e **[!UICONTROL Classifications]** no Analytics mapeado **[!UICONTROL Report Suite]**.

   Quando essa sincronização entre [!DNL Adobe Analytics] e o Adobe Campaign estiver concluída, você poderá fechar a janela.

1. As configurações podem ser exibidas na guia **[!UICONTROL Data Settings]** da janela **[!UICONTROL Configure Analytics integration]**.

   Usando o botão **[!UICONTROL Sync]**, [!DNL Adobe Campaign] sincronizará as alterações de nome feitas em [!DNL Adobe Analytics]. Se o componente for excluído em [!DNL Adobe Analytics], o componente será tachado em [!DNL Adobe Campaign] ou exibido com uma mensagem **não encontrada**.

   ![](assets/analytics_connnector_12.png)

   >[!NOTE]
   >
   > Não é possível adicionar ou remover segmentos nesta versão do Campaign v8.

1. Em **[!UICONTROL External account]**, clique no link **[!UICONTROL Enrich the formula...]** para alterar a fórmula de cálculo da URL para especificar as informações de integração da ferramenta Web Analytics (IDs da campanha) e os domínios dos sites cuja atividade deve ser rastreada.

   ![](assets/analytics_connnector_13.png)

1. Especifique o(s) nome(s) de domínio dos sites.

   ![](assets/analytics_connnector_14.png)

1. Clique em **[!UICONTROL Next]** e verifique se os nomes de domínio foram salvos.

   ![](assets/analytics_connnector_15.png)

1. Se necessário, é possível sobrecarregar a fórmula de cálculo. Para fazer isso, marque a caixa e edite a fórmula diretamente na janela.

   >[!IMPORTANT]
   >
   >Esse modo de configuração é reservado para usuários especialistas: qualquer erro nessa fórmula pode resultar na interrupção dos deliveries de email.

1. A guia **[!UICONTROL Advanced]** permite configurar ou modificar mais configurações técnicas.

   * **[!UICONTROL Lifespan]**: permite especificar o atraso (em dias_ após os eventos da Web recuperados no Adobe Campaign por workflows técnicos. Padrão: 180 dias.
   * **[!UICONTROL Persistence]**: permite o período durante o qual todos os eventos da Web (uma compra, por exemplo) podem ser atribuídos a uma campanha de re-marketing. Padrão: 7 dias.

>[!NOTE]
>
>Se estiver usando várias ferramentas de medição de público, você pode selecionar **[!UICONTROL Other]** na lista suspensa **[!UICONTROL Partners]** ao criar a conta externa. Você só pode fazer referência a uma conta externa nas propriedades de delivery: será necessário adaptar a fórmula de URLs controladas adicionando os parâmetros esperados pela Adobe e todas as outras ferramentas de medição usadas.

## Fluxo de trabalho técnico dos processos de análise da Web {#technical-workflows-of-web-analytics-processes}

A troca de dados entre o Adobe Campaign e o Adobe Analytics é realizada por um workflow técnico que é executado como uma tarefa em segundo plano.

Esse workflow está disponível na árvore do Campaign Explorer, na pasta **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** > **[!UICONTROL Web analytics process]**.

![](assets/webanalytics_workflows.png)

O workflow **[!UICONTROL Sending of indicators and campaign attributes]** permite enviar indicadores de campanha de email via Adobe Campaign para a Adobe Experience Cloud usando o Adobe Analytics Connector. Esse workflow é acionado às 4:00 AM todos os dias e pode levar 24 horas para que os dados sejam enviados ao Analytics.

Observe que esse workflow não deve ser reiniciado ou todos os dados anteriores podem distorcer os resultados do Analytics.

Os indicadores envolvidos são:

* **[!UICONTROL Messages to deliver]** (@toDeliver)
* **[!UICONTROL Processed]** (@processed)
* **[!UICONTROL Success]** (@success)
* **[!UICONTROL Total count of opens]** (@totalRecipientOpen)
* **[!UICONTROL Recipients who have opened]** (@recipientOpen)
* **[!UICONTROL Total number of recipients who clicked]** (@totalRecipientClick)
* **[!UICONTROL People who clicked]** (@personClick)
* **[!UICONTROL Number of distinct clicks]** (@recipientClick)
* **[!UICONTROL Opt-Out]** (@optOut)
* **[!UICONTROL Errors]** (@error)

>[!NOTE]
>
>Os dados enviados são o delta baseado no último instantâneo que pode levar ao valor negativo nos dados de métrica.

Os atributos enviados são os seguintes:

* **[!UICONTROL Internal name]** (@internalName)
* **[!UICONTROL Label]** (@label)
* **[!UICONTROL Label]**(operation/@label): somente se o pacote do **Campaign** estiver instalado
* **[!UICONTROL Nature]**(operation/@nature): somente se o pacote do **Campaign** estiver instalado
* **[!UICONTROL Tag 1]** (webAnalytics/@tag1)
* **[!UICONTROL Tag 2]** (webAnalytics/@tag2)
* **[!UICONTROL Tag 3]** (webAnalytics/@tag3)
* **[!UICONTROL Contact date]** (scheduling/@contactDate)

## Rastrear deliveries {#tracking-deliveries-in-adobe-campaign}

Para que a Adobe Experience Cloud possa rastrear a atividade nos sites, depois que o Adobe Campaign enviou o delivery, é necessário fazer referência ao conector correspondente nas propriedades de delivery. Para fazer isso, siga as etapas abaixo:

1. Abra o delivery da campanha a ser rastreado.

   ![](assets/webanalytics_delivery_properties_003.png)

1. Abra as propriedades de delivery.
1. Acesse a guia **[!UICONTROL Web Analytics]** e selecione a conta externa criada anteriormente. Consulte [Configurar a conta externa no Adobe Campaign](#external-account-ac).

   ![](assets/webanalytics_delivery_properties_002.png)

1. Agora você pode enviar o delivery e acessar o relatório no Adobe Analytics.


**Tópicos relacionados**

* [Campaign - Integração com Experience Cloud Triggers](ac-triggers.md)
