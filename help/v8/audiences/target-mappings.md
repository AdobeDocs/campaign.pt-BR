---
title: Trabalhar com target mappings
description: Saiba como usar e criar target mappings
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 40%

---

# Trabalhar com target mappings{#gs-target-mappings}

Por padrão, templates de delivery têm como target **[!UICONTROL Recipients]**. O target mapping, portanto, usa os campos da tabela **nms:recipient.**

Você pode usar outros target mappings para seus deliveries ou criar um novo target mapping.

## Mapeamentos de target incorporados {#ootb-mappings}

O Adobe Campaign vem com os seguintes target mappings incorporados:

| Nome | Uso para | Schema |
|---|---|---|
| Recipients | Enviar delivery aos recipients (tabela de recipients integrada) | nms:recipient |
| Visitantes | Enviar delivery aos visitantes cujos perfis foram coletados por meio de referência (marketing viral) para o ex. | mns:visitor |
| Subscrições | Enviar delivery aos recipients que assinam um serviço de informações, como um boletim informativo | nms:subscription |
| Assinaturas do visitante | Enviar delivery aos visitantes que são inscritos em um serviço de informações | nms:visitorSub |
| Operadores | Enviar delivery aos operadores do Adobe Campaign | nms:operator |
| Arquivo externo | Enviar delivery por meio de um arquivo que contenha todas as informações necessárias para o delivery | Nenhum schema vinculado, nenhum target inserido |

## Criar um target mapping {#new-mapping}

Você também pode criar um target mapping. Talvez seja necessário adicionar um target mapping personalizado, por exemplo, se:

* use uma tabela de recipient personalizada,
* você configura uma dimensão de filtro diferente do targeting dimension incorporado na tela de target mapping.

Saiba mais sobre tabelas de destinatários personalizadas em [esta página](../dev/custom-recipient.md).

O assistente de criação de target mapping do Adobe Campaign ajuda a criar todos os esquemas necessários para usar seu target mapping personalizado.

1. Navegue até **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** do Adobe Campaign Explorer.

1. Crie um novo target mapping e selecione seu schema personalizado como o targeting dimension.

   ![](assets/new-target-mapping.png)


1. Indique os campos onde as informações do perfil são armazenadas: sobrenome, nome, email, endereço etc.

   ![](assets/wf_new_mapping_define_join.png)

1. Especifique os parâmetros para armazenamento de informações, incluindo o sufixo dos schemas de extensão para que sejam facilmente identificáveis.

   ![](assets/wf_new_mapping_define_names.png)

   Você pode escolher se deseja armazenar exclusões (**excludelog**), com mensagens (**broadlog**) ou em uma tabela separada.

   Você também pode escolher se deseja gerenciar o rastreamento para esse mapeamento de delivery (**trackinglog**).

1. Em seguida, selecione as extensões a serem consideradas. O tipo de extensão depende das configurações e complementos do Campaign.

   ![](assets/wf_new_mapping_define_extensions.png)

   Clique no botão **[!UICONTROL Save]** para iniciar a criação de mapeamento de delivery: todas as tabelas vinculadas são criadas automaticamente com base nos parâmetros selecionados.

