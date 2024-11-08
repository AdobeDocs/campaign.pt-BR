---
title: Introdução à personalização
description: Saiba como personalizar o conteúdo da mensagem
feature: Personalization
role: User
level: Beginner
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: 3ac2976839f084761ba56647b282062d8d457ff2
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 64%

---

# Introdução à personalização {#personalize-content}

Para aproveitar ao máximo cada campanha de marketing, o Adobe Campaign oferece uma maneira de fornecer conteúdo personalizado que fala com os clientes em seu nível. Com base nos dados do perfil, recursos de personalização para criar uma experiência personalizada para diferentes grupos e indivíduos: você pode adaptar suas mensagens a cada recipient específico, aproveitando os dados e as informações que tem sobre eles. Pode ser seu nome, interesses, onde vivem, o que compraram e muito mais.

O Adobe Campaign simplifica a personalização: você pode exibir diferentes tipos de conteúdo personalizado para cada destinatário usando um único [modelo de mensagem](create-templates.md). Em suas mensagens transacionais, como emails de confirmação de compra ou abandono de carrinho, inclua informações de listagens de produtos para cada indivíduo em um único modelo de email.


## Estratégias do Personalization {#personalization-strategy}

Use o Campaign para criar conteúdo dinâmico e enviar mensagens personalizadas. Os recursos de personalização podem ser combinados para melhorar suas mensagens e criar uma experiência do usuário personalizada.

Você pode personalizar o conteúdo da mensagem ao:

* Inserir **campos de personalização** dinâmicos

  Os campos de personalização são usados na personalização de primeiro nível das mensagens. Você pode selecionar qualquer campo disponível no banco de dados no editor de personalização. Para uma entrega, é possível selecionar qualquer campo relacionado ao destinatário, à mensagem ou à entrega. Esses atributos de personalização podem ser inseridos na linha de assunto ou no corpo das mensagens. [Saiba mais](personalization-fields.md).

  A sintaxe a seguir insere a cidade do destinatário no conteúdo: &lt;%= recipient.location.city %>.

* Inserção de **blocos de conteúdo** predefinidos

  O Campaign vem com um conjunto de blocos de personalização contendo uma renderização específica que você pode inserir nas entregas. Por exemplo, você pode adicionar um logotipo, uma mensagem de saudação ou um link para a mirror page da mensagem. Os blocos de conteúdo estão disponíveis em uma entrada dedicada no editor de personalização. [Saiba mais](personalization-blocks.md).

* Criação de **conteúdo condicional**

  Configure o conteúdo condicional para adicionar personalização dinâmica com base no perfil do destinatário, por exemplo. Blocos de texto e/ou imagens são inseridos quando uma determinada condição for satisfeita. [Saiba mais](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Medidas de proteção e recomendações{#perso-guardrails}

### Tempo limite do Personalization {#perso-timeout}

Para aumentar a proteção da entrega, é possível definir um período de tempo limite para a fase de personalização.

Na guia **[!UICONTROL Delivery]** de **[!UICONTROL Delivery properties]**, selecione um valor máximo em segundos na opção **[!UICONTROL Maximum personalization run time]**.

Durante a pré-visualização ou envio, se a fase de personalização exceder o tempo máximo definido nesse campo, o processo será interrompido com uma mensagem de erro e o delivery falhará.

O valor padrão é de 5 segundos.

Se essa opção for definida como 0, não haverá limite de tempo para a fase de personalização.


### Variáveis internas{#internal-variables}

As variáveis a seguir são variáveis internas que podem ser usadas para personalização, mas não devem ser modificadas: **delivery**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue** e **proposition**.


## Tutorial em vídeo {#personalization-video}

Entenda os diferentes tipos de conteúdo dinâmico e saiba como criar e aplicar blocos de personalização e declarações condicionais a uma entrega.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)
