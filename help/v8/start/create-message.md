---
title: Introdução a mensagens
description: Introdução a mensagens
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: c508c80bea39e4fc32786d92d06651a1f91ca697
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 100%

---

# Introdução a mensagens {#gs-ac-audiences}

## Canais de entrega {#gs-ac-channels}

Com o Adobe Campaign, você pode enviar campanhas entre canais, incluindo e-mails, SMS, notificações push e correspondências diretas e medir a eficiência usando vários relatórios dedicados. Essas mensagens são projetadas e enviadas em entregas, além disso podem ser personalizadas para cada destinatário.

As funcionalidades principais incluem definição de metas, definição e personalização de mensagens, execução de comunicações e relatórios operacionais associados. O principal ponto de acesso funcional é o assistente de entrega. Esse ponto de acesso leva a vários recursos cobertos pelo Adobe Campaign.

O Adobe Campaign v8 vem com os seguintes canais de entrega:

* **Canal de email**: entregas de email permitem enviar emails personalizados para a população do target. [Saiba mais](#gs-channel-email)

* **Canais móveis**: entregas em canais móveis permitem enviar mensagens personalizadas em dispositivos móveis para a população do público-alvo. [Saiba mais](#gs-channel-sms)

* **Canal do aplicativo móvel**: as entregas por aplicativo móvel permitem enviar notificações para dispositivos iOS e Android.  [Saiba mais](#gs-channel-push)

* **Canal de correspondência direta**: entregas de correspondência direta permitem gerar um arquivo de extração que contém dados sobre a população de público-alvo. [Saiba mais](#gs-channel-direct)


  Outros canais são descritos [nesta página](#other-channels).

  >[!NOTE]
  >
  >O número de canais disponíveis depende do seu contrato. Verifique o contrato de licença.

## Escolha seu canal {#gs-channel}

### Canal de email {#gs-channel-email}

O [Canal de email](../send/direct-mail.md) é um dos canais principais do Adobe Campaign, permitindo agendar e enviar emails personalizados para targets específicos.

Você pode enviar diferentes tipos de emails:

* Emails de envio único: emails que você pode enviar uma vez para um target definido. Normalmente, eles são usados para promover um conteúdo específico que seria preparado e enviado apenas uma vez (boletim informativo, email promocional etc.).
* Emails recorrentes: em uma campanha, envie o mesmo email regularmente e agregue cada envio e seus relatórios periodicamente. O mesmo email é enviado, mas geralmente para um target diferente, com base no target qualificado do dia do envio. Um exemplo comum é um email de aniversário. Para obter mais informações, consulte [Entregas recorrentes](../../automation/workflow/recurring-delivery.md).
* Emails transacionais: emails unitários que são acionados com base no comportamento dos clientes. Consulte [Mensagens transacionais](../send/transactional.md).

Para saber mais sobre o uso da entrega e recomendações, consulte [Práticas recomendadas de entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=pt-BR#sending-messages){target="_blank"} do Adobe Campaign Classic

Para obter mais informações sobre os tipos diferentes de entrega, consulte [esta página](#types-of-deliveries).

### Canal móvel {#gs-channel-sms}

O Adobe Campaign permite que você faça entrega de mensagens por [SMS](../send/sms/sms.md) e [LINE](../send/line.md) em celulares.

Para mensagens SMS, você poderá criar, modificar e personalizar mensagens somente no formato de texto. Você também poderá visualizar suas mensagens SMS antes de enviá-las.

Para mensagens por LINE, você poderá enviar texto ou imagens e links.

Para fazer entrega de mensagens SMS ou LINE a um celular, você vai precisar de:

* Uma conta externa configurada no canal **[!UICONTROL Mobile (SMS)]** ou no canal **[!UICONTROL LINE]**.
* Um modelo de entrega por SMS ou LINE que esteja vinculado corretamente a essa conta externa.


### Canal de notificação por push {#gs-channel-push}

É possível usar o Adobe Campaign para enviar [notificações por push](../send/push.md) personalizadas e segmentadas em dispositivos móveis iOS e Android, por meio de aplicativos dedicados. Depois que as etapas de configuração e integração forem executadas, as entregas de iOS e de Android poderão ser criadas e enviadas com o Adobe Campaign. Você também pode projetar e enviar notificações avançadas com imagens ou vídeos para dispositivos Android.

### Canal de correspondência direta {#gs-channel-direct}

A [Correspondência direta](../send/direct-mail.md) é um canal offline que permite criar, personalizar e gerar um arquivo externo para compartilhar com seus provedores de correspondência direta. Use este canal para orquestrar canais online e offline nas jornadas do cliente.

Quando você prepara uma entrega de correspondência direta, o Adobe Campaign gera um arquivo incluindo todos os perfis direcionados e as informações de contato escolhidas (endereço postal por exemplo). Você poderá enviar esse arquivo para seu provedor de correspondência direta que irá cuidar do envio real.


### Outros canais {#other-channels}

O Adobe Campaign também vem com um modelo de entrega por telefone, que é usado para criar entregas externas. A utilização desse canal implica que você implemente metodologias específicas para processar arquivos de saída. As etapas de configuração são as mesmas do [Canal de correspondência direta](../send/direct-mail.md).

>[!NOTE]
>
>O canal de telefone não é um canal integrado. A implementação requer o envolvimento da Adobe Consulting ou de um Parceiro da Adobe. Entre em contato com seu representante da Adobe para obter mais informações.

As entregas do tipo “Outros” usam um modelo técnico específico que não executa um processo: isso permite gerenciar ações de marketing executadas fora da plataforma Adobe Campaign.

Este canal não tem nenhum mecanismo específico. É um canal genérico que tem sua própria opção de roteamento de conta externa, tipo de modelo de entrega e atividade de fluxo de trabalho de campanha, como qualquer outro canal de comunicação disponível no Adobe Campaign. Esse canal foi projetado apenas para fins descritivos, por exemplo, para definir entregas para as quais você deseja manter um rastreamento do público-alvo de uma campanha executada em uma ferramenta diferente do Adobe Campaign.

## Escolha o tipo de entrega {#types-of-deliveries}

Existem três tipos de objetos de entrega no Campaign:

### Entrega única {#single-delivery}

Uma **entrega** é um objeto de entrega independente executado uma vez. Ele pode ser duplicado, preparado novamente, mas, desde que esteja no seu estado final (cancelado, interrompido, concluído), não poderá ser reutilizado.

As entregas podem ser criadas a partir da lista de entregas ou em um fluxo de trabalho através de uma atividade de [Entrega](../../automation/workflow/delivery.md) .

Os workflows também fornecem atividades de entrega específicas de acordo com o tipo de canal que você deseja usar. Para obter mais informações sobre essas atividades, consulte [esta seção](../../automation/workflow/cross-channel-deliveries.md).

### Entrega recorrente {#recurring-delivery}

Uma **entrega recorrente** está disponível no contexto de um fluxo de trabalho. Ela permite criar uma nova entrega sempre que a atividade é executada. Isso evita que você crie uma nova entrega para tarefas recorrentes. Como exemplo, se você executar esse tipo de atividade uma vez por mês, acabará com 12 entregas após um ano.

As entregas recorrentes são criadas em workflows através da [atividade Entrega recorrente.](../../automation/workflow/recurring-delivery.md) Um exemplo dessa atividade que está sendo usada é apresentado nesta seção: [Criação de uma entrega recorrente em um workflow de direcionamento](../../automation/workflow/send-a-birthday-email.md).

### Entrega contínua {#continuous-delivery}

Uma **entrega contínua** está disponível no contexto de um fluxo de trabalho. Ela permite que você adicione novos destinatários a uma entrega já existente, o que evita a necessidade de criar uma nova entrega a cada execução.

Se uma informação na entrega for alterado (conteúdo, nome, etc.), um novo objeto de entrega será criado na execução da entrega. Se nenhuma informação for alterada, o mesmo objeto da entrega será reutilizado e os logs de entrega e rastreamento serão adicionados no mesmo objeto.

Como exemplo, se você executar esse tipo de atividade uma vez por mês, acabará com uma única entrega após um ano (desde que não tenha feito nenhuma alteração na entrega).

As entregas contínuas são criadas em workflows através da [atividade Entrega contínua](../../automation/workflow/continuous-delivery.md).


## Escolha como enviar suas mensagens{#gs-send-msg}

Depois que a mensagem for criada e o conteúdo testado, você poderá escolher como deseja enviá-la. O Campaign oferece um conjunto de recursos para:

* Enviar mensagens manualmente para o target principal

  ![](assets/send-email.png)

  Saiba como enviar mensagens [nesta seção](../send/send.md)

* Enviar mensagens associadas a uma [campanha de marketing](campaigns.md)

  ![](assets/deliveries-in-a-campaign.png)

  Saiba como enviar mensagens no contexto de uma campanha [nesta seção](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=pt-BR){target="_blank"}

* Enviar mensagens por meio de um [fluxo de trabalho](../config/workflows.md)

  ![](assets/send-in-a-wf.png)

  Saiba como automatizar entregas de email [nesta página](../../automation/workflow/delivery.md)

* [Acionar mensagens](../send/transactional.md) de um evento

  O envio de mensagens transacionais (Centro de mensagens) é o módulo do Campaign criado para gerenciar mensagens por acionador.

  Saiba mais sobre o recurso de mensagens transacionais [nesta seção](../architecture/architecture.md#transac-msg-archi)

  As etapas para configurar e enviar mensagens transacionais são detalhadas [nesta página](../send/transactional.md)

* Agendar suas mensagens

  ![](assets/schedule-send.png)

  Saiba como agendar o envio de suas entregas [nesta página](../send/configure-and-send.md)

  Consulte também [Caso de uso: saiba como agendar e enviar um email de aniversário](../../automation/workflow/send-a-birthday-email.md)


## Adicionar personalização{#personalization}

As mensagens entregues pelo Adobe Campaign podem ser personalizadas de várias maneiras. [Saiba mais sobre os recursos de personalização](../send/personalize.md)

Você pode:

* Inserir campos de personalização dinâmicos. [Saiba mais](../send/personalization-fields.md)
* Inserir blocos de personalização predefinidos. [Saiba mais](../send/personalization-blocks.md)
* Criar conteúdo condicional. [Saiba mais](../send/conditions.md)


## Logs de rastreamento e entrega{#gs-tracking-logs}

O monitoramento de entregas após serem enviados é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes. Você pode monitorar após enviar uma entrega, bem como entender como as falhas de entrega e as quarentenas são gerenciadas.

Saiba como monitorar suas entregas na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=pt-BR#sending-messages){target="_blank"}

