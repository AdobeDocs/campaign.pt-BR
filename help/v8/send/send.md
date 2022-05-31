---
title: Enviar e monitorar seus emails
description: Saiba mais sobre o escopo e as especificidades do envio de emails com o Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 9fa6666532a6943c438268d7ea832f0908588208
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 31%

---


# Enviar e monitorar seus emails

Depois que o delivery estiver configurado e pronto para ser enviado, certifique-se de executar a análise do delivery.

![](../assets/do-not-localize/book.png) [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#confirming-delivery){target=&quot;_blank&quot;}

Depois de concluído, confirme o delivery para iniciar o delivery de mensagens.

Você também pode:

* agende o delivery para mais tarde usando [a opção adiar o delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#scheduling-the-delivery-sending){target=&quot;_blank&quot;},
* envie para vários lotes usando [várias ondas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target=&quot;_blank&quot;}.

Rastrear a execução do delivery a partir do **Delivery** , acessível por meio do detalhe deste delivery ou pela lista de deliveries.

## Monitorar emails

Depois de enviado, verifique o status do delivery no Painel de delivery e acesse os logs do delivery e os relatórios para confirmar se as mensagens foram enviadas corretamente.

![](../assets/do-not-localize/book.png) [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target=&quot;_blank&quot;}


## MTA da campanha {#mta}

O Campaign v8 Mail Transfer Agent (MTA) fornece a melhor infraestrutura de envio do setor, permitindo o deliverability, reputação, throughput, relatórios, manipulação de devolução, aumento de IP e gerenciamento de configuração de conexão ideais.

Disponível para todos os clientes do Campaign v8, ele garante escalabilidade, uma alta taxa de transferência de delivery e ajuda a enviar mais emails mais rapidamente. Isso é feito com novas técnicas de delivery adaptáveis que alteram as configurações de envio de email em tempo real, com base no feedback dos Provedores de serviço da Internet.

### Benefícios

O Adobe Campaign usa um Agente de transferência de email (MTA) que executa o MTA de email comercial do SparkPost chamado **Momento**.

O Momentum representa uma tecnologia MTA inovadora e de alto desempenho, que inclui um tratamento mais inteligente de rejeição e um recurso automatizado de otimização de entrega que ajuda os remetentes a alcançarem e manterem as taxas ideais de delivery da caixa de entrada.

* O MTA permite um aumento maciço na velocidade geral do throughput e uma redução significativa das devoluções temporárias.
* Ele usa a tecnologia MTA mais recente para fornecer a você as velocidades de throughput ideais para a entrega de email.
* Adaptando-se instantânea e automaticamente ao feedback que recebe, ele também garante um delivery de email mais preciso e inteligente com dados de delivery em tempo real.

### Qualificação de rejeição

Para **síncrono** mensagens de erro de falha de delivery, o MTA determina o tipo de devolução e a qualificação e envia essas informações para o Campaign.

O MTA qualifica a rejeição SMTP e envia essa qualificação de volta ao Campaign no formato de um código de rejeição mapeado para um motivo de rejeição e qualificação de campanha.

>[!NOTE]
>
>Atualmente **assíncrono** as rejeições são qualificadas pelo processo inMail por meio do **[!UICONTROL Inbound email]** regras. Para obter mais informações, consulte [Documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

Saiba mais sobre falhas de delivery em [esta seção](delivery-failures.md).


### Regras MX específicas

As regras MX (Mail eXchanger) são as regras que gerenciam a comunicação entre um servidor de envio e um servidor de recebimento.

O MTA tem suas próprias regras MX que permitem personalizar a taxa de transferência por domínio com base em sua própria reputação histórica de email e no feedback em tempo real proveniente dos domínios em que você está enviando emails.

### Assinatura DKIM

O Domain Keys Identified Mail (DKIM) é um método de autenticação usado para detectar endereços de remetente falsificados (comumente chamados de falsificação).

No Adobe Campaign, a assinatura de autenticação de email do DKIM é executada pelo MTA.

Saiba mais sobre o DKIM no [Guia de práticas recomendadas de capacidade de entrega do Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=pt-BR#authentication){target=&quot;_blank&quot;}.

## Serviço de feedback por email {#email-feedback-service}

Com o recurso EFS (Serviço de feedback de email), o status de cada email é relatado com precisão, pois o feedback é capturado diretamente do MTA.

Depois que o delivery for iniciado, não haverá alterações no **[!UICONTROL Success]** porcentagem quando a mensagem é retransmitida com êxito do Campaign para o MTA.

Os logs do delivery mostram o status **[!UICONTROL Taken into account by the service provider]** para cada endereço direcionado.

Quando a mensagem é realmente entregue aos perfis segmentados e, uma vez que essas informações são relatadas em tempo real do MTA, os logs do delivery mostram a variável **[!UICONTROL Sent]** status para cada endereço que recebeu a mensagem com êxito. A porcentagem de **[!UICONTROL Success]** aumenta de acordo com cada delivery bem-sucedido.

Quando mensagens de rejeição permanente são relatadas pelo MTA, o status do log muda de **[!UICONTROL Taken into account by the service provider]** para **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Quando mensagens de rejeição temporária são relatadas novamente pelo MTA, o status do log permanece inalterado (**[!UICONTROL Taken into account by the service provider]**): somente a variável [motivo do erro](delivery-failures.md#delivery-failure-reasons) é atualizado<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. A porcentagem de **[!UICONTROL Success]** permanece inalterada. Mensagens de rejeição automática são repetidas em todo o delivery [período de validade](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

* Se uma nova tentativa for bem-sucedida antes do fim do período de validade, o status da mensagem mudará para **[!UICONTROL Sent]** e a porcentagem **[!UICONTROL Success]** será aumentada de maneira apropriada.

* Caso contrário, o status mudará para **[!UICONTROL Failed]**. A porcentagem de **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->permanece inalterada.

>[!NOTE]
>
>Para obter mais informações sobre rejeições permanentes e temporárias, consulte [esta seção](delivery-failures.md#delivery-failure-reasons).
>
>Para obter mais informações sobre tentativas após uma falha temporária de delivery, consulte [esta seção](delivery-failures.md#retries).

A tabela abaixo mostra como os KPIs e os status de logs de envio são atualizados em cada etapa do processo de envio com o recurso EFS.

| Etapa do processo de envio | Resumo do KPI | Envio de status de logs |
|--- |--- |--- |
| A mensagem é retransmitida com êxito do Campaign para o MTA | A porcentagem de **[!UICONTROL Success]** não é exibida (começa em 0%) | Levado em consideração pelo provedor de serviço |
| Mensagens de rejeição permanente são relatadas no MTA | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Com falha |
| Mensagens de rejeição temporária são relatadas no MTA | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Levado em consideração pelo provedor de serviço |
| Tentativas de mensagens com rejeição temporária são bem-sucedidas | A porcentagem de **[!UICONTROL Success]** é aumentada de maneira apropriada | Enviada |
| Falha nas tentativas de mensagens com rejeição temporária | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Com falha |
