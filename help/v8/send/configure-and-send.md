---
title: Configurar emails com o Adobe Campaign
description: Saiba como configurar emails no Adobe Campaign.
feature: Email
role: User
level: Beginner
source-git-commit: 21e251acd76f2bbb751f8e295934d597af336559
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 83%

---

# Configurar e enviar o delivery {#configure-delivery}

## Definir parâmetros adicionais {#delivery-additional-parameters}

Antes de enviar o delivery, você poderá definir os parâmetros de envio nas propriedades de delivery, por meio da guia **[!UICONTROL Delivery]**.

![](assets/delivery-properties-delivery.png)

* **[!UICONTROL Delivery priority]**: use essa opção para alterar a ordem de envio dos deliveries, definindo o nível de prioridade em **[!UICONTROL Very low]** para **[!UICONTROL Very high]** (o valor padrão é **[!UICONTROL Normal]**).

* **[!UICONTROL Message batch quantity]**: use essa opção para definir o número de mensagens agrupadas no mesmo pacote de distribuição XML. Se o parâmetro for definido como 0, as mensagens serão automaticamente agrupadas. O tamanho do pacote é definido pelo cálculo `<delivery size>/1024`, com no mínimo 8 e no máximo 256 mensagens por pacote.

  >[!IMPORTANT]
  >
  >Quando o delivery é criado duplicando um existente, esse parâmetro é redefinido.

