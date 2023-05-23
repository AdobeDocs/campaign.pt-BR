---
title: Enviar e monitorar emails
description: Saiba mais sobre o escopo e as especificidades do envio de emails com o Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 33%

---


# Enviar e monitorar emails

Depois que o delivery estiver configurado e pronto para ser enviado, certifique-se de executar a análise do delivery. [Saiba mais](delivery-analysis.md)

Depois de concluído, confirme o delivery para iniciar o delivery de mensagens.

Rastrear a execução da entrega a partir de **Entrega** , acessível por meio do detalhe deste delivery ou pela lista de deliveries.

## Monitorar emails

Depois de enviado, verifique o status do delivery no Painel do delivery e acesse os logs e relatórios do delivery para confirmar se as mensagens foram enviadas corretamente.

![](../assets/do-not-localize/book.png) [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}


## MTA da campanha {#mta}

O Mail Transfer Agent (MTA) do Campaign v8 fornece a melhor infraestrutura de envio do setor, permitindo entrega, reputação, taxa de transferência, relatórios, tratamento de rejeição, aumento do IP e gerenciamento da configuração de conexão ideais.

Disponível para todos os clientes do Campaign v8, garante escalabilidade, alta taxa de transferência de delivery e ajuda a enviar mais emails mais rapidamente. Isso é feito com novas técnicas de delivery adaptáveis que alteram as configurações de envio de email em tempo real, com base no feedback dos Provedores de serviço da Internet.

### Benefícios

O Adobe Campaign usa um Mail Transfer Agent (MTA) que executa o MTA de email comercial do SparkPost chamado **Momento**.

O Momentum representa uma tecnologia MTA inovadora e de alto desempenho, que inclui um tratamento mais inteligente de rejeição e um recurso automatizado de otimização de entrega que ajuda os remetentes a alcançarem e manterem as taxas ideais de delivery da caixa de entrada.

* O MTA permite um grande aumento na velocidade geral de taxa de transferência e uma redução significativa nas rejeições temporárias.
* Ele usa a mais recente tecnologia MTA para fornecer a você as velocidades de taxa de transferência ideais para seu delivery de email.
* Adaptando-se instantânea e automaticamente ao feedback que recebe, ele também garante um delivery de email mais preciso e inteligente com dados de delivery em tempo real.

### Qualificação de rejeição

Para **síncrono** mensagens de erro de falha de delivery, o MTA determina o tipo de rejeição e a qualificação e envia essas informações para o Campaign.

O MTA qualifica a rejeição de SMTP e envia essa qualificação de volta ao Campaign no formato de um código de rejeição mapeado para um motivo de rejeição e qualificação do Campaign.

>[!NOTE]
>
>Atualmente **assíncrono** As rejeições são qualificadas pelo processo inMail por meio da **[!UICONTROL Inbound email]** regras.

Saiba mais sobre falhas de delivery em [nesta seção](delivery-failures.md).


### Regras MX específicas

As regras MX (Mail eXchanger) são as regras que gerenciam a comunicação entre um servidor de envio e um servidor de recebimento.

O MTA tem suas próprias regras de MX, que permitem personalizar a taxa de transferência por domínio com base na sua própria reputação histórica de email e no feedback em tempo real proveniente dos domínios em que você está enviando emails.

### Assinatura DKIM

O DKIM (Domain Keys Identified Mail) é um método de autenticação usado para detectar endereços de remetente falsificados (geralmente chamado de falsificação).

No Adobe Campaign, a assinatura de autenticação de email do DKIM é executada pelo MTA.

Saiba mais sobre o DKIM no [Guia de práticas recomendadas de capacidade de delivery do Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=pt-BR#authentication){target="_blank"}.

## Serviço de feedback por email {#email-feedback-service}

Com o recurso Serviço de feedback por email (EFS), o status de cada email é relatado com precisão, pois o feedback é capturado diretamente do MTA.

Depois que o delivery é iniciado, não há alteração no **[!UICONTROL Success]** porcentagem quando a mensagem é transmitida com êxito do Campaign para o MTA.

Os logs do delivery mostram o status **[!UICONTROL Taken into account by the service provider]** para cada endereço direcionado.

Quando a mensagem é realmente entregue aos perfis direcionados e uma vez que essas informações são relatadas em tempo real do MTA, os logs do delivery mostram as **[!UICONTROL Sent]** status para cada endereço que recebeu a mensagem com êxito. A porcentagem de **[!UICONTROL Success]** aumenta de acordo com cada delivery bem-sucedido.

Quando mensagens com rejeição permanente são relatadas do MTA, o status do log muda de **[!UICONTROL Taken into account by the service provider]** para **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Quando mensagens com rejeição temporária são relatadas do MTA, o status do log permanece inalterado (**[!UICONTROL Taken into account by the service provider]**): somente o [motivo do erro](delivery-failures.md#delivery-failure-reasons) está atualizado<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. A porcentagem de **[!UICONTROL Success]** permanece inalterada. As mensagens com rejeição temporária são então repetidas durante todo o delivery [período de validade](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}:

* Se uma nova tentativa for bem-sucedida antes do fim do período de validade, o status da mensagem mudará para **[!UICONTROL Sent]** e a porcentagem **[!UICONTROL Success]** será aumentada de maneira apropriada.

* Caso contrário, o status mudará para **[!UICONTROL Failed]**. A porcentagem de **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->permanece inalterada.

>[!NOTE]
>
>Para obter mais informações sobre rejeições permanentes e temporárias, consulte [esta seção](delivery-failures.md#delivery-failure-reasons).
>
>Para obter mais informações sobre tentativas após uma falha temporária de delivery, consulte [esta seção](delivery-failures.md#retries).

A tabela abaixo mostra como os KPIs e os status dos logs de envio são atualizados em cada etapa do processo de envio com o recurso EFS.

| Etapa do processo de envio | Resumo do KPI | Envio de status de logs |
|--- |--- |--- |
| A mensagem foi transmitida com êxito do Campaign para o MTA | A porcentagem de **[!UICONTROL Success]** não é exibida (começa em 0%) | Levado em consideração pelo provedor de serviço |
| Mensagens com rejeição permanente são relatadas de volta do MTA | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Com falha |
| Mensagens com rejeição temporária são relatadas de volta do MTA | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Levado em consideração pelo provedor de serviço |
| Tentativas de mensagens com rejeição temporária são bem-sucedidas | A porcentagem de **[!UICONTROL Success]** é aumentada de maneira apropriada | Enviada |
| Falha nas tentativas de mensagens com rejeição temporária | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Com falha |
