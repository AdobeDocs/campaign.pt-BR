---
product: campaign
title: Alterações futuras no Canal de notificação por push
description: Alterações futuras no Canal de notificação por push
hide: true
hidefromtoc: true
source-git-commit: 70d1e7336cce7660890b13def5efcb614c0dc12e
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 3%

---

# Alterações futuras no Canal de notificação por push {#push-upgrade}

Há alterações importantes no serviço Firebase Cloud Messaging (FCM) que podem afetar sua implementação do Adobe Campaign Classic.

Como parte do esforço contínuo da Google para melhorar seus serviços, as APIs herdadas do FCM serão descontinuadas em junho de 2024 ([Protocolo HTTP do Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging/http-server-ref))

Essas APIs estão atualmente integradas ao Adobe Campaign Classic para enviar mensagens de notificação por push. Entendemos que muitos de nossos clientes, como você, dependem desses serviços para suas campanhas de marketing e necessidades de comunicação e, especialmente, para dispositivos Android.

## Você será afetado?

* **Usuários da API HTTP (herdada)**: se qualquer uma de suas campanhas de notificação por push ativas utilizar a API HTTP (herdada), sua configuração será diretamente afetada por essa alteração. Recomendamos que você analise suas configurações atuais e se prepare para a migração para as APIs mais recentes.

* **Boas notícias para usuários da API HTTP v1**: se a configuração usar exclusivamente a API HTTP v1 para notificações por push do Android, você já estará em conformidade e nenhuma outra ação será necessária da sua parte.

## O Que Estamos Fazendo?

* **Plano de transição**: Nossa equipe está trabalhando ativamente no desenvolvimento de um plano de transição abrangente. Isso garantirá que, quando necessário, você possa atualizar sua implementação para as APIs do FCM mais recentes já disponíveis nas versões recentes do Adobe Campaign e com o mínimo de interrupção nas campanhas.

* **Instruções detalhadas**: forneceremos um guia passo a passo e outros recursos para facilitar um processo de transição suave.

* **Suporte**: nossa Equipe de suporte ao cliente estará disponível para ajudá-lo durante essa transição. Também podemos realizar webinários e sessões de capacitação para abordar os aspectos técnicos e as práticas recomendadas para a transição.

## O que esperamos de você?

* **Mantenha-se informado**: Fique de olho na sua caixa de entrada para obter mais comunicações conosco, incluindo o plano de transição detalhado.

* **Revisar configuração atual**: dedique este tempo para revisar sua configuração e personalização atuais no Adobe Campaign Classic, de modo que você esteja preparado para fazer as alterações necessárias, se necessário.

* **Entre em contato**: Se você tiver dúvidas ou preocupações imediatas, entre em contato com nossa equipe de suporte.

## Etapas de implementação

Nas próximas semanas, compartilharemos mais detalhes sobre o plano de transição para APIs herdadas do FCM, incluindo linhas do tempo e itens de ação. Tenha certeza de que nosso objetivo principal é tornar essa transição o mais simples possível para você e sua equipe.

Agradecemos sua atenção e sua compreensão à medida que nos adaptamos a essas mudanças. Seu sucesso é nossa principal prioridade e temos o compromisso de apoiá-lo em todas as etapas do caminho.

Para que você possa antecipar a alteração, estas são as etapas gerais que serão necessárias para migrar sua configuração de push da API HTTP (herdada) para a API HTTPv1 do FCM.

### Atualização da build

* Campaign Classic: o suporte a HTTPv1 foi adicionado à versão 20.3.1. Se você estiver usando uma versão anterior, é necessário primeiro atualizar para a build de Campaign Classic mais recente.

* Campaign v8: HTTPv1 é compatível com todas as versões do Campaign v8. Nenhuma atualização necessária.

### Servidor de marketing

As alterações de configuração podem ser realizadas pelo cliente/parceiro.

1. Primeiro, você precisa extrair o arquivo JSON. O arquivo JSON da conta do serviço do SDK de administrador do Firebase é necessário para mover o aplicativo móvel para HTTPv1. Consulte esta [página](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. Navegue até a lista de **Serviços e assinaturas**.

1. Localize todos os aplicativos móveis usando a versão da API HTTP (herdada).

1. Para cada um desses aplicativos móveis, defina o **Versão da API** para HTTPv1 e siga as instruções de configuração detalhadas na [documentação](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

>[!NOTE]
>
>A mudança para a API HTTPv1 será considerada para novos deliveries. Os deliveries em repetição, em andamento e em uso ainda usarão a API HTTP (herdada).

### Servidor Mid-Sourcing

Não há alterações necessárias.

### Servidor de execução em tempo real

Você precisa entrar em contato com o suporte da Adobe Campaign para isso. O procedimento de migração é o mesmo do servidor de marketing.

### Sistema operacional Android e aplicativo móvel Android

Não há alterações específicas necessárias no código dos aplicativos móveis do Android e o comportamento da notificação não deve ser alterado.

No entanto, HTTPv1 está introduzindo três novos elementos de carga:

| Nome | Valor padrão |
|---|---|
| adesivo | Falso |
| prioridade | Padrão |
| visibilidade | Falso |
| adesivo | Privado |
