---
title: Relatórios globais do Adobe Campaign
description: Saiba como acessar e usar relatórios globais
feature: Reporting, Monitoring
exl-id: 6e3409d8-86bd-44ba-a40d-10287f53a960
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '1763'
ht-degree: 96%

---

# Relatórios globais {#global-reports}

Esses relatórios dizem respeito à atividade dos dados no banco de dados inteiro. Para exibir o painel de relatórios, vá para a guia **[!UICONTROL Reports]**.

![](assets/reports-tab.png)

Para exibir relatórios, clique em seus nomes. Os seguintes relatórios estão disponíveis por padrão:

![](assets/report-global-list.png)

>[!NOTE]
>
>Esta seção mostra apenas os relatórios vinculados aos deliveries.

* **[!UICONTROL Delivery throughput]**: consulte [Taxa de transferência de delivery](#delivery-throughput).
* **[!UICONTROL Browsers]** : consulte [Navegadores](#browsers).
* **[!UICONTROL Sharing to social networks]** : consulte [Compartilhamento em redes sociais](#sharing-to-social-networks).
* **[!UICONTROL Statistics on sharing activities]** : consulte [Estatísticas de atividades de compartilhamento](#statistics-on-sharing-activities).
* **[!UICONTROL Operating systems]**: consulte [Sistemas operacionais](#operating-systems).
* **[!UICONTROL URLs and click streams]**: consulte [URLs e fluxos de clique](delivery-reports.md#urls-and-click-streams).
* **[!UICONTROL Tracking indicators]** : consulte [Indicadores de rastreamento](delivery-reports.md#tracking-indicators).
* **[!UICONTROL Non-deliverables and bounces]** : consulte [Não entregues e devoluções](#non-deliverables-and-bounces).
* **[!UICONTROL User activities]** : consulte [Atividades do usuário](#user-activities).
* **[!UICONTROL Subscription tracking]** : consulte [Rastreamento de subscrição](#subscription-tracking).
* **[!UICONTROL Delivery summary]** : consulte [Resumo do delivery](delivery-reports.md#delivery-summary).
* **[!UICONTROL Delivery statistics]** : consulte [Estatísticas de delivery](#delivery-statistics).
* **[!UICONTROL Breakdown of opens]** : consulte [Detalhamento das aberturas](#breakdown-of-opens).

## Taxa de transferência de delivery {#delivery-throughput}

Este relatório contém informações sobre a taxa de transferência de delivery da plataforma inteira por um determinado período. Para medir a velocidade em que as mensagens são entregues, os critérios são o número de mensagens enviadas por hora e o tamanho das mensagens (em bits por segundo). No exemplo abaixo, o primeiro gráfico mostra as entregas bem-sucedidas em azul e o número de deliveires incorretos em laranja.

![](assets/report-toolbar.png)

Você pode configurar os valores exibidos alterando a escala de tempo: visualização de 1 hora, 3 horas, 24 horas, etc. Clique em **[!UICONTROL Refresh]** para confirmar a seleção.

>[!NOTE]
>
>Você também pode monitorar o número de deliveries enviados por hora usando o [Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/sftp-storage-management.html?lang=pt-BR).
>
>O Painel de controle é acessível a todos os usuários administradores. As etapas para conceder acesso de Administrador a um usuário estão detalhadas [nesta página](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=pt-BR#discover-control-panel).

## Atividades do usuário {#user-activities}

Este relatório mostra o detalhamento de aberturas, cliques e transações por meia hora, hora ou dia, no formato de um gráfico.

As seguintes opções estão disponíveis:

* **[!UICONTROL Opens]** : Número total de mensagens abertas. Os emails no formato de texto não são considerados. [Saiba mais](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clicks]** : Número total de cliques nos links nos deliveries. Cliques em links de unsubscription e mirror pages não são considerados.
<!--
* **[!UICONTROL Transactions]** : Total number of transactions after a message is received. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->

## Não entregues e devolvidos {#non-deliverables-and-bounces}

Este relatório mostra o detalhamento de não entregues, bem como uma análise de devoluções por domínio de Internet.

**[!UICONTROL Number of messages processed]** representa o número total de mensagens processadas pelo servidor de delivery. Esse valor é menor do que o número de mensagens a serem entregues quando alguns deliveries tiverem sido interrompidos ou pausados (antes de serem processados pelo servidor).

**[!UICONTROL Breakdown of errors by type]**

>[!NOTE]
>
>Os erros exibidos nesse relatório acionam o processo de quarentena. Para obter mais informações sobre a gestão de quarentena, consulte [Gestão de Quarentena](../send/quarantines.md).

A primeira seção desse relatório mostra o detalhamento de não entregues no formulário de uma tabela de valores e um gráfico.

Para cada tipo de erro, temos:

* o número de mensagens de erro desse tipo,
* a porcentagem de mensagens com erros desse tipo em comparação ao número total de mensagens com erros,
* a porcentagem de mensagens com erro desse tipo em comparação ao número total de mensagens processadas.

Os seguintes indicadores são usados:

* **[!UICONTROL User unknown]** : Tipo de erro gerado durante o delivery para indicar que o endereço de email é inválido.
* **[!UICONTROL Invalid domain]** : Tipo de erro gerado ao enviar um delivery para indicar que o domínio do endereço de email está errado ou não existe.
* **[!UICONTROL Inbox full]** : Tipo de erro gerado após cinco tentativas de delivery para indicar que a caixa de entrada dos recipients contém muitas mensagens.
* **[!UICONTROL Account disabled]** : Tipo de erro gerado ao enviar um delivery para indicar que o endereço não existe mais.
* **[!UICONTROL Rejected]** : Tipo de erro gerado quando um endereço é rejeitado pelo IAP (Provedor de Acesso à Internet), por exemplo, ao seguir uma regra de segurança da aplicação (software antispam).
* **[!UICONTROL Unreachable]** : Tipo de erro que ocorre na string de distribuição de mensagens: incidente na retransmissão SMTP, domínio temporariamente inacessível, etc
* **[!UICONTROL Not connected]** : Tipo de erro para indicar que o celular do recipient está desligado ou sem rede no momento do envio.

   >[!NOTE]
   >
   >Este indicador está relacionado aos deliveries no [canais móveis](../send/send.md) somente.

   Você pode abrir cada linha da tabela de valores clicando no símbolo `[+]`. Para cada tipo de erro, é possível exibir o detalhamento das mensagens de erro por domínio.

**[!UICONTROL Breakdown of errors per domain]**

A segunda seção desse relatório mostra o detalhamento de erros por domínio da Internet na forma de uma tabela de valores e um gráfico.

Para cada nome de domínio, temos:

* o número de mensagens com erros para esse domínio,
* a porcentagem de mensagens com erros para esse domínio em comparação ao número total de mensagens processadas para este domínio,
* a porcentagem de mensagens de erro para esse domínio em comparação ao número total de mensagens de erro.

Você pode abrir cada linha da tabela de valores clicando no símbolo [[+]]. Para cada tipo de domínio, é possível exibir o detalhamento das mensagens de erro por tipo de erro.

![](assets/errors-report-details.png)

>[!NOTE]
>
>Os nomes de domínio exibidos nesse relatório são definidos em nível de cubo. Para alterar esses valores, edite o cubo **[!UICONTROL Delivery logs (broadlogrcp)]**. Para obter mais informações, consulte [esta seção](gs-cubes.md). A categoria **[!UICONTROL Others]** inclui nomes de domínio que não pertencem a uma classe específica.

## Navegadores {#browsers}

Este relatório mostra o detalhamento dos navegadores da Internet usados pelos recipients do delivery para o período relacionado.

>[!NOTE]
>
>Os valores mostrados nesse relatório são estimativas: apenas recipients que clicaram em um delivery serão considerados.

**Estatísticas globais**

As estatísticas globais no uso do navegador são apresentadas na forma de uma tabela de valores e um gráfico.

![](assets/browser-report.png)

Os seguintes indicadores são usados:

* **[!UICONTROL Visitors]** : número total de recipients alvos (por navegador de Internet) e que clicaram em um delivery pelo menos uma vez.
* **[!UICONTROL Pages viewed]** : número total de cliques nos links em um delivery (por navegador de Internet) para todos os deliveries.
* **[!UICONTROL Usage rate]** : essa taxa representa o detalhamento dos visitantes (por navegador de Internet) em relação ao número total de visitantes.

**Estatísticas por navegador**

Na tabela de valores de estatística global, você pode clicar em cada nome de navegador para exibir suas estatísticas de uso.

![](assets/browser-report-info.png)

As estatísticas são apresentadas no formato de uma curva, um gráfico e uma tabela de valores.

A curva **[!UICONTROL History]** representa a taxa de participação deste navegador por dia. A taxa é a relação do número de visitantes por dia (nesse navegador) em comparação ao número de visitantes medidos no dia com a maior taxa de presença.

O gráfico **[!UICONTROL Breakdown per version]** representa o detalhamento dos visitantes por versão em comparação ao número total de visitantes (nesse navegador).

A tabela de valores usa os seguintes indicadores:

* **[!UICONTROL Global rate]**: essa taxa representa o detalhamento dos visitantes por versão em comparação ao número total de visitantes (em todos os navegadores).
* **[!UICONTROL Relative rate]**: essa taxa representa o detalhamento dos visitantes por versão em comparação ao número total de visitantes (nesse navegador).


<!--
### Sharing to social networks {#sharing-to-social-networks}

Viral marketing lets delivery recipients share information with their contact network: they can add a link to their profile (Facebook, Twitter, etc.) or send a message to a friend. Each share and each access to shared information is tracked within the delivery. For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

This report shows the breakdown of shared and opened messages per social network (Facebook, Twitter, etc.) and/or per email.

![](assets/s_ncs_user_social_report.png)

**[!UICONTROL Email delivery statistics]**

In the email delivery statistics, two values are displayed:

* **[!UICONTROL Number of messages to be delivered]** : Total number of messages processed during delivery analysis.
* **[!UICONTROL Number of successful deliveries]** : Number of messages processed successfully.

**[!UICONTROL Sharing activities and mail open statistics]**

The central table shows the statistics on email shares and opens.

In the **[!UICONTROL Shares]** column, we have the following indicators:

* **[!UICONTROL No. of sharing activities]** : Total number of messages shared on each social network. This value equals the total number of clicks on the icon of the matching **[!UICONTROL Links for sharing to social networks]** personalization block.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of shares per social network, in relation to the total number of shares.
* **[!UICONTROL Sharing rate]** : This rate represents the breakdown of shares per social network, in relation to the number of messages to be delivered.

In the **[!UICONTROL Opens]** column, we have the following indicators:

* **[!UICONTROL No. of opens]** : Total number of messages opened by people whom the message was forwarded to (via the **[!UICONTROL Links for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of opens per social network, in relation to the total number of opens.
* **[!UICONTROL Rate of opens]** : This rate represents the breakdown of opens per social network, in relation to the total number of shares.

**[!UICONTROL Breakdown of sharing activities and opens]**

This section includes two charts which represent the breakdown of sharing activities and opens per social network.


## Statistics on sharing activities {#statistics-on-sharing-activities}

This report shows the evolution of shares to social media in time.

For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

Statistics are presented in the form of a table of values and a chart.

The following indicators are used:

* **[!UICONTROL New contacts]** : Number of new subscriptions following the reception of a message shared via email. This value matches the number of people who received a message shared via email, clicked the **[!UICONTROL Subscription link]** and filled in the subscription form. 
* **[!UICONTROL Opens]** : Total number of messages opened by people whom the message was transferred to (via the **[!UICONTROL Link for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Sharing activities]** : Total number of messages shared via social networks. This value matches the total number of clicks on the icon of the **[!UICONTROL Links for sharing to social networks]** personalization block.
-->

## Sistemas operacionais {#operating-systems}

Este relatório exibe o detalhamento dos sistemas operacionais usados pelos recipients de delivery do período relacionado.

>[!NOTE]
>
>Os valores mostrados nesse relatório são estimativas: apenas recipients que clicaram em um delivery serão considerados.

**Estatísticas globais**

As estatísticas de uso global dos sistemas operacionais são apresentadas no formato de uma tabela de valores e um gráfico.

![](assets/os-report.png)

Os seguintes indicadores são usados:

* **[!UICONTROL Visitors]** : média diária do número total de recipients alvos (por sistema operacional) que clicaram em um delivery pelo menos uma vez.
* **[!UICONTROL Pages viewed]** : média diária do número total de cliques nos links de delivery (por sistema operacional) para todos os deliveries.
* **[!UICONTROL Rate of use]** : essa taxa representa o detalhamento dos visitantes (por sistema operacional) em relação ao número total de visitantes.

**Estatísticas por sistema operacional**

Na tabela de valores de estatística global, clique no nome de cada sistema operacional para exibir as estatísticas por sistema operacional.

![](assets/os-report-details.png)

As estatísticas são apresentadas no formato de uma curva, um gráfico e uma tabela de valores.

A curva **[!UICONTROL History]** representa a taxa de uso deste sistema operacional por dia. Essa taxa é a relação do número de visitantes por dia (neste sistema operacional) em relação ao número de visitantes medidos no dia com a maior participação.

O gráfico **[!UICONTROL Breakdown by version]** representa o detalhamento dos visitantes por versão em relação ao número total de visitantes neste sistema operacional.

A tabela de valores usa os seguintes indicadores:

* **[!UICONTROL Global rate]** : essa taxa representa o detalhamento dos visitantes (por versão) em relação ao número total de visitantes em todos os sistemas operacionais.
* **[!UICONTROL Relative rate]** : essa taxa representa o detalhamento dos visitantes (por versão) em relação ao número total de visitantes desse sistema operacional.

## Rastreamento de assinatura {#subscription-tracking}

Este relatório permite monitorar subscrições de serviços de informação. Ele mostra subscrições e unsubscriptions.

![](assets/service-report.png)

Ele pode ser exibido para uma subscrição clicando no nó **[!UICONTROL Profiles and targets > Services and subscriptions]** da home page ou do navegador. Selecione a subscrição desejada e depois clique na guia **[!UICONTROL Reports]**. O relatório **[!UICONTROL Subscriptions tracking]** está disponível por padrão. Ele permite ver as tendências de subscrição e unsubscription e a taxa de fidelidade por um período. Você pode configurar a representação desses dados pela lista suspensa. Clique em **[!UICONTROL Refresh]** para validar a configuração selecionada.

Para obter mais informações, consulte [esta página](../start/subscriptions.md).

**[!UICONTROL Number subscribed to date]** representa o número total de pessoas subscritas atualmente.

**[!UICONTROL Overall evolution of subscriptions]**

A tabela de valores usa os seguintes indicadores:

* **[!UICONTROL Subscribers]**: número total de assinantes do período relacionado.
* **[!UICONTROL Subscriptions]**: número de subscrições do período relacionado.
* **[!UICONTROL Unsubscriptions]**: número de cancelamentos de subscrições do período relacionado.
* **[!UICONTROL Evolution]**: número de cancelamentos de subscrições menos o número de subscrições. A taxa é calculada com base no número total de assinantes.
* **[!UICONTROL Loyalty]**: taxa de fidelidade de assinantes do período relacionado.

**[!UICONTROL Subscription evolution curves]**

Este gráfico mostra a evolução das assinaturas e dos cancelamentos de assinaturas no período relacionado.

## Estatísticas de entrega {#delivery-statistics}

Este relatório mostra o detalhamento por domínio de Internet, de todas as mensagens processadas e enviadas, de devoluções permanentes e temporárias, aberturas, cliques e unsubscriptions.

![](assets/broadcast-report.png)

Os seguintes indicadores são usados:

* **[!UICONTROL Emails processed]**: número total de mensagens processadas pelo servidor de delivery.
* **[!UICONTROL Delivered]**: porcentagem do número de mensagens processadas com êxito em comparação ao número total de mensagens processadas.
* **[!UICONTROL Hard bounces]**: porcentagem do número de devoluções permanentes em comparação ao número total de mensagens processadas.
* **[!UICONTROL Soft bounces]**: porcentagem do número de devoluções temporárias em comparação ao número total de mensagens processadas.

   >[!NOTE]
   >
   >Para obter mais informações sobre devoluções permanentes e temporárias, consulte [esta página](../send/quarantines.md).

* **[!UICONTROL Opens]**: porcentagem do número de recipients alvos que abriram uma mensagem pelo menos uma vez em comparação ao número de mensagens processadas com êxito.
* **[!UICONTROL Clicks]**: porcentagem do número de pessoas que clicaram em um delivery pelo menos uma vez em comparação ao número de mensagens processadas com êxito.
* **[!UICONTROL Unsubscription]**: porcentagem do número de cliques em um link de cancelamento de subscrição em comparação ao número de mensagens processadas com êxito.

## Detalhamento de aberturas {#breakdown-of-opens}

Este relatório mostra o detalhamento de aberturas por sistema operacional, dispositivo e navegador para o período relacionado. Para cada categoria, dois gráficos são usados. O primeiro exibe estatísticas referentes a aberturas em um computador e dispositivos móveis. O segundo exibe estatísticas relacionadas apenas a aberturas em dispositivos móveis.

O número de aberturas corresponde ao número total de mensagens abertas. Os emails em formato de texto não são contados. Para obter mais informações sobre rastreamento de aberturas, consulte [nesta seção](metrics-calculation.md#tracking-opens-).

![](assets/user-agent-report.png)

>[!NOTE]
>
>Os nomes do navegador e do sistema operacional fazem parte das informações enviadas pelo agente do usuário do navegador em que a mensagem foi aberta. O Adobe Campaign deduz o tipo de dispositivo usando as informações do dispositivo.
