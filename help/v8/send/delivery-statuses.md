---
title: Status de entrega
description: Saiba mais sobre os status disponíveis no painel da entrega
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 69%

---

# Status de entrega {#delivery-statuses}

Depois que uma entrega é enviada, o painel da entrega exibe um status que permite monitorar se o envio foi bem sucedido. Os possíveis status estão detalhados na seção abaixo.

![](assets/delivery-status.png)

Para obter mais detalhes sobre as diferentes falhas de entrega que podem ser encontradas e como resolvê-las, consulte [Noções básicas sobre falhas de entrega](delivery-failures.md).

**Tópicos relacionados:**

* [Enviar e monitorar emails](send.md)
* [Entender as falhas de entrega](delivery-failures.md)
* [Introdução à capacidade de entrega](about-deliverability.md)

## Lista de status de entrega {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> Status<br /> </th> 
   <th> Definições e soluções<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Sent<br /> </td> 
   <td> A entrega foi enviada corretamente ao provedor de mensagens (mas o destinatário não a recebeu necessariamente).<br /> </td> 
  </tr> 
  <tr> 
   <td> Ignorado<br /> </td> 
   <td> A entrega não foi enviada ao destinatário devido a um erro no endereço. Ele foi incluído na lista de bloqueios, colocado em quarentena, não fornecido ou duplicado. <br /> </td> 
  </tr> 
  <tr> 
   <td> Failed<br /> </td> 
   <td> A entrega não conseguiu alcançar o destinatário devido a um endereço inválido ou a uma caixa de entrada cheia, por exemplo. Também pode ser um problema com blocos de personalização, pois esses blocos podem gerar erros quando os esquemas não correspondem ao mapeamento da entrega. Consulte <a href="delivery-failures.md" target="_blank">Conhecendo as falhas de entrega</a><br /> </td> 
  </tr>
  <tr> 
   <td> Pending<br /> </td> 
   <td> A entrega está pronta para ser enviada e será processada pelo servidor de entrega (MTA). Consulte <a href="#pending-status" target="_blank">Status pendente</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Not applicable<br /> </td> 
   <td> A entrega foi levada em conta pelo servidor (MTA), mas não foi processada.<br /> </td> 
  </tr>  
  <tr> 
   <td> Delivery canceled<br /> </td> 
   <td> A entrega foi cancelada por um operador.<br /> </td> 
  </tr> 
  <tr> 
   <td> Levado em consideração pelo provedor de serviço<br /> </td> 
   <td> Para deliveries de SMS, o provedor de serviço SMS recebeu o delivery.<br /> Para entregas de email, a mensagem foi repassada com êxito do Campaign para o MTA (Agente de Transferência de Correspondência).</td> 
  </tr> 
  <tr> 
   <td> Received on mobile<br /> </td> 
   <td> O destinatário recebeu o SMS em seu dispositivo móvel.<br /> </td> 
  </tr>
  <tr> 
   <td> Sent to the service provider<br /> </td> 
   <td> A entrega foi enviada para o provedor de serviços SMS, mas ainda não foi recebida.<br />
   </td> 
  </tr> 
  <tr> 
   <td> Prepared<br /> </td> 
   <td> Status intermediário usado somente para conectores externos como o canal móvel. Ele segue o status "Pendente" e é o conector externo que determinará o status seguinte.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Para saber como otimizar a capacidade de entrega dos emails do Adobe Campaign, consulte [esta seção](about-deliverability.md). Para obter informações mais detalhadas sobre a capacidade de entrega, consulte o [Manual de práticas recomendadas de capacidade de entrega da Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR).

## Status pendente {#pending-status}

Após confirmar a entrega, você pode ver que o status da entrega é **[!UICONTROL Pending]**. Esse status significa que o processo de execução está aguardando a disponibilidade de alguns recursos.

O status **[!UICONTROL Pending]** pode significar que a sua entrega foi agendada e está pendente até a data especificada. Para obter mais informações, consulte a seção [Agendar envio de entrega](configure-and-send.md#schedule-delivery-sending).

Se a entrega não estiver sendo enviada e o status permanecer **[!UICONTROL Pending]**, poderá ser devido a:

* **Muitas campanhas em execução simultaneamente**

  O limite de campanhas simultâneas é definido na opção **[!UICONTROL NmsOperation_LimitConcurrency]**. O valor padrão é 10.

  Como usuário do Managed Cloud Services, você pode trabalhar com a Adobe para ajustar esse limite, se necessário. Saiba mais sobre opções na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html?lang=pt-BR){target="_blank"}.

* **Problemas de disponibilidade de recursos**

  O MTA (Message Transfer Agent) pode estar aguardando a disponibilização de recursos antes de processar o delivery.

>[!NOTE]
>
>Como usuário do Campaign v8 Managed Cloud Services, a infraestrutura do MTA é monitorada e gerenciada pela Adobe. Se você tiver problemas persistentes com entregas pendentes, entre em contato com o Atendimento ao cliente da Adobe.

**Tópicos relacionados:**

* [Enviar e monitorar emails](send.md#email-monitoring)
* [Entender as falhas de entrega](delivery-failures.md)
* [Monitorar o ambiente do Campaign](../start/monitor.md#monitor-deliveries)

