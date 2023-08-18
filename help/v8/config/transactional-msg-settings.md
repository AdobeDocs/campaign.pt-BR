---
title: Configurações de mensagens transacionais do Campaign
description: Configurações de mensagens transacionais do Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 42%

---

# Configurações de mensagens transacionais

As mensagens transacionais (Centro de mensagens) são um módulo do Campaign criado para gerenciar mensagens acionadas. Saiba mais sobre Mensagens transacionais no [nesta seção](../send/transactional.md).

Entender a arquitetura de mensagens transacionais no [esta página](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) Como usuário do Managed Cloud Service, [Adobe de contato](../start/campaign-faq.md#support) para instalar e configurar as mensagens transacionais do Campaign em seu ambiente.

## Definir permissões

Para criar novos usuários para as instâncias de execução do Centro de mensagens hospedadas na Adobe Cloud, você precisará entrar em contato com o Atendimento ao cliente da Adobe. Os usuários do Centro de mensagens são operadores específicos que exigem permissões dedicadas para acessar pastas de ‘eventos em tempo real’ (nmsRtEvent).

## Extensões do esquema

Todas as extensões de esquema feitas nos esquemas usados por [Workflows técnicos do Centro de mensagens](#technical-workflows) nas instâncias de controle ou de execução precisam ser duplicadas nas outras instâncias usadas pelo módulo de mensagens transacionais do Adobe Campaign.

## Enviar notificações transacionais por push

Quando combinado com [Módulo de canal de aplicativo móvel](../send/push.md), as mensagens transacionais permitem que você envie mensagens transacionais por meio de notificações em dispositivos móveis.

Para enviar notificações por push transacionais, você precisa executar as seguintes configurações:

1. Instale o pacote **Canal de aplicativo móvel** nas instâncias de controle e de execução.

   >[!CAUTION]
   >
   >Verifique seu contrato de licença antes de instalar um novo pacote integrado do Campaign.

1. Replique o **Aplicativo móvel** e os aplicativos móveis associados nas instâncias de execução.

Além disso, o evento deve conter os seguintes elementos:

* A ID do dispositivo móvel: **registrationId** para Android e **deviceToken** para iOS. Essa ID representa o &quot;endereço&quot; para o qual a notificação é enviada.
* O link para o aplicativo móvel ou a chave de integração (**uuid**) que permite recuperar informações de conexão específicas do aplicativo.
* O canal para onde a notificação é enviada (**wishedChannel**): 41 para iOS e 42 para Android.
* Quaisquer outros dados de personalização.

Veja abaixo um exemplo de uma configuração de evento para enviar notificações transacionais por push:

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```



## Limpar eventos {#purge-events}

É possível adaptar as configurações do assistente de implantação para definir por quanto tempo os dados devem ser armazenados no banco de dados.

A limpeza de eventos é executada automaticamente pelo **Limpeza do banco de dados** fluxo de trabalho técnico. Esse workflow limpa os eventos recebidos e armazenados nas instâncias de execução e eventos arquivados em uma instância de controle.

Use as setas conforme apropriado para alterar as configurações de limpeza do **Eventos** (em uma instância de execução) e **Eventos arquivados** (em uma instância de controle).


## Workflows técnicos {#technical-workflows}

Você deve garantir que os workflows técnicos nas instâncias de controle e de execução tenham sido iniciados antes de implantar qualquer template de mensagem transacional.

Os workflows de arquivamento podem ser acessados na pasta **Administration > Production > Message Center.**

### Workflows da instância de controle {#control-instance-workflows}

Na instância de controle, deve ser criado um workflow de arquivamento para cada **[!UICONTROL Message Center execution instance]** conta externa. Clique no botão **[!UICONTROL Create the archiving workflow]** para criar e iniciar o workflow.

### Workflows da instância de execução {#execution-instance-workflows}

Na(s) instância(s) de execução, você deve iniciar os seguintes workflows técnicos:

* **[!UICONTROL Processing batch events]** (internal name: **[!UICONTROL batchEventsProcessing]** ): esse fluxo de trabalho permite dividir eventos em lote em uma fila antes que eles sejam vinculados a um template de mensagem.
* **[!UICONTROL Processing real time events]** (internal name: **[!UICONTROL rtEventsProcessing]** ): esse workflow permite dividir eventos em tempo real em uma fila antes que eles sejam vinculados a um template de mensagem.
* **[!UICONTROL Update event status]** (internal name: **[!UICONTROL updateEventStatus]** ): esse workflow permite que você atribua um status ao evento.

  Os possíveis status do evento são:

   * **[!UICONTROL Pending]**: o evento está na fila. Nenhum template de mensagem foi atribuído a ele.
   * **[!UICONTROL Pending delivery]**: o evento está na fila, um template de mensagem foi atribuído a ele e está sendo processado pelo delivery.
   * **[!UICONTROL Sent]**: esse status é copiado dos logs do delivery. Significa que o delivery foi enviado.
   * **[!UICONTROL Ignored by the delivery]**: esse status é copiado dos logs do delivery. Ele significa que o delivery foi ignorado.
   * **[!UICONTROL Delivery failed]**: esse status é copiado dos logs do delivery. Ele significa que o delivery falhou.
   * **[!UICONTROL Event not taken into account]**: o evento não pôde ser vinculado a um template de mensagem. O evento não será processado.
