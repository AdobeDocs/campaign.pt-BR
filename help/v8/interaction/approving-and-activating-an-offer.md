---
product: campaign
title: Aprovação e ativação de uma oferta
description: Aprovação e ativação de uma oferta
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: managing-an-offer-catalog
exl-id: cf7649fe-f62a-4dfa-a19e-9c1ca545e3e3
TQID: 'https://experienceleague.adobe.com/f0zYxpc5-71Ci-4Q485v4rRdD1xHs6tKLkl7vrITMP0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 72%
---
# Aprovação e ativação de uma oferta{#approving-and-activating-an-offer}



Após completar o conteúdo da oferta, é preciso aprová-la para ser duplicada no ambiente live e ser entregue. A aprovação aborda o conteúdo da oferta e sua elegibilidade.

O banner no painel de oferta informa se a oferta precisa passar pelo ciclo de aprovação ou não.

![Banner do painel de oferta informando que a oferta está com aprovação pendente, com o botão Aprovação.](assets/offer_validate_001.png)

## Aprovação do conteúdo da oferta {#approving-offer-content}

Aprovar o conteúdo de oferta significa selecionar as representações que deseja disponibilizar no ambiente live.

O conteúdo de uma oferta tem uma representação por espaço. Como cada espaço de oferta tem sua própria estrutura e suas próprias funções de renderização, a representação da oferta pode variar.

É possível optar por aprovar o conteúdo da oferta em determinados espaços disponíveis e reject em outros.

>[!IMPORTANT]
>
>Quando o conteúdo e a elegibilidade de uma oferta são aprovados, o fluxo de trabalho de publicação (Notificação de oferta) é executado automaticamente e a oferta é ativada e disponibilizada em todos os espaços ativados.

Para aprovar o conteúdo da oferta, aplique as seguintes etapas:

1. Clique no botão **[!UICONTROL Approval]** e selecione **[!UICONTROL Approve content]** na janela pop-up.

   ![Menu de aprovação com Aprovar conteúdo selecionado, abrindo a Ação na caixa de diálogo de oferta.](assets/offer_validate_002.png)

1. Utilizando a lista suspensa, selecione as representações que deseja continuar editando ou aquelas que deseja publicar no ambiente live, então clique em **[!UICONTROL Content approval]**.

   ![Ação na caixa de diálogo de oferta: escolha Continuar edição ou Habilitar, adicione um comentário e clique em Aprovação de conteúdo.](assets/offer_validate_003.png)

   Quando o conteúdo da oferta for aprovado, as informações serão atualizadas na tabela do painel de ofertas.

   ![Painel de ofertas após a aprovação: a representação mostra Habilitado e a seção Aprovações mostra Conteúdo aprovado.](assets/offer_validate_004.png)

   >[!NOTE]
   >
   >A menção **[!UICONTROL Content approved]** não significa que todas as representações de oferta foram habilitadas e aprovadas. Indica se o processo de aprovação de conteúdo foi atingido, independentemente de todas as ofertas terem sido habilitadas/aprovadas ou não.

## Aprovação de elegibilidade para a oferta {#approving-offer-eligibility}

Aprovar a elegibilidade de oferta significa aceitar ou rejeitar pesos de oferta e as regras de elegibilidade também configuradas na oferta ou herdada das regras criadas na categoria pai.

>[!IMPORTANT]
>
>Quando o conteúdo e a elegibilidade de uma oferta são aprovados, o fluxo de trabalho de publicação (Notificação de oferta) é executado automaticamente e a oferta é ativada e disponibilizada em todos os espaços ativados.

* A lista completa de regras pode ser visualizada clicando em **[!UICONTROL Schedule and eligibility rules]**.

  ![Lista de regras de agendamento e qualificação com pesos e intervalos de datas, aberta na caixa de diálogo de aprovação.](assets/offer_validate_005.png)

