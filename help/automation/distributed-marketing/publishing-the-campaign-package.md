---
product: campaign
title: Publicar o pacote de campanha
description: Publicar o pacote de campanha
feature: Distributed Marketing
version: Campaign v8, Campaign Classic v7
role: User
exl-id: 2cd1981d-f192-41dc-b2f2-4fcd60493079
TQID: https://experienceleague.adobe.com/cikc1fFIGeRzZ-mas4mqGqMsuMCSDOHhBT2g4tf8fZw
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: cdc2fbe67fe123c895c8d3d71daffe022ba5c030
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 70%
---
# Publicar o pacote de campanha{#publishing-the-campaign-package}

Operadores de entidades centrais publicam campanhas que desejam oferecer às entidades locais na **[!UICONTROL list of campaign packages]**.

Antes de serem publicados na lista de pacotes de campanha, os pacotes de campanha devem ser aprovados pela entidade central. Para fazer isso, é possível especificar um revisor ou grupo de revisores por meio do link **[!UICONTROL Approval parameters]** no pacote de campanha.

## Atribuir um revisor {#assigning-a-reviewer}

Para selecionar o revisor, clique no link **[!UICONTROL Approval parameters]** do pacote de campanha e escolha o revisor relevante na lista suspensa.

![Caixa de diálogo de parâmetros de aprovação de um pacote de campanha com o campo Revisor definido como um grupo de gerenciamento central.](assets/s_advuser_mkg_dist_define_valid.png)

Você pode iniciar o processo de aprovação clicando em **[!UICONTROL Submit for approval]**.

![Painel do pacote de campanha mostrando a mensagem enviada para aprovação e o botão Aprovar o pacote.](assets/s_advuser_mkg_dist_valid_process.png)

Uma mensagem de notificação é enviada ao revisor para confirmar a disponibilidade desse pacote de campanha. A mensagem contém um link para aceitar ou rejeitar a aprovação via acesso à web.

![Email de aprovação com o link Aceitar ou Rejeitar abrindo a página Ação no pacote com as opções Aceitar e Rejeitar.](assets/s_advuser_mkg_dist_valid_process1.png)

>[!NOTE]
>
>No nível da entidade organizacional, você também pode especificar os revisores para aprovar pedidos. Para obter mais informações, consulte [Entidades organizacionais](about-distributed-marketing.md#organizational-entities).

## Adicionar outros revisores {#adding-other-reviewers}

É possível adicionar outros revisores a partir do link **[!UICONTROL Edit...]**, localizado na guia **[!UICONTROL Approval parameters...]** do pacote de campanha.

![Editar link nos Parâmetros de aprovação abrindo a janela Editar revisores com Revisores adicionais e Agendamento de aprovação.](assets/s_advuser_mkg_dist_select_op_valid.png)

## Cronograma de aprovação {#approval-periods}

Por padrão, os revisores recebem três dias a partir da data de envio para processar a aprovação.

Na janela dos revisores de edição, é possível definir lembretes para enviar uma ou várias mensagens se um pacote de campanha não tiver sido aprovado. Para fazer isso, clique no link **[!UICONTROL Add reminder]** e, em seguida, no botão **[!UICONTROL Add]**.

Os lembretes podem ser enviados em uma determinada data e/ou **x** dias após a data de envio. O tipo de lembrete pode ser configurado na primeira coluna da tabela de lembretes. No exemplo abaixo, os revisores receberão uma mensagem de lembrete em 11/01/2023, ou seja, dois dias antes da data selecionada na coluna **[!UICONTROL Date]**, e um segundo lembrete um dia antes do final do período de aprovação, ou seja, dois dias após a data de envio para aprovação.

![Editar janela de revisores com um atraso de aprovação 3d e dois lembretes: Atraso do prazo de aprovação e Data especificada.](assets/s_advuser_mkg_dist_reminder_planning.png)

Depois que estiver definido e o pacote for enviado para aprovação, o cronograma de execução é exibido na guia **[!UICONTROL Audit]**. Ele mostra o prazo de processamento calculado com base na configuração anterior, bem como nas datas de todos os lembretes configurados.

## Aprovar via console do cliente {#approving-via-the-adobe-campaign-console}

Se nenhum revisor tiver sido especificado ou se nenhum dos operadores notificados tiver aprovado o pacote, o botão **[!UICONTROL Approve the package]** permitirá prosseguir diretamente para a aprovação no **[!UICONTROL Dashboard]** do pacote de campanha ou da visão geral dos pacotes.

![Aprove o botão de pacote abrindo a caixa de diálogo Ação no pacote com as opções Aceitar ou Rejeitar e um campo Comentário.](assets/s_advuser_mkg_dist_valid_button.png)

Após a aprovação, a campanha é publicada, adicionada à lista e, assim que sua data de disponibilidade é alcançada, as entidades locais podem usá-la. Se as entidades locais foram especificadas ao criar a campanha, uma mensagem é enviada aos operadores no grupo de notificação para saberem que a campanha está disponível. Se nenhuma entidade foi especificada anteriormente, a campanha estará disponível para todas as entidades locais, por padrão. Para obter mais informações, consulte [Entidades organizacionais](about-distributed-marketing.md#organizational-entities).
