---
title: Configurações de mensagens transacionais de campanha
description: Configurações de mensagens transacionais de campanha
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 42%

---

# Configurações de mensagens transacionais

![](../assets/do-not-localize/speech.png) Como um usuário do Managed Cloud Services, [Adobe de contato](../start/campaign-faq.md#support) para instalar e configurar mensagens transacionais do Campaign no seu ambiente.

![](../assets/do-not-localize/glass.png) Os recursos de mensagens transacionais são detalhados em [esta seção](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Entenda a arquitetura de mensagens transacionais no [esta página](../architecture/architecture.md#transac-msg-archi).

## Definir permissões

Para criar novos usuários para as instâncias de execução do Centro de mensagens hospedadas na Adobe Cloud, você precisará entrar em contato com o Atendimento ao cliente da Adobe. Os usuários do Centro de mensagens são operadores específicos que exigem permissões dedicadas para acessar pastas de &quot;eventos em tempo real&quot; (nmsRtEvent).

## Extensões de schema

Todas as extensões de schema feitas nos schemas usados por **Workflows técnicos do Centro de mensagens** em instâncias de controle ou de execução precisam ser duplicadas nas outras instâncias usadas pelo módulo de mensagens transacionais do Adobe Campaign.

![](../assets/do-not-localize/book.png) Saiba mais sobre os workflows técnicos do Centro de mensagens em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## Enviar notificações transacionais por push

Quando combinadas com o módulo Canal de aplicativo móvel, as mensagens transacionais permitem que você envie mensagens transacionais por meio de notificações em dispositivos móveis.

![](../assets/do-not-localize/book.png) O canal de aplicativo móvel é detalhado em [esta seção](../send/push.md).

Para enviar notificações transacionais por push, é necessário executar as seguintes configurações:

1. Instale o pacote **Canal de aplicativo móvel** nas instâncias de controle e de execução.

   >[!CAUTION]
   >
   >Verifique o contrato de licença antes de instalar um novo pacote integrado do Campaign.

1. Replicar o **Aplicativo móvel** e os aplicativos móveis associados nas instâncias de execução.

Para que o Campaign envie notificações transacionais por push, o evento deve conter os seguintes elementos:

* A ID do dispositivo móvel: **registrationId** para Android e **deviceToken** para iOS. Essa ID representa o &quot;endereço&quot; para o qual a notificação será enviada.
* O link para o aplicativo móvel ou a chave de integração (**uuid**) que permite recuperar informações de conexão específicas do aplicativo.
* O canal para onde a notificação é enviada (**wishedChannel**): 41 para iOS e 42 para Android.
* Outros dados a serem aproveitados para personalização.

Este é um exemplo de um evento que contém essas informações:

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

## Monitorar limites {#monitor-thresholds}

Você pode configurar os limites de aviso (laranja) e os limites de alerta (vermelho) dos indicadores que aparecem no **Nível de serviço do Centro de mensagens** e **Tempo de processamento do Centro de mensagens** relatórios.

Para fazer isso, siga as etapas abaixo:

1. Abra o assistente de implantação no **instância de execução** e navegue até o **[!UICONTROL Message Center]** página.
1. Use as setas para modificar os limites.


## Limpar eventos {#purge-events}

Você pode adaptar as configurações do assistente de implantação para definir por quanto tempo os dados devem ser armazenados no banco de dados.

A limpeza de eventos é executada automaticamente pelo **Limpeza do banco de dados** fluxo de trabalho técnico. Esse workflow limpa os eventos recebidos e armazenados nas instâncias de execução e eventos arquivados em uma instância de controle.

Use as setas conforme o caso para alterar as configurações de limpeza do **Eventos** (em uma instância de execução) e **Eventos arquivados** (em uma instância de controle).


## Workflows técnicos {#technical-workflows}

Você deve garantir que os workflows técnicos nas instâncias de controle e de execução tenham sido iniciados antes de implantar qualquer template de mensagem transacional.

Os workflows de arquivamento podem ser acessados na pasta **Administration > Production > Message Center.**

### Workflows da instância de controle {#control-instance-workflows}

Na instância de controle, é necessário criar um workflow de arquivamento para cada **[!UICONTROL Message Center execution instance]** conta externa. Clique no botão **[!UICONTROL Create the archiving workflow]** para criar e iniciar o workflow.

### Workflows da instância de execução {#execution-instance-workflows}

Na(s) instância(s) de execução, você deve iniciar os seguintes workflows técnicos:

* **[!UICONTROL Processing batch events]** (internal name: **[!UICONTROL batchEventsProcessing]** ): esse fluxo de trabalho permite dividir eventos em lote em uma fila antes que eles sejam vinculados a um template de mensagem.
* **[!UICONTROL Processing real time events]** (internal name: **[!UICONTROL rtEventsProcessing]** ): esse workflow permite dividir eventos em tempo real em uma fila antes que eles sejam vinculados a um template de mensagem.
* **[!UICONTROL Update event status]** (internal name: **[!UICONTROL updateEventStatus]** ): esse workflow permite que você atribua um status ao evento.

   Os status possíveis do evento são:

   * **[!UICONTROL Pending]**: o evento está na fila. Nenhum template de mensagem foi atribuído a ele.
   * **[!UICONTROL Pending delivery]**: o evento está na fila, um template de mensagem foi atribuído a ele e está sendo processado pelo delivery.
   * **[!UICONTROL Sent]**: esse status é copiado dos logs do delivery. Significa que o delivery foi enviado.
   * **[!UICONTROL Ignored by the delivery]**: esse status é copiado dos logs do delivery. Ele significa que o delivery foi ignorado.
   * **[!UICONTROL Delivery failed]**: esse status é copiado dos logs do delivery. Ele significa que o delivery falhou.
   * **[!UICONTROL Event not taken into account]**: o evento não pôde ser vinculado a um template de mensagem. O evento não será processado.
