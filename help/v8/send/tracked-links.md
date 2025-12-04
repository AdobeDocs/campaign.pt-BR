---
title: Configurar links rastreados
description: Saiba como configurar links rastreados em deliveries
feature: Monitoring
role: User, Developer
level: Beginner
exl-id: ed88e1d6-c0d5-4a85-9f3e-be670f4bcc10
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 80%

---

# Configurar links rastreados {#how-to-configure-tracked-links}

Para cada entrega, você pode rastrear a recepção das mensagens e a ativação dos links inseridos no conteúdo da mensagem. Isso permite rastrear o comportamento dos destinatários seguindo as ações de entrega que foram direcionadas.

>[!NOTE]
>
>Os links no conteúdo de email que contêm personalização precisam de sintaxe específica para serem rastreados. Saiba mais sobre como adicionar links a emails que podem ser personalizados e que oferecem suporte ao rastreamento em [esta seção](personalized-links.md).

O rastreamento de mensagens é habilitado por padrão. Para personalizar como URLs são rastreados, siga as etapas abaixo:

1. Selecione a opção **[!UICONTROL Display URLs]** na seção inferior do assistente de entrega, abaixo do conteúdo da mensagem.

   ![](assets/s_ncs_user_email_del_display_urls.png)

   Ao selecionar um dos URLs rastreados na lista, ele é realçado no conteúdo da entrega, exceto pelo link na mirror page e no link de cancelamento de subscrição fornecido como padrão.

   ![](assets/s_ncs_user_email_del_show_urls.png)

1. Para cada URL da mensagem, selecione se deseja ativar ou não o rastreamento.

   >[!IMPORTANT]
   >
   >Quando o URL do link é usado como um rótulo, é recomendado desativar o rastreamento para evitar riscos de rejeição devido ao phishing.
   >
   >Por exemplo, se o URL www.adobe.com é inserido na mensagem e o rastreamento está ativado, o conteúdo do link de hipertexto será modificado para https://nlt.adobe.net/r/?id=xxxxxx. Isso significa que ele pode ser considerado como fraudulento por clientes de mensagens destinatárias.

1. Se necessário, altere o rótulo de rastreamento. Clique duas vezes no rótulo e insira um novo.

   >[!NOTE]
   >
   >Os rótulos dos URLs rastreados e os rótulos podem ser modificados para simplificar a leitura de informações ao rastrear as entregas. Dois URLs ou rótulos com o mesmo nome são adicionados ao calcular a contagem de cliques.

1. Se necessário, altere o modo de rastreamento. Selecione um novo modo na coluna **[!UICONTROL Tracking]** que corresponde ao link direcionado, conforme abaixo:

   ![](assets/s_ncs_user_select_tracking_mode.png)

   Para cada URL individual, é possível definir o modo de rastreamento para um destes valores:

   * **[!UICONTROL Enabled]**: ativa o rastreamento nesta URL.
   * **[!UICONTROL Not tracked]**: desativa o rastreamento nesta URL.
   * **[!UICONTROL Always enabled]**: sempre ativa o rastreamento desta URL. Essas informações são salvas para que na próxima vez, se o URL aparecer novamente em um conteúdo de mensagem futura, o rastreamento será ativado automaticamente.
   * **[!UICONTROL Never tracked]**: nunca ativa o rastreamento desta URL. Essas informações são salvas para que na próxima vez, se o URL aparecer novamente em um uma mensagem futura, o rastreamento será desativado automaticamente.
   * **[!UICONTROL Opt-out]**: considera esta URL como recusa ou cancelamento de assinatura.
   * **[!UICONTROL Mirror page]**: considera esta URL como sendo de mirror page.

1. Além disso, é possível selecionar uma categoria para cada URL rastreado na lista suspensa da coluna **[!UICONTROL Category]**. Essas categorias podem ser exibidas em relatórios, como no relatório **[!UICONTROL URLs and click streams]** (consulte [esta seção](../reporting/delivery-reports.md#urls-and-click-streams)). As categorias estão definidas em uma enumeração específica: **[!UICONTROL urlCategory]**. Saiba mais sobre como trabalhar com enumerações em [esta seção](../config/enumerations.md).

## Práticas recomendadas para delimitadores de URL {#url-delimiters}

É altamente recomendável colocar URLs em delimitadores na guia **[!UICONTROL Text content]** antes de aplicar a fórmula de rastreamento. Os delimitadores de URL inseridos nessa guia são usados pelo Adobe Campaign para identificar URLs em strings. Você pode usar estes pares de delimitadores:

* Parênteses ( )
* Colchetes [ ]
* Chaves { }

Neste exemplo, o URL https://www.adobe.com é seguido por um ponto e vírgula. O ponto e vírgula pode ser interpretado pelos clientes de email do destinatário como parte do URL. Isso pode quebrar o link. Para evitar esse problema, é possível colocar o URL em delimitadores de uma destas maneiras:

* (https://www.adobe.com);
* [https://www.adobe.com];
* {https://www.adobe.com};
