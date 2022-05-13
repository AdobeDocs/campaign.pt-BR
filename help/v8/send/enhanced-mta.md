---
title: Enviar com o MTA aprimorado no Adobe Campaign
description: Saiba mais sobre o escopo e as especificidades do envio de emails com o MTA aprimorado do Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
source-git-commit: 448436d56d14dca2d18088ebfc94f9e21ebb58c4
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 69%

---

# Enviar com o MTA aprimorado {#sending-with-enhanced-mta}

O **MTA aprimorado do Adobe Campaign** O (Mail Transfer Agent) fornece uma infraestrutura de envio atualizada que permite o melhor delivery, reputação, throughput, relatórios, manipulação de devolução, aumento de IP e gerenciamento de configurações de conexão.

Ele é implementado para melhorar a escalabilidade, aumentar a taxa de transferência do delivery e ajudar a enviar mais emails mais rapidamente. Isso é feito com novas técnicas de delivery adaptáveis que alteram as configurações de envio de email em tempo real, com base no feedback dos Provedores de serviço da Internet.

## Uso e benefícios

**O que é o MTA aprimorado?**

O Adobe Campaign usa um Agente de transferência de email (MTA) que executa o MTA de email comercial do SparkPost chamado **Momento**.

O Momentum representa uma tecnologia MTA inovadora e de alto desempenho, que inclui um tratamento mais inteligente de rejeição e um recurso automatizado de otimização de entrega que ajuda os remetentes a alcançarem e manterem as taxas ideais de delivery da caixa de entrada.

**Quais são os benefícios?**

* O MTA aprimorado permite um aumento maciço na velocidade geral do throughput e uma redução significativa nas devoluções temporárias.
* Ele usa a tecnologia MTA mais recente para fornecer a você as velocidades de throughput ideais para a entrega de email.
* Adaptando-se instantânea e automaticamente ao feedback que recebe, ele também garante um delivery de email mais preciso e inteligente com dados de delivery em tempo real.

## Especificidades do MTA aprimorado {#enhanced-mta-impacts}

### Qualificação de rejeição

Para **síncrono** mensagens de erro de falha de delivery, o MTA aprimorado determina o tipo de devolução e a qualificação e envia essas informações para o Campaign.

O MTA aprimorado qualifica a rejeição de SMTP e envia essa qualificação de volta ao Campaign no formato de um código de rejeição mapeado para um motivo de rejeição e qualificação do Campaign.

>[!NOTE]
>
>Atualmente **assíncrono** as rejeições são qualificadas pelo processo inMail por meio do **[!UICONTROL Inbound email]** regras. Para obter mais informações, consulte [Documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

Saiba mais sobre falhas de delivery em [esta seção](delivery-failures.md).

### Período de validade

A configuração do período de validade em seus deliveries do Campaign só será usada pelo MTA aprimorado se for definida como **3,5 dias ou menos**. Se você definir um valor superior a 3,5 dias no Campaign, ele não será levado em consideração.

Por exemplo, se o período de validade for definido como o valor padrão de 5 dias no Campaign, as mensagens com rejeição temporária entrarão na fila de tentativas do MTA aprimorado e serão repetidas apenas por até 3,5 dias a partir do momento em que a mensagem chegar ao MTA aprimorado. Nesse caso, o valor definido no Campaign não será usado.

Quando uma mensagem estiver na fila do MTA aprimorado por 3,5 dias e não for entregue, o tempo limite expirará, e seu status será atualizado de **[!UICONTROL Sent]** para **[!UICONTROL Failed]** nos logs do delivery.

Para obter mais informações sobre o período de validade, consulte [Documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}.

### Tentativas

As tentativas de rejeição temporária e o tempo entre elas são determinados pelo MTA aprimorado com base no tipo e na gravidade das respostas de rejeição provenientes do domínio de email da mensagem.

>[!NOTE]
>
>As configurações de nova tentativa nas propriedades de delivery não são usadas pelo Campaign.

Saiba mais sobre tentativas em [esta seção](delivery-failures.md#retries).

### Regras MX específicas

As regras MX (Mail eXchanger) são as regras que gerenciam a comunicação entre um servidor de envio e um servidor de recebimento.

O MTA aprimorado tem suas próprias regras de MX, que permitem personalizar a taxa de transferência por domínio com base em sua própria reputação de email histórica e no feedback em tempo real proveniente dos domínios para os quais você está enviando emails.

### Assinatura DKIM

O Domain Keys Identified Mail (DKIM) é um método de autenticação usado para detectar endereços de remetente falsificados (comumente chamados de falsificação).

No Adobe Campaign, a assinatura de autenticação de email do DKIM é executada pelo MTA aprimorado.

Saiba mais sobre o DKIM no [Guia de práticas recomendadas de capacidade de entrega do Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=pt-BR#authentication){target=&quot;_blank&quot;}.

## Serviço de feedback por email {#email-feedback-service}

Com o recurso Serviço de feedback por email (EFS), o status de cada email é relatado com precisão, pois o feedback é capturado diretamente do MTA aprimorado (Agente de transferência de mensagem).

Depois que o delivery é iniciado, não há alteração na porcentagem de **[!UICONTROL Success]** quando a mensagem é transmitida com êxito do Campaign para o MTA aprimorado.

Os logs do delivery mostram o status **[!UICONTROL Taken into account by the service provider]** para cada endereço direcionado.

Quando a mensagem é realmente entregue aos perfis direcionados e uma vez que essas informações são relatadas em tempo real do MTA aprimorado, os logs do delivery mostram o status **[!UICONTROL Sent]** para cada endereço que recebeu a mensagem com êxito. A porcentagem de **[!UICONTROL Success]** aumenta de acordo com cada delivery bem-sucedido.

Quando mensagens com rejeição permanente são relatadas do MTA aprimorado, o status do log muda de **[!UICONTROL Taken into account by the service provider]** para **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Quando mensagens com rejeição temporária são relatadas do MTA aprimorado, o status do log permanece inalterado (**[!UICONTROL Taken into account by the service provider]**): somente o [motivo do erro](delivery-failures.md#delivery-failure-reasons) é atualizado<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. A porcentagem de **[!UICONTROL Success]** permanece inalterada. Mensagens de rejeição automática são repetidas em todo o delivery [período de validade](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

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
| A mensagem foi transmitida com êxito do Campaign para o MTA aprimorado | A porcentagem de **[!UICONTROL Success]** não é exibida (começa em 0%) | Levado em consideração pelo provedor de serviço |
| Mensagens com rejeição permanente são relatadas de volta do MTA aprimorado | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Com falha |
| Mensagens com rejeição temporária são relatadas de volta do MTA aprimorado | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Levado em consideração pelo provedor de serviço |
| Tentativas de mensagens com rejeição temporária são bem-sucedidas | A porcentagem de **[!UICONTROL Success]** é aumentada de maneira apropriada | Enviada |
| Falha nas tentativas de mensagens com rejeição temporária | Nenhuma alteração na porcentagem de **[!UICONTROL Success]** | Com falha |