* Para alterar as regras de elegibilidade, clique em **[!UICONTROL Reject]** e em **[!UICONTROL Eligibility approval]**.

  ![Caixa de diálogo de aprovação de qualificação com Rejeitar selecionado, um comentário e o botão Aprovação de qualificação.](assets/offer_validate_007.png)

  Os vários status são atualizados no painel de ofertas.

  ![Painel após a rejeição: a aprovação da qualificação foi rejeitada com o banner, o botão Enviar qualificação, A qualificação foi rejeitada.](assets/offer_validate_006.png)

* Para aceitar a elegibilidade da oferta, clique em **[!UICONTROL Approve eligibility]**.

  ![Botão Enviar qualificação abrindo a Ação na caixa de diálogo de oferta com as opções Aprovar e Rejeitar.](assets/offer_validate_008.png)

  Aprove a elegibilidade, adicione um comentário se necessário e clique em **[!UICONTROL Eligibility approval]**.

  ![Caixa de diálogo Aprovação de qualificação com Aprovar selecionada, um comentário inserido e o botão Aprovação de qualificação.](assets/offer_validate_009.png)

  Os vários status são atualizados no painel de ofertas.

  ![Painel mostrando a oferta com implantação pendente para o ambiente live, com Qualificação aprovada e Conteúdo aprovado.](assets/offer_validate_010.png)

## Rastreamento de aprovação {#approval-tracking}

O rastreamento de aprovação está disponível no painel de ofertas. Clique em **[!UICONTROL Hide/display logs]** para acessá-lo.

![Painel de ofertas com os logs de aprovação exibidos após clicar em Ocultar/exibir logs, listar ação, tipo e aprovador.](assets/offer_validate_012.png)

>[!NOTE]
>
>O rastreamento também está disponível na guia **[!UICONTROL Audit]** da oferta, com detalhes dos comentários dos revisores.

## Reiniciar a aprovação {#restart-the-approval}

Depois que a aprovação for iniciada, ela poderá ser reiniciada. Para fazer isso, siga estas instruções:

1. Clique em **[!UICONTROL Content approved]** no painel de ofertas.
1. Na janela **[!UICONTROL Edit]** que aparece, selecione a aprovação para reiniciar e clique em **[!UICONTROL Re-initialize approval to submit it again]**.
1. Confirme clicando em **[!UICONTROL Ok]**.

![Diário de aprovações na janela Editar com o link Reinicializar aprovação para enviá-lo novamente.](assets/offer_validate_013.png)

## Publicação da oferta {#publishing-the-offer}

Uma vez que o conteúdo e a elegibilidade de uma oferta tenham sido aprovados, a oferta é publicada por um fluxo de trabalho que é executado automaticamente para cada oferta cujo ciclo de aprovação foi concluído. O fluxo de trabalho **[!UICONTROL Offer notification]** também é executado a cada hora para sincronizar (se necessário) os espaços e categorias contidos no catálogo de ofertas do ambiente de design para o ambiente live.

O painel de controle disponível no ambiente de design contém informações sobre a publicação, incluindo o nome da oferta correspondente no ambiente live.

![Criar painel de ofertas: banner de data de implantação, link de Ofertas online com status Publicado, representação online.](assets/offer_golive_001.png)

Para exibir a oferta disponível no ambiente ativo, clique no rótulo da oferta: a oferta ativa tem um painel que contém todas as informações relevantes.

![Link para o painel de ofertas em tempo real, que mostra o status Online, seu ambiente e suas regras de agendamento e qualificação.](assets/offer_golive_002.png)

## Desabilitação de uma oferta {#disabling-an-offer}

Depois que a oferta for aprovada, você poderá desabilitá-la.

Para fazer isso, vá para o painel de controle de uma oferta online ou oferta aguardando para ficar online e clique em **[!UICONTROL Disable offer]**.

Você também pode desabilitar diretamente uma categoria indo até a guia **[!UICONTROL Eligibility]** e marcando a caixa **[!UICONTROL Enabled]**.

>[!NOTE]
>
>Quando uma oferta é excluída em um ambiente de design, ela é automaticamente desativada no ambiente online vinculado. Após um período de retenção de apresentações, as ofertas desativadas são excluídas do ambiente online.

![Implantação pendente do painel de ofertas, com o botão Desabilitar oferta usado para desativar a oferta.](assets/offer_preview_deactivate.png)
