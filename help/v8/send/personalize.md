---
title: Introdução à personalização
description: Saiba como personalizar o conteúdo da mensagem
feature: Personalization
role: User
level: Beginner
source-git-commit: a8568e0c1e9af11b533b7d435691dc12cc0a2485
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 30%

---

# Introdução à personalização {#personalize-content}

Para aproveitar ao máximo cada campanha de marketing, o Adobe Campaign oferece uma maneira de fornecer conteúdo personalizado que fala para os clientes em seu nível. Com base nos dados do perfil, os recursos de personalização para criar uma experiência personalizada para diferentes grupos e indivíduos: é possível adaptar suas mensagens a cada recipient específico aproveitando os dados e as informações que você tem sobre elas. Pode ser seu primeiro nome, interesses, onde eles vivem, o que compraram, e muito mais.

O Adobe Campaign simplifica a personalização: você pode exibir diferentes tipos de conteúdo personalizado para cada recipient usando um único [modelo de email](create-templates.md). Nas mensagens transacionais, como confirmação de compra ou emails de abandono de carrinho, inclua informações de lista de produtos para cada indivíduo em um único modelo de email.


## Estratégias de personalização {#personalization-strategy}

Use o Campaign para criar conteúdo dinâmico e enviar mensagens personalizadas. Os recursos de personalização podem ser combinados para melhorar suas mensagens e criar uma experiência de usuário personalizada.

Você pode personalizar o conteúdo da mensagem ao:

* Inserção dinâmica **campos de personalização**

   Os campos de personalização são usados para personalização de primeiro nível das mensagens. Você pode selecionar qualquer campo disponível no banco de dados no editor de personalização. Para um delivery, é possível selecionar qualquer campo relacionado ao recipient, à mensagem ou ao delivery. Esses atributos de personalização podem ser inseridos na linha de assunto ou no corpo de suas mensagens. [Saiba mais](personalization-fields.md).

   A sintaxe a seguir insere a cidade do recipient no conteúdo: &lt;%= recipient.location.city %>.

* Inserção de predefinido **blocos de conteúdo**

   O Campaign vem com um conjunto de blocos de personalização que contêm uma renderização específica que você pode inserir nos deliveries. Por exemplo, você pode adicionar um logotipo, uma mensagem de saudação ou um link para a mirror page da mensagem. Os blocos de conteúdo estão disponíveis em uma entrada dedicada no editor de personalização. [Saiba mais](personalization-blocks.md).

* Criar **conteúdo condicional**

   Configure o conteúdo condicional para adicionar personalização dinâmica com base no perfil do recipient, por exemplo. Blocos de texto e/ou imagens são inseridos quando uma determinada condição é verdadeira. [Saiba mais](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Medidas de proteção e recomendações{#perso-guardrails}

### Tempo limite da personalização{#perso-timeout}

Para aumentar a proteção da entrega, é possível definir um período de tempo limite para a fase de personalização.

Na guia **[!UICONTROL Delivery]** de **[!UICONTROL Delivery properties]**, selecione um valor máximo em segundos na opção **[!UICONTROL Maximum personalization run time]**.

Durante a visualização ou envio, se a fase de personalização exceder o tempo máximo definido neste campo, o processo será anulado com uma mensagem de erro e o delivery falhará.

O valor padrão é de 5 segundos.

Se essa opção for definida como 0, não haverá limite de tempo para a fase de personalização.


### Variáveis internas{#internal-variables}

As variáveis a seguir são variáveis internas que podem ser usadas para personalização, mas não devem ser modificadas: **delivery**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue** e **proposition**.


## Tutorial em vídeo {#personalization-video}

Entenda os diferentes tipos de conteúdo dinâmico e saiba como criar e aplicar blocos de personalização e declarações condicionais a um delivery.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)