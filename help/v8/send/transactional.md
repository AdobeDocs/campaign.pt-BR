---
title: Mensagens transacionais do Campaign
description: Introdução a mensagens transacionais
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 59%

---

# Introdução a mensagens transacionais{#send-transactional-messages}

O envio de mensagens transacionais (Centro de mensagens) é um módulo do Campaign criado para gerenciar mensagens por disparo. Essas notificações são geradas a partir de eventos acionados dos sistemas de informações e podem ser: fatura, confirmação de pedido, confirmação de remessa, alteração de senha, notificação de indisponibilidade de produto, extrato de conta, criação de conta de site etc.

>[!NOTE]
>
>Como usuário do Managed Cloud Services, [contate a Adobe](../start/campaign-faq.md#support){target="_blank"} para configurar as mensagens transacionais do Campaign em seu ambiente.

As mensagens transacionais são usadas para enviar:

* notificações, como confirmações de pedidos ou redefinições de senha, por exemplo
* uma resposta individual em tempo real a uma ação do cliente
* conteúdo não promocional

As configurações de mensagens transacionais estão detalhadas em [esta seção](../config/transactional-msg-settings.md).

Entenda a arquitetura de mensagens transacionais em [esta página](../architecture/architecture.md#transac-msg-archi).

## Princípio operacional das mensagens transacionais {#transactional-messaging-operating-principle}

O módulo de mensagens transacionais do Adobe Campaign é integrado a um sistema de informações que retorna eventos que serão transformados em mensagens transacionais personalizadas. Essas mensagens podem ser enviadas individualmente ou em lotes por email, SMS ou notificações por push.

Por exemplo, imagine que você é uma empresa com um site onde os clientes podem comprar produtos.

O Adobe Campaign permite enviar um email de notificação para clientes que adicionaram produtos ao carrinho. Quando um deles sai do site sem concluir a compra (evento externo que aciona um evento do Campaign), um email de abandono de carrinho é enviado automaticamente a eles (entrega de mensagem transacional).

As principais etapas para colocar isso em prática são detalhadas abaixo:

1. [Crie um tipo de evento](#create-event-types).
1. [Criar o modelo de mensagem](transactional-template.md#create-message-template). Você deve vincular um evento à sua mensagem durante essa etapa.
1. [Testar a mensagem](transactional-template.md#test-message-template).
1. [Publicar o modelo da mensagem](transactional-template.md#publish-message-template).

Depois de criar e publicar o modelo de mensagem transacional, se um evento correspondente for acionado, os dados relevantes serão enviados para o Campaign por meio dos [métodos SOAP](../send/event-description.md) PushEvent e PushEvents, e a entrega será enviada aos recipients direcionados.

## Criar tipos de evento {#create-event-types}

Para garantir que cada evento possa ser alterado em uma mensagem personalizada, primeiro é necessário criar **tipos de evento**.

Ao [criar um modelo de mensagem](#create-message-template), você selecionará o tipo de evento que corresponde à mensagem que deseja enviar.

>[!CAUTION]
>
>Você deve criar tipos de evento antes de poder usá-los em modelos de mensagem.

Para criar tipos de evento que serão processados pelo Adobe Campaign, siga as etapas abaixo:

1. Navegue até a pasta **[!UICONTROL Administration > Platform > Enumerations]** do explorador do Campaign.
1. Selecione a enumeração **[!UICONTROL Event type]** na lista.
1. Clique em **[!UICONTROL Add]** para criar um valor enumeração. Pode ser uma confirmação de pedido, uma alteração de senha, uma alteração de entrega de pedido etc.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Cada tipo de evento deve corresponder a um valor na enumeração **[!UICONTROL Event type]**.

1. Após a criação dos valores da lista discriminada, faça logoff e logon novamente na instância para que a criação seja efetivada.

>[!NOTE]
>
>Saiba mais sobre [enumerações](../config/enumerations.md).

Para a próxima etapa, saiba como [criar e publicar seu modelo para mensagens transacionais](transactional-template.md).
