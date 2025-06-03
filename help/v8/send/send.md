---
title: Enviar e monitorar emails
description: Saiba mais sobre o escopo e as especificidades do envio de emails com o Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 26%

---


# Enviar e monitorar emails  {#send-and-monitor-emails}

Quando o delivery estiver configurado e pronto para ser enviado, certifique-se de executar a análise do delivery. [Saiba mais](delivery-analysis.md)

Depois de concluído, confirme o delivery para iniciar o delivery de mensagens.

Rastreie a execução da entrega a partir da guia **Entrega**, acessível por meio do detalhe desta entrega ou pela lista de entregas.

## Monitorar emails {#email-monitoring}

Depois de enviado, verifique seu status de entrega no **Painel de Entrega** e acesse os logs e relatórios de entrega para confirmar se as mensagens foram enviadas corretamente.

No painel de delivery, é possível verificar as mensagens processadas e os logs de auditoria do delivery. Você também pode controlar o status das mensagens nos logs do delivery.

>[!NOTE]
>
>Os status da entrega não são exibidos em tempo real. Saiba mais sobre o Serviço de Comentários por Email [nesta seção](#email-feedback-service).


[Saiba mais sobre o monitoramento de entrega na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}

## MTA da campanha {#mta}

O Mail Transfer Agent (MTA) do Campaign v8 fornece a melhor infraestrutura de envio do setor, permitindo entrega, reputação, taxa de transferência, relatórios, tratamento de rejeição, aumento do IP e gerenciamento da configuração de conexão ideais.

Disponível para todos os clientes do Campaign v8, garante escalabilidade, alta taxa de transferência de delivery e ajuda a enviar mais emails mais rapidamente. Isso é feito com novas técnicas de entrega adaptáveis que alteram as configurações de envio de email em tempo real, com base no feedback dos Provedores de serviço da Internet.

### Benefícios

O Adobe Campaign usa um Mail Transfer Agent (MTA) que executa o MTA de email comercial do SparkPost chamado **Momentum**.

O Momentum representa uma tecnologia MTA inovadora e de alto desempenho, que inclui um tratamento mais inteligente de rejeição e um recurso automatizado de otimização de entrega que ajuda os remetentes a alcançar e manter as taxas ideais de delivery da caixa de entrada.

* O MTA permite um aumento maciço na velocidade geral de taxa de transferência e uma redução significativa em rejeições temporárias.
* Ele usa a mais recente tecnologia MTA para fornecer a você as velocidades de taxa de transferência ideais para seu delivery de email.
* Adaptando-se instantânea e automaticamente ao feedback que recebe, ele também garante uma entrega de email mais preciso e inteligente com dados de entrega em tempo real.

### Qualificação de rejeição

Para mensagens de erro de falha de entrega **síncrona**, o MTA determina o tipo de rejeição e a qualificação e envia essas informações para o Campaign.

O MTA qualifica a rejeição de SMTP e envia essa qualificação de volta ao Campaign no formato de um código de rejeição mapeado para um motivo de rejeição e qualificação do Campaign.

>[!NOTE]
>
>Atualmente, **as rejeições assíncronas** são qualificadas pelo processo do InMail por meio das **[!UICONTROL Inbound email]** regras.

Saiba mais sobre falhas de entrega em [esta seção](delivery-failures.md).


### Regras MX específicas

As regras MX (Mail eXchanger) são as regras que gerenciam a comunicação entre um servidor de envio e um servidor de recebimento.

O MTA tem suas próprias regras de MX, que permitem personalizar a taxa de transferência por domínio com base na sua própria reputação histórica de email e no feedback em tempo real proveniente dos domínios em que você está enviando emails.

### Assinatura DKIM

O Domain Keys Identified Mail (DKIM) é um método de autenticação usado para detectar endereços de remetente forjados (geralmente chamado de falsificação).

No Adobe Campaign, a assinatura de autenticação de email do DKIM é executada pelo MTA.

Saiba mais sobre o DKIM no [Manual de práticas recomendadas de capacidade de delivery do Adobe](https://experienceleague.adobe.com/pt-br/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure#authentication){target="_blank"}.

## Serviço de feedback por email {#email-feedback-service}

O EFS (Campaign Email Feedback Service, Serviço de feedback por email) relata o status de cada delivery de email enviado com o Adobe Campaign.

Depois que a entrega é iniciada, não há alteração na porcentagem de **[!UICONTROL Success]** quando a mensagem é transmitida com êxito do Campaign para o MTA. Os logs da entrega mostram o status **[!UICONTROL Taken into account by the service provider]** para cada endereço direcionado.

Quando a mensagem é realmente entregue aos perfis direcionados e uma vez que essas informações são relatadas em tempo real do MTA, os logs de entrega mostram o status **[!UICONTROL Sent]** para cada endereço que recebeu a mensagem com êxito. A porcentagem de **[!UICONTROL Success]** aumenta de acordo com cada entrega bem-sucedida.

Quando mensagens com rejeição permanente são relatadas do MTA, o status do log muda de **[!UICONTROL Taken into account by the service provider]** para **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Quando mensagens com rejeição temporária são relatadas do MTA, o status do log permanece inalterado (**[!UICONTROL Taken into account by the service provider]**): somente o [motivo do erro](delivery-failures.md#delivery-failure-reasons) é atualizado<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. A porcentagem de **[!UICONTROL Success]** permanece inalterada. As mensagens com rejeição temporária são então repetidas durante todo o [período de validade da entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}

* Se uma nova tentativa for bem-sucedida antes do fim do período de validade, o status da mensagem mudará para **[!UICONTROL Sent]** e a porcentagem **[!UICONTROL Success]** será aumentada de maneira apropriada.

* Caso contrário, o status mudará para **[!UICONTROL Failed]**. A porcentagem de **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->permanece inalterada.

>[!NOTE]
>
>Para obter mais informações sobre rejeições permanentes e temporárias, consulte [esta seção](delivery-failures.md#delivery-failure-reasons).
>
>Para obter mais informações sobre tentativas após uma falha temporária de entrega, consulte [esta seção](delivery-failures.md#retries).

A tabela abaixo mostra como os KPIs e os status dos logs de envio são atualizados em cada etapa do processo de envio.

| Etapa do processo de envio | Resumo do KPI | Envio de status de logs |
|--- |--- |--- |
| A mensagem foi transmitida com êxito do Campaign para o MTA | A porcentagem de **[!UICONTROL Success]** não é exibida (começa em 0%) | Levado em consideração pelo provedor de serviço |
| Mensagens com rejeição permanente são relatadas de volta do MTA | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Com falha |
| Mensagens com rejeição temporária são relatadas de volta do MTA | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Levado em consideração pelo provedor de serviço |
| Tentativas de mensagens com rejeição temporária são bem-sucedidas | A porcentagem de **[!UICONTROL Success]** é aumentada de maneira apropriada | Enviada |
| Falha nas tentativas de mensagens com rejeição temporária | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Com falha |
