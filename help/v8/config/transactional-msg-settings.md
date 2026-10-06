---
title: Configurações de mensagens transacionais do Campaign
description: Configurações de mensagens transacionais do Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: d3b34fea-a110-482f-adb2-aae8d686bac8
    internal-label: Transactional messaging
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 28%
---
# Configurações de mensagens transacionais {#mc-settings}

As mensagens transacionais (Centro de mensagens) são um módulo do Campaign criado para gerenciar mensagens acionadas. Saiba mais sobre mensagens transacionais em [esta seção](../send/transactional.md).

Entenda a arquitetura de mensagens transacionais em [esta página](../architecture/architecture.md#transac-msg-archi).


>[!NOTE]
>
>Como usuário do Managed Cloud Services, [contate a Adobe](../start/campaign-faq.md#support) para instalar e configurar as mensagens transacionais do Campaign em seu ambiente.

## Definir permissões {#mc-permissions}

Para criar novos usuários para as instâncias de execução do Centro de mensagens hospedadas na Adobe Cloud, entre em contato com o Gerente de transição da Adobe. Os usuários do Centro de mensagens são operadores específicos que exigem permissões dedicadas para acessar pastas de &quot;eventos em tempo real&quot; (nmsRtEvent).

## Extensões do esquema  {#mc-schema-ext}

Todas as extensões de esquema feitas nos esquemas usados por [fluxos de trabalho técnicos do Centro de Mensagens](#technical-workflows) em instâncias de controle ou de execução precisam ser duplicadas nas outras instâncias usadas pelo módulo de mensagens transacionais do Adobe Campaign.

## Enviar notificações transacionais por push {#mc-transactional-push}

Quando combinado com o [Módulo de canal de aplicativo móvel](../send/push.md), as mensagens transacionais permitem que você envie mensagens transacionais por meio de notificações em dispositivos móveis.

Para enviar notificações por push transacionais, você precisa executar as seguintes configurações:

1. Instale o pacote **Canal de aplicativo móvel** nas instâncias de controle e de execução.

   >[!CAUTION]
   >
   >Verifique seu contrato de licença antes de instalar um novo pacote integrado do Campaign.

1. Replicar o serviço **Aplicativo móvel** e os aplicativos móveis associados nas instâncias de execução.

Além disso, o evento deve conter os seguintes elementos:

* A ID do dispositivo móvel: **registrationId** para Android e **deviceToken** para iOS. Essa ID representa o &quot;endereço&quot; para o qual a notificação é enviada.
* O link para o aplicativo móvel ou a chave de integração (**uuid**) que permite recuperar as informações de conexão específicas do aplicativo.
* O canal para onde a notificação será enviada (**wishedChannel**): 41 para iOS e 42 para Android.
* Quaisquer outros dados de personalização.

Veja abaixo um exemplo de uma configuração de evento para enviar notificações transacionais por push:

```xml
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation="none" uuid="com.adobe.NeoMiles"/>
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

A limpeza de eventos é executada automaticamente pelo fluxo de trabalho técnico **Limpeza de banco de dados**. Esse fluxo de trabalho limpa os eventos recebidos e armazenados nas instâncias de execução e eventos arquivados em uma instância de controle.

Use as setas conforme apropriado para alterar as configurações de limpeza dos **Eventos** (em uma instância de execução) e dos **Eventos arquivados** (em uma instância de controle).


## Fluxos de trabalho técnicos {#technical-workflows}

Você deve garantir que os workflows técnicos nas instâncias de controle e de execução tenham sido iniciados antes de implantar qualquer template de mensagem transacional.

Os fluxos de trabalho de arquivamento podem ser acessados na pasta **Administration > Production > Message Center**.

### Fluxos de trabalho da instância de controle {#control-instance-workflows}

Na instância de controle, você deve criar um fluxo de trabalho de arquivamento para cada conta externa **[!UICONTROL Message Center execution instance]**. Clique no botão **[!UICONTROL Create the archiving workflow]** para criar e iniciar o fluxo de trabalho.

### Fluxo de trabalho da instância de execução {#execution-instance-workflows}

Na(s) instância(s) de execução, você deve iniciar os seguintes workflows técnicos:

* **[!UICONTROL Processing batch events]** (internal name: **[!UICONTROL batchEventsProcessing]** ): esse fluxo de trabalho permite dividir eventos em lote em uma fila antes que eles sejam vinculados a um modelo de mensagem.
* **[!UICONTROL Processing real time events]** (internal name: **[!UICONTROL rtEventsProcessing]** ): esse fluxo de trabalho permite dividir eventos em tempo real em uma fila antes que eles sejam vinculados a um modelo de mensagem.
* **[!UICONTROL Update event status]** (internal name: **[!UICONTROL updateEventStatus]** ): esse fluxo de trabalho permite que você atribua um status ao evento.

  Os possíveis status do evento são:

  * **[!UICONTROL Pending]**: evento na fila. Nenhum modelo de mensagem foi atribuído a ele.
  * **[!UICONTROL Pending delivery]**: o evento está na fila, um modelo de mensagem foi atribuído a ele e está sendo processado pela entrega.
  * **[!UICONTROL Sent]**: este status é copiado dos logs de entrega. Significa que a entrega foi enviada.
  * **[!UICONTROL Ignored by the delivery]**: este status é copiado dos logs de entrega. Ele significa que a entrega foi ignorada.
  * **[!UICONTROL Delivery failed]**: este status é copiado dos logs de entrega. Ele significa que a entrega falhou.
  * **[!UICONTROL Event not taken into account]**: o evento não pôde ser vinculado a um modelo de mensagem. O evento não será processado.
