---
title: Trabalhar com target mappings
description: Saiba como usar e criar target mappings
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
exl-id: 5256fc15-1878-4064-9c75-7876a3826b83
TQID: https://experienceleague.adobe.com/ArJJi775HkzlpPOu-SoKg8UTcYTperTC1ySmXrHHpJg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 376
ht-degree: 38%

---

# Trabalhar com target mappings{#gs-target-mappings}

Por padrão, os modelos de entrega de email e SMS têm como alvo **[!UICONTROL Recipients]**. O target mapping, portanto, usa os campos da tabela **nms:recipient**.

Para notificações por push, o target mapping padrão é **Aplicativos do assinante (nms:appSubscriptionRcp)**, que está vinculado à tabela de destinatários.

Você pode usar outros target mappings para seus deliveries ou criar um novo.

## Mapeamentos de destino incorporados {#ootb-mappings}

O Adobe Campaign vem com os seguintes target mappings incorporados:

| Nome | Use para | Esquema |
|---|---|---|
| Destinatários | Entregar aos destinatários (tabela de destinatários integrada) | nms:recipient |
| Visitantes | Enviar delivery aos visitantes cujos perfis foram coletados por meio de referência (marketing viral), por exemplo. | mns:visitor |
| Subscrições | Entregar aos destinatários que assinam um serviço de informações, como um boletim informativo | nms:subscription |
| Assinaturas do visitante | Entregar aos visitantes que são inscritos em um serviço de informações | nms:visitorSub |
| Operadores | Entregar aos operadores do Adobe Campaign | nms:operator |
| Arquivo externo | Entregar por meio de um arquivo que contenha todas as informações necessárias para a entrega | Nenhum esquema vinculado, nenhum target inserido |
| Aplicativos de assinante | Enviar delivery aos recipients que assinaram um aplicativo | nms:appSubscriptionRcp |


## Criar um target mapping {#new-mapping}

Você também pode criar um target mapping. Talvez seja necessário adicionar um target mapping personalizado, por exemplo, se:

* usar uma tabela de recipient personalizada,
* configure uma dimensão de filtro diferente da targeting dimension integrada na tela target mapping.

Saiba mais sobre tabelas de destinatários personalizadas em [esta página](../dev/custom-recipient.md).

O assistente de criação de target mapping do Adobe Campaign ajuda a criar todos os esquemas necessários para usar seu target mapping personalizado.

1. Navegue até **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** no Adobe Campaign Explorer.

1. Crie um novo target mapping e selecione seu esquema personalizado como o targeting dimension.

   ![](assets/new-target-mapping.png)


1. Indique os campos onde as informações do perfil são armazenadas: sobrenome, nome, email, endereço, etc.

   ![](assets/wf_new_mapping_define_join.png)

1. Especifique os parâmetros para armazenamento de informações, incluindo o sufixo dos schemas de extensão para que sejam facilmente identificáveis.

   ![](assets/wf_new_mapping_define_names.png)

   Você pode escolher se deseja armazenar exclusões (**excludelog**), com mensagens (**broadlog**) ou em uma tabela separada.

   Você também pode escolher se deseja gerenciar o rastreamento para esse mapeamento de entrega (**trackinglog**).

1. Em seguida, selecione as extensões a serem consideradas. O tipo de extensão depende das configurações e dos complementos do Campaign.

   ![](assets/wf_new_mapping_define_extensions.png)

   Clique no botão **[!UICONTROL Save]** para iniciar a criação de mapeamento de entrega: todas as tabelas vinculadas são criadas automaticamente com base nos parâmetros selecionados.
