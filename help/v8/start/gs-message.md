---
title: Introdução a mensagens
description: Introdução a mensagens
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a523e76d-776c-47d3-9c15-34241cee1092
source-git-commit: 110a2cac920ca3087f6fcb3cab8474729f6075be
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 74%

---

# Introdução a mensagens {#gs-ac-msg}

Com o Adobe Campaign, você pode enviar campanhas entre canais, incluindo e-mails, SMS, notificações push e correspondências diretas e medir a eficiência usando vários relatórios dedicados. Essas mensagens são projetadas e enviadas em entregas, e podem ser personalizadas para cada destinatário.

As funcionalidades principais incluem direcionamento, definição e personalização de mensagens, execução de comunicações e os relatórios operacionais associados.

## Casos de uso {#gs-ac-delivery}

Para enviar mensagens, você deve criar um delivery. O modo de criação do delivery depende do seu caso de uso.

>[!NOTE]
>
>Ao criar um delivery, você deve selecionar um template. Os modelos padrão estão disponíveis para cada canal. Saiba mais sobre modelos de entrega em [esta página](../send/create-templates.md).

1. **Mensagens únicas** - Você pode enviar mensagens únicas para um público-alvo. Saiba como enviar sua primeira mensagem em [esta seção](create-message.md).

   ![](assets/send-email.png)

1. **Mensagens em uma campanha de marketing** - Você pode enviar mensagens no contexto de uma [campanha de marketing](campaigns.md), definir um processo de aprovação, enviá-las e rastreá-las em um painel consolidado. Saiba mais em [esta seção](../../automation/campaigns/marketing-campaign-deliveries.md).

   ![](assets/deliveries-in-a-campaign.png)

1. **Mensagens em um fluxo de trabalho** - Você pode enviar mensagens por meio de um [fluxo de trabalho](../config/workflows.md) e automatizar suas entregas. Saiba mais em [esta página](../../automation/workflow/delivery.md).

   ![](assets/send-in-a-wf.png)

1. **Mensagens acionadas** - Você pode [Acionar mensagens](../send/transactional.md) a partir de um evento. As mensagens transacionais (Centro de mensagens) são o módulo do Campaign criado para gerenciar mensagens de acionador. As etapas para configurar e enviar mensagens transacionais são detalhadas [nesta página](../send/transactional.md)

## Canais de comunicação {#gs-channel}

O Adobe Campaign v8 vem com os canais de entrega listados abaixo. Os canais disponíveis em seu ambiente dependem do seu contrato. Verifique o contrato de licença.

* **Canal de email**: entregas de email permitem enviar emails personalizados para a população do target. [Saiba mais](../send/email.md)

* **Canais móveis**: entregas em canais móveis permitem enviar mensagens personalizadas em dispositivos móveis para a população do público-alvo. Você pode enviar mensagens de [SMS](../send/sms/sms.md) e [LINE](../send/line/line.md) em dispositivos móveis.

* **Canal de aplicativo móvel**: você pode usar o Adobe Campaign para enviar [notificações por push](../send/push.md) personalizadas e segmentadas em dispositivos móveis iOS e Android, por meio de aplicativos dedicados. Depois que as etapas de configuração e integração forem executadas, as entregas de iOS e de Android poderão ser criadas e enviadas com o Adobe Campaign. Você também pode projetar e enviar notificações avançadas com imagens ou vídeos para dispositivos Android.

* **Canal de correspondência direta**: [A correspondência direta](../send/direct-mail.md) é um canal offline que permite criar, personalizar e gerar um arquivo externo para compartilhar com seus provedores de correspondência direta. Use este canal para orquestrar canais online e offline nas jornadas do cliente.

  Quando você prepara uma entrega de correspondência direta, o Adobe Campaign gera um arquivo incluindo todos os perfis direcionados e as informações de contato escolhidas (endereço postal por exemplo). Você poderá enviar esse arquivo para seu provedor de correspondência direta que irá cuidar do envio real.


