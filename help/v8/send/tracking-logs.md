---
title: Acessar logs de rastreamento
description: Saiba como acessar e interpretar logs de rastreamento
feature: Monitoring
role: User
level: Beginner
exl-id: df494786-5950-4646-aa9c-4dde45845057
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 19%

---

# Acessar logs de rastreamento {#accessing-the-tracking-logs}

Quando a entrega é enviada e o rastreamento é ativado, o fluxo de trabalho técnico **[!UICONTROL Tracking]** é encarregado de obter os dados de rastreamento. Por padrão, isso é executado por hora.

## Exibir rastreamento em perfis de recipient {#recipient-tracking}

Essas informações aparecem na guia **[!UICONTROL Tracking]** do perfil de destinatários direcionados pela entrega, como no exemplo a seguir:

![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

Essa guia exibe todos os URLs rastreados e clicados pelo recipient, incluindo:

* O URL clicado
* A data e a hora do clique
* O delivery no qual o URL foi encontrado
* Quaisquer outras informações de rastreamento relevantes

É possível filtrar e classificar essas informações para analisar o comportamento do recipient e identificar padrões de engajamento.

## Exibir rastreamento nas entregas {#delivery-tracking}

As informações de rastreamento também podem ser acessadas por meio da guia **[!UICONTROL Tracking]** da entrega.

![](assets/s_ncs_user_select_tracking_tab_from_del.png)

Nessa guia, é possível exibir:

* **[!UICONTROL Tracking statistics]**: fornece uma visão geral de aberturas, cliques e outros eventos de rastreamento
* **[!UICONTROL URLs and click streams]**: mostra quais links foram clicados e quantas vezes
* **[!UICONTROL Hot clicks]**: exibe uma representação visual de onde os destinatários clicaram em sua mensagem
* **[!UICONTROL Tracking logs]**: fornece registros de rastreamento detalhados e individuais

## Solução de problemas de rastreamento {#troubleshooting}

>[!NOTE]
>
>Se não for possível ver a guia **[!UICONTROL Tracking]** de uma entrega, significa que o rastreamento não foi ativado. Consulte [esta seção](tracked-links.md) para saber como configurar o rastreamento.

### Verifique o workflow técnico de rastreamento {#check-tracking-workflow}

O workflow técnico Tracking deve estar em execução para coletar dados de rastreamento. Você pode localizar o fluxo de trabalho técnico de Rastreamento na pasta **[!UICONTROL Administration > Production > Technical workflows]**.

Para verificar o workflow:

1. Abrir o fluxo de trabalho **[!UICONTROL Tracking]**
1. Verificar a data da última execução
1. Verificar se não há erros nos logs de workflow

Se o workflow não estiver em execução ou tiver erros, entre em contato com o administrador do sistema.

## Verificar coleta de dados de rastreamento

Depois de enviar um delivery com rastreamento ativado:

1. Aguardar até que o workflow de rastreamento seja executado (por padrão, a cada hora)
1. Abra a entrega e vá para a guia **[!UICONTROL Tracking]**
1. Verifique se os dados de rastreamento estão aparecendo
1. Se nenhum dado for exibido, verifique se:
   * O rastreamento foi ativado nas configurações de delivery
   * O fluxo de trabalho técnico de rastreamento está em execução
   * Os recipients abriram o email e clicaram em links

## Tópicos relacionados {#related-topics}

* [Saiba como configurar links rastreados](tracked-links.md)
* [Saiba como testar o rastreamento](testing-tracking.md)
* [Entender os relatórios de rastreamento](../reporting/delivery-reports.md#tracking-indicators)