* **[!UICONTROL Send using multiple waves]**: use essa opção para enviar suas mensagens em lotes, em vez de enviá-las para todo o público-alvo de uma só vez. [Saiba mais](#sending-using-multiple-waves).

* **[!UICONTROL Test SMTP delivery]**: use essa opção para testar o envio via SMTP. A entrega é processada até a conexão com o servidor SMTP, mas não é enviada: para cada destinatário do delivery, o Campaign se conecta ao servidor do provedor SMTP, executa o comando SMTP RCPT TO e encerra a conexão antes do comando SMTP DATA.

  >[!NOTE]
  >
  >* Essa opção não deve ser definida no mid-sourcing.
  >
  >* Saiba mais sobre a configuração do servidor SMTP em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/configure-delivery-settings.html#smtp-relay){target="_blank"}.

* **[!UICONTROL Email BCC]**: essa opção permite armazenar emails em um sistema externo por meio do CCO. Para isso, basta adicionar um endereço de email de CCO ao destinatário da mensagem. [Saiba mais](email-parameters.md).

## Enviar usando várias ondas {#sending-using-multiple-waves}

Para balancear a carga, você pode dividir deliveries em vários lotes. Configure o número de lotes e sua proporção com relação ao delivery inteiro.

>[!NOTE]
>
>Você só poderá definir o tamanho e o atraso entre duas ondas consecutivas. Os critérios de seleção de recipient para cada onda não podem ser configurados.

1. Abra a janela de propriedades do e clique na guia **[!UICONTROL Delivery]** Delivery.
1. Selecione a opção **[!UICONTROL Send using multiple waves]** e clique no link **[!UICONTROL Define waves...]**.

   ![](assets/delivery-define-waves.png)

1. Para configurar ondas, você pode:

   * Definir o tamanho de cada onda. Por exemplo, se você inserir **[!UICONTROL 30%]** no campo correspondente, cada onda representará 30% das mensagens incluídas no delivery, exceto a última, que representará 10% das mensagens.

     No campo **[!UICONTROL Period]**, especifique o atraso entre o início de duas ondas consecutivas. Por exemplo, se você inserir **[!UICONTROL 2d]**, a primeira onda começará imediatamente, a segunda onda começará em dois dias, a terceira onda em quatro dias e assim por diante.

     ![](assets/delivery-waves-size.png)

   * Defina um calendário para enviar cada onda.

     Na coluna **[!UICONTROL Start]**, especifique o atraso entre o início de duas ondas consecutivas. Na coluna **[!UICONTROL Size]**, insira um número fixo ou uma porcentagem.

     No exemplo abaixo, a primeira onda representa 25% do número total de mensagens incluídas no delivery e iniciará imediatamente. As próximas duas ondas completam o delivery e são definidas para começar em intervalos de seis horas.

     ![](assets/delivery-waves-calendar.png)

   Uma regra de tipologia específica, **[!UICONTROL Wave scheduling check]**, garante que a última onda seja planejada antes do limite da validade do delivery. Tipologias de campanha e suas regras, configuradas na variável **[!UICONTROL Typology]** das propriedades de delivery, são apresentadas em [nesta seção](../../automation/campaign-opt/campaign-typologies.md#typology-rules)<!--ref TBC-->.

   >[!IMPORTANT]
   >
   >Certifique-se de que as últimas ondas não excedam o prazo do delivery, que é definido na guia **[!UICONTROL Validity]**. Caso contrário, algumas mensagens podem não ser enviadas.
   >
   >Você também deverá permitir tempo suficiente para novas tentativas ao configurar as últimas ondas. <!--See [this section]().-->

1. Para monitorar seus envios, vá para os logs de delivery. Consulte [esta página](send.md)<!--ref TBC-->.

   Você pode ver os deliveries que já foram enviados nas ondas processadas (status **[!UICONTROL Sent]**) e os deliveries a serem enviados nas ondas restantes (status **[!UICONTROL Pending]**).

Os dois exemplos abaixo são os casos de uso mais comuns para usar várias ondas.

* **Durante o processo de aumento**

  Quando os emails são enviados usando uma nova plataforma, os provedores de serviços de Internet (ISPs) suspeitam de endereços IP que não são reconhecidos. Se grandes volumes de emails forem enviados repentinamente, os ISPs freqüentemente os marcam como spam.

  Para evitar ser marcado como spam, você poderá aumentar progressivamente o volume enviado usando ondas. Isso deve garantir o desenvolvimento suave da fase de inicialização e permitir que você reduza a taxa geral de endereços inválidos.

  Para fazer isso, use a opção **[!UICONTROL Schedule waves according to a calendar]**. Por exemplo, defina a primeira onda para 10%, a segunda para 15% e assim por diante.

  ![](assets/delivery-waves-ex-ramp-up.png)

* **Campanhas envolvendo uma central de atendimento**

  Ao gerenciar uma campanha de fidelidade por telefone, sua organização tem uma capacidade limitada para processar o número de chamadas para contatar os assinantes.

  Usando ondas, você poderá restringir o número de mensagens a 20 por dia, que é a capacidade diária de processamento de uma central de atendimento.

  Para fazer isso, selecione a opção **[!UICONTROL Schedule multiple waves of the same size]**. Insira **[!UICONTROL 20]** como o tamanho da onda e **[!UICONTROL 1d]** no campo **[!UICONTROL Period]**.

  ![](assets/delivery-waves-ex-call-center.png)

## Confirmar o delivery {#confirm-delivery}

Quando o delivery estiver configurado e pronto para ser enviado, certifique-se de executar a análise do delivery antes de confirmar o envio.

Para fazer isso, siga as etapas abaixo.

1. Clique em **[!UICONTROL Send]**, selecione a ação desejada.

   * Para enviar o delivery imediatamente, selecione [**Entregar o mais rápido possível**].
   * Para agendar o envio para uma data posterior, selecione **[!UICONTROL Postpone the delivery]**. [Saiba mais](#schedule-delivery-sending)

1. Clique em **[!UICONTROL Analyze]**. Para obter mais informações, consulte [Iniciar a análise](../../delivery/using/steps-validating-the-delivery.md#analyzing-the-delivery).

   ![](assets/delivery-send-analyze.png)

1. Depois de concluído, clique em **[!UICONTROL Confirm delivery]** para iniciar a entrega de mensagens.

   ![](assets/delivery-send-confirm.png)

1. Você pode fechar o assistente do delivery e rastrear a execução do delivery a partir do **[!UICONTROL Delivery]** , acessível por meio do detalhe deste delivery ou pela lista de deliveries.

   Para obter mais informações, consulte as seções abaixo:

   * [Monitoramento de uma entrega](send.md)
   * [Compreensão de falhas de entrega](delivery-failures.md)

<!--About message tracking-->

## Agendar o envio do delivery {#schedule-delivery-sending}

É possível adiar a entrega de mensagens para agendar a entrega ou gerenciar as regras de pressão e evitar o excesso de solicitações em relação a uma população.

1. Clique no botão **[!UICONTROL Send]** e selecione a opção **[!UICONTROL Postpone delivery]**.

1. Especifique uma data de início no campo **[!UICONTROL Contact date]**.

   ![](assets/delivery-send-postpone.png)

1. Inicie a análise de delivery e confirme o envio do delivery. No entanto, o envio do delivery não será iniciado até a data indicada no campo **[!UICONTROL Contact date]**.

   >[!IMPORTANT]
   >
   >Depois de iniciar a análise, a data de contato que você definiu será corrigida. Se você modificar essa data, será necessário reiniciar a análise para que suas modificações sejam levadas em conta.

   ![](assets/delivery-send-scheduled.png)

Na lista do delivery, a entrega será exibida com a variável **[!UICONTROL Pending]** status.

O agendamento pode ser configurado de forma ascendente através do botão **[!UICONTROL Scheduling]** do delivery.

![](assets/delivery-scheduling-button.png)

Isso permite adiar o delivery para uma data posterior ou salvar o delivery no calendário provisional.

* A opção **[!UICONTROL Schedule delivery (no automatic execution)]** permite agendar uma análise provisional do delivery.

  Quando essa configuração é salva, o delivery muda para o status **[!UICONTROL Targeting pending]**. A análise será iniciada na data especificada.

* A opção **[!UICONTROL Schedule delivery (automatic execution on planned date)]** permite especificar a data do delivery.

  Clique em **[!UICONTROL Send]** e selecione **[!UICONTROL Postpone delivery]**, depois inicie a análise e confirme o delivery. Quando a análise for concluída, o destinatário do delivery estará pronto e as mensagens serão automaticamente enviadas na data especificada.

Datas e horas são expressas no fuso horário do operador atual. A lista suspensa **[!UICONTROL Time zone]** localizada abaixo do campo de entrada de data do contato permite converter automaticamente a data e a hora inseridas para o fuso horário selecionado.

Por exemplo, se você agendar uma entrega para que ela seja executada automaticamente às 8h, horário de Londres, a hora será convertida automaticamente para o fuso horário selecionado:

![](assets/delivery-schedule-time-zone.png)

<!--
## Adjust delivery failure management {#delivery-failure-management}

### Configure retries {#configure-retries}

Temporarily undelivered messages due to a **Soft** or **Ignored** error are subject to an automatic retry. The delivery failure types and reasons are presented in this [section](../../delivery/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

>[!IMPORTANT]
>
>For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the retry settings in the delivery are no longer used by Campaign. Soft bounce retries and the length of time between them are determined by the Enhanced MTA based on the type and severity of the bounce responses coming back from the message's email domain.

For on-premise installations and hosted/hybrid installations using the legacy Campaign MTA, the central section of the **[!UICONTROL Delivery]** tab for delivery parameters indicates how many retries should be performed the day after the delivery and the minimum delay between retries.

![](assets/s_ncs_user_wizard_retry_param.png)

By default, five retries are scheduled for the first day of the delivery with a minimum interval of one hour spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Validity]** tab (see [Defining validity period](#defining-validity-period)).

### Define the validity period {#define-validity-period}

When the delivery has been launched, the messages (and any retries) can be sent until the delivery deadline. This is indicated in the delivery properties, via the **[!UICONTROL Validity]** tab.

![](assets/s_ncs_user_email_del_valid_period.png)

* The **[!UICONTROL Delivery duration]** field lets you enter the limit for global delivery retries. This means that Adobe Campaign sends the messages beginning on the start date, and then, for messages returning an error only, regular, configurable retries are performed until the validity limit is reached.

  You can also choose to specify dates. To do this, select **[!UICONTROL Explicitly set validity dates]**. In this case, the delivery and validity limit dates also let you specify the time. The current time is used by default, but you can modify this directly in the input field.

  >[!IMPORTANT]
  >
  >For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the **[!UICONTROL Delivery duration]** setting in your Campaign email deliveries will be used only if set to **3.5 days or less**. If you define a value higher than 3.5 days, it will not be taken into account.

* **Validity limit of resources**: The **[!UICONTROL Validity limit]** field is used for uploaded resources, mainly for the mirror page and images. The resources on this page are valid for a limited time (to save disk space).

  The values in this field can be expressed in the units listed in [this section](../../platform/using/adobe-campaign-workspace.md#default-units).
-->