---
title: Monitorar seus deliveries na interface do Campaign
description: Saiba como acessar a lista de deliveries e usar o painel de delivery para monitorar seus deliveries
feature: Monitoring
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 70%

---

# Monitorar seus deliveries na interface do Campaign {#delivery-dashboard}

O monitoramento de deliveries é essencial para garantir que suas campanhas sejam eficientes e atinjam os clientes. O Adobe Campaign fornece ferramentas para acessar seus deliveries e monitorar seu desempenho por meio da lista de delivery e do painel de delivery.

## Acessar a lista de deliveries {#list-of-deliveries}

Você pode acessar entregas a partir da lista de entrega, por meio do nó **[!UICONTROL Campaign Management > Deliveries]** da árvore.

![](assets/deliveries-list.png)

Por padrão, a lista de entregas contém os nomes e os status das entregas criadas no nó selecionado. Ele também mostra o número de mensagens a serem enviadas, processadas e enviadas com sucesso.

* O número de **[!UICONTROL Messages to send]** corresponde ao número de destinatários target após a análise e antes da entrega.
* O número de mensagens na coluna **[!UICONTROL Success]** corresponde ao número de mensagens enviadas pelo servidor e recebidas pelos destinatários.
* O número de mensagens **[!UICONTROL Processed]** corresponde ao número de mensagens recebidas mais o número de mensagens com erros.

>[!NOTE]
>
>Para entregas grandes, convém atualizar esses valores. Para fazer isso, selecione a entrega em questão e clique com o botão direito nela. Selecione **[!UICONTROL Action > Recompute delivery and tracking indicators...]** e use o assistente para atualizar essas informações.

## Visão geral do painel de entrega {#delivery-dashboard-overview}

O **painel de entrega** é fundamental para monitorar suas entregas e eventuais problemas encontrados durante o envio de mensagens.

Ele permite recuperar informações sobre uma entrega e editá-las, se necessário. Lembre-se de que o conteúdo da guia não pode mais ser alterado após o envio da entrega.

Estas são as informações que você pode monitorar usando as várias guias disponíveis no painel:

* [Resumo da entrega](#delivery-summary)
* [Relatórios de entrega](#delivery-reports)
* [Logs da entrega, mirror pages, exclusões](#delivery-logs-and-history)
* [Histórico e logs de rastreamento da entrega](#tracking-logs)
* [Renderização de entrega](#delivery-rendering)
* [Auditoria de entrega](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**Tópicos relacionados:**

* [Entender as falhas de entrega](delivery-failures.md)
* [Gerenciamento de quarentena](quarantines.md)
* [Práticas recomendadas de entrega](../start/delivery-best-practices.md)
* [Gerenciamento da capacidade de entrega](about-deliverability.md)

## Resumo da entrega {#delivery-summary}

A guia **[!UICONTROL Summary]** contém as características da entrega: status da entrega, canal usado, informações sobre o remetente, assunto, informações relacionadas à execução.

## Relatórios de entrega {#delivery-reports}

O link **[!UICONTROL Reports]**, acessível na guia **[!UICONTROL Summary]**, permite que você veja um conjunto de relatórios referentes à ação da entrega: relatório geral da entrega, relatório detalhado, relatório da entrega, distribuição de mensagens com falha, taxa de abertura, cliques e transações, etc.

O conteúdo dessa guia pode ser configurado de acordo com os requisitos. Para obter mais informações sobre relatórios de entrega, consulte [esta seção](../reporting/delivery-reports.md).

![](assets/delivery-report.png)

## Logs da entrega, histórico e exclusões {#delivery-logs-and-history}

A guia **[!UICONTROL Delivery]** fornece um histórico das ocorrências nesta entrega. Ela contém os logs de entrega, ou seja, a lista de mensagens enviadas e seus status, e as mensagens associadas.

Para uma entrega, você pode exibir (por exemplo) apenas os destinatários com uma entrega com falha ou um endereço em quarentena. Para fazer isso, clique no botão **[!UICONTROL Filters]** e selecione **[!UICONTROL By state]**. Em seguida, selecione o estado na lista suspensa. Vários status são listados na [página de status de entrega](delivery-statuses.md).

>[!NOTE]
>
>A lista que exibe os logs do delivery pode ser personalizada, como qualquer lista no Campaign. Por exemplo, você pode adicionar uma coluna para saber qual endereço IP enviou cada email em uma entrega. Para obter mais informações sobre a configuração de exibição de listas, consulte [esta seção](../config/ui-settings.md#customize-lists).

![](assets/s_ncs_user_delivery_delivery_tab.png)

O link **[!UICONTROL Display the mirror page for this message...]** permite exibir a mirror page do conteúdo da entrega selecionado na lista em uma nova janela.

A mirror page só está disponível para as entregas para as quais o conteúdo HTML foi definido. Para obter mais informações, consulte [Link para a mirror page](mirror-page.md).

![](assets/s_ncs_user_wizard_miror_page_link.png)

## Histórico e logs de rastreamento da entrega {#tracking-logs}

A guia **[!UICONTROL Tracking]** lista o histórico de rastreamento dessa entrega. Esta guia exibe os dados de rastreamento das mensagens enviadas, ou seja, todas as URLs sujeitas ao rastreamento por meio do Adobe Campaign. Os dados de rastreamento são atualizados de hora em hora.

>[!NOTE]
>
>Se o rastreamento não estiver habilitado para uma entrega, essa guia não será exibida.

A configuração de rastreamento é realizada no estágio apropriado do assistente de entrega. Consulte [Como configurar links rastreados](tracking.md).

Os dados de **[!UICONTROL Tracking]** são interpretados nos relatórios de entrega. Consulte [esta seção](../reporting/delivery-reports.md).

![](assets/s_ncs_user_delivery_tracking_tab.png)

## Renderização da caixa de entrada {#delivery-rendering}

A guia **[!UICONTROL Inbox rendering]** permite que você visualize a mensagem enviada nos diferentes contextos em que ela pode ser recebida e verificar a compatibilidade nos principais desktops e aplicativos.

Assim você pode ter certeza de que a sua mensagem será exibida aos destinatários de forma eficaz em uma variedade de clientes da web, webmails e dispositivos.

Para obter mais informações sobre renderização da Caixa de entrada, consulte [esta página](inbox-rendering.md)


## Auditoria de entrega {#delivery-audit-}

A guia **[!UICONTROL Audit]** contém o log de entrega e todas as mensagens relacionadas às provas.

O botão **[!UICONTROL Refresh]** permite atualizar os dados. Use o botão **[!UICONTROL Filters]** para definir um filtro nos dados.

Ícones especiais permitem identificar erros ou avisos. Consulte [Análise de entrega](delivery-analysis.md).

A subguia **[!UICONTROL Proofs]** permite visualizar a lista de provas que foram enviadas.

![](assets/s_ncs_user_delivery_log_tab.png)

Você pode modificar as informações exibidas nessa janela (e das guias **[!UICONTROL Delivery]** e **[!UICONTROL Tracking]**) selecionando as colunas a serem exibidas. Para fazer isso, clique no ícone **[!UICONTROL Configure list]** localizado no canto inferior direito. Para obter mais informações sobre a configuração de exibição de listas, consulte [esta seção](../config/ui-settings.md#customize-lists).

## Sincronização do painel de entrega {#delivery-dashboard-synchronization}

No painel de entrega, convêm verificar as mensagens processadas e os logs de entregas para garantir que sua entrega foi enviada com êxito.

Alguns indicadores ou status podem estar incorretos ou não atualizados, isso pode ser resolvido com as seguintes soluções:

* Se o status da entrega estiver incorreto, verifique se todas as aprovações necessárias foram feitas para a entrega ou se os fluxos de trabalho técnicos do **[!UICONTROL operationMgt]** e do **[!UICONTROL deliveryMgt]** estão sendo executados sem erros.

* Se o contador de entrega não corresponder à sua entrega, tente recalcular os indicadores clicando com o botão direito do mouse na entrega relevante no explorador do Adobe Campaign e selecionando **[!UICONTROL Recompute delivery and tracking indicators]** > **[!UICONTROL Actions]** para sincronizar novamente. Para obter mais informações sobre indicadores de rastreamento, consulte esta [seção](../reporting/delivery-reports.md#tracking-indicators).

Você também pode rastrear suas entregas com relatórios diferentes através do painel de entrega. Para obter mais informações, consulte esta [seção](../reporting/delivery-reports.md).

>[!NOTE]
>
>Como usuário do Campaign v8 Managed Cloud Services, a infraestrutura é monitorada e gerenciada pela Adobe. Se você tiver problemas persistentes com os indicadores de entrega ou com a sincronização de painéis, entre em contato com o Atendimento ao cliente da Adobe.

## Solução de problemas de entregas lentas {#troubleshooting-slow-deliveries}

Se a entrega parecer demorar mais do que o normal depois de clicar no botão **[!UICONTROL Send]**, verifique as possíveis causas a seguir:

### Problemas de reputação do endereço IP

Alguns provedores de email podem ter adicionado seus endereços IP a uma lista de bloqueios. Verifique os logs da entrega (broadlogs) na guia **[!UICONTROL Delivery]** para obter mensagens de devolução que indiquem problemas de reputação. Consulte a seção [monitoramento da capacidade de entrega](monitoring-deliverability.md) para obter orientação sobre o gerenciamento de reputação.

### Tamanho e complexidade do delivery

Seu delivery pode ser muito grande para ser processado rapidamente. Isso pode ocorrer com:

Grande personalização do JavaScript que requer processamento de dados significativo para cada recipient.

Entrega com mais de 60 kilobytes devido ao grande conteúdo do HTML, imagens incorporadas ou personalização extensa.

Consulte [Práticas recomendadas de entrega](../start/delivery-best-practices.md) para saber mais sobre diretrizes de conteúdo e práticas recomendadas de personalização. O tamanho máximo recomendado é de aproximadamente 35 KB para um desempenho ideal.

### Desempenho do sistema

Problemas de sistema podem impedir que os servidores processem deliveries com eficiência. Se você suspeitar de problemas de desempenho, verifique os logs do delivery em busca de erros de tempo limite ou problemas de comunicação.

>[!NOTE]
>
>Como usuário do Campaign v8 Managed Cloud Services, o monitoramento da infraestrutura do servidor é gerenciado pela Adobe. Se você tiver problemas persistentes de desempenho com o envio do delivery, entre em contato com o Atendimento ao cliente da Adobe com seus logs do delivery.