* **Outros canais**: o Adobe Campaign também vem com um modelo de entrega de telefone, que é usado para criar entregas externas. A utilização desse canal implica que você implemente metodologias específicas para processar arquivos de saída. As etapas de configuração são as mesmas do [Canal de correspondência direta](../send/direct-mail.md).

  >[!NOTE]
  >
  >O canal de telefone não é um canal integrado. A implementação requer o envolvimento da Adobe Consulting ou de um Parceiro da Adobe. Entre em contato com seu representante da Adobe para obter mais informações.

  As entregas do tipo “Outros” usam um modelo técnico específico que não executa um processo: isso permite gerenciar ações de marketing executadas fora da plataforma Adobe Campaign.

  Este canal não tem nenhum mecanismo específico. É um canal genérico que tem sua própria opção de roteamento de conta externa, tipo de modelo de entrega e atividade de fluxo de trabalho de campanha, como qualquer outro canal de comunicação disponível no Adobe Campaign. Esse canal foi projetado apenas para fins descritivos, por exemplo, para definir entregas para as quais você deseja manter um rastreamento do público-alvo de uma campanha executada em uma ferramenta diferente do Adobe Campaign.

## Tipos de entrega {#types-of-deliveries}

Existem três tipos de objetos de entrega no Campaign:

### Entrega única {#single-delivery}

Uma **entrega** é um objeto de entrega independente executado uma vez. Ele pode ser duplicado, preparado novamente, mas, desde que esteja no seu estado final (cancelado, interrompido, concluído), não poderá ser reutilizado.

As entregas podem ser criadas a partir da lista de entregas ou em um fluxo de trabalho através de uma atividade de [Entrega](../../automation/workflow/delivery.md) .

Os fluxos de trabalho também fornecem atividades de entrega específicas de acordo com o tipo de canal que você deseja usar. Para obter mais informações sobre essas atividades, consulte [esta seção](../../automation/workflow/cross-channel-deliveries.md).

### Entrega recorrente {#recurring-delivery}

Uma **entrega recorrente** está disponível no contexto de um fluxo de trabalho. Ela permite criar uma nova entrega sempre que a atividade é executada. Isso evita que você crie uma nova entrega para tarefas recorrentes. Como exemplo, se você executar esse tipo de atividade uma vez por mês, acabará com 12 entregas após um ano.

As entregas recorrentes são criadas em fluxos de trabalho através da [atividade Entrega recorrente.](../../automation/workflow/recurring-delivery.md) Um exemplo dessa atividade que está sendo usada é apresentado nesta seção: [Criação de uma entrega recorrente em um fluxo de trabalho de segmentação](../../automation/workflow/send-a-birthday-email.md).

### Entrega contínua {#continuous-delivery}

Uma **entrega contínua** está disponível no contexto de um fluxo de trabalho. Ela permite que você adicione novos destinatários a uma entrega já existente, o que evita a necessidade de criar uma nova entrega a cada execução.

Se uma informação na entrega for alterado (conteúdo, nome, etc.), um novo objeto de entrega será criado na execução da entrega. Se nenhuma informação for alterada, o mesmo objeto da entrega será reutilizado e os logs de entrega e rastreamento serão adicionados no mesmo objeto.

Como exemplo, se você executar esse tipo de atividade uma vez por mês, acabará com uma única entrega após um ano (desde que não tenha feito nenhuma alteração na entrega).

As entregas contínuas são criadas em fluxos de trabalho através da [atividade Entrega contínua](../../automation/workflow/continuous-delivery.md).

## Recursos do Personalization {#personalization}

As mensagens entregues pelo Adobe Campaign podem ser personalizadas de várias maneiras. [Saiba mais sobre os recursos de personalização](../send/personalize.md)

Você pode:

* Inserir campos de personalização dinâmicos. [Saiba mais](../send/personalization-fields.md)
* Inserir blocos de personalização predefinidos. [Saiba mais](../send/personalization-blocks.md)
* Criar conteúdo condicional. [Saiba mais](../send/conditions.md)


## Rastreamento e monitoramento {#gs-tracking-logs}

O monitoramento de entregas após serem enviados é uma etapa essencial para garantir que as campanhas de marketing sejam eficientes e atinjam os clientes. Você pode monitorar após enviar uma entrega, bem como entender como as falhas de entrega e as quarentenas são gerenciadas.

Saiba como monitorar suas entregas na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=pt-BR#sending-messages){target="_blank"}
