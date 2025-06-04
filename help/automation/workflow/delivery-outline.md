---
product: campaign
title: Descrição da entrega
description: Saiba mais sobre a atividade do workflow do Delivery outline
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 100%

---

# Delivery outline{#delivery-outline}

A **descrição da entrega** permite usar uma descrição em um workflow de campanha. O outline deve ter sido criado antecipadamente na campanha.

Para configurar a atividade, basta marcar outline desejado e a data de contato planejada. É possível adicionar regras do filtro adicionando tipologias ou regras de tipologia.

## Exemplo: Inserção de uma oferta por meio de uma entrega outline {#example--inserting-an-offer-via-a-delivery-outline}

A atividade de **descrição da entrega**, disponível nos workflows da campanha, permite apresentar ofertas mencionadas em uma descrição da entrega na campanha atual em andamento.

>[!NOTE]
>
>O pacote de **Interaction** deve ser instalado.

1. Em um workflow, adicione uma atividade de descrição da entrega antes de adicionar uma atividade de entrega.
1. Na atividade de descrição da entrega, especifique a descrição que deseja usar.
1. Preencha os campos disponíveis de acordo com sua entrega.
1. Há dois casos possíveis:

   * Se desejar chamar o mecanismo de oferta, marque a caixa **[!UICONTROL Restrict the number of propositions selected]**. Especifique o espaço de oferta e o número de propostas que serão apresentadas na entrega.

     Os pesos da oferta e as regras de elegibilidade serão considerados pelo mecanismo de oferta.

   * Se não marcar a caixa, todas as ofertas na descrição da entrega serão apresentadas sem chamar o mecanismo de oferta.

   A pré-visualização leva em conta o número de ofertas especificadas na entrega. Ao executar um workflow, é o número especificado na descrição da entrega que é levada em conta.

   ![](assets/int_compo_offre_wf1.png)
