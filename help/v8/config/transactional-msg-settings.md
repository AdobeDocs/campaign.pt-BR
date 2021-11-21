---
title: Configurações de mensagens transacionais de campanha
description: Configurações de mensagens transacionais de campanha
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 22%

---

# Configurações de mensagens transacionais

![](../assets/do-not-localize/speech.png)  Como um usuário do Managed Cloud Services, [Adobe de contato](../start/campaign-faq.md#support) para instalar e configurar mensagens transacionais do Campaign no seu ambiente.

![](../assets/do-not-localize/glass.png) Os recursos de mensagens transacionais são detalhados em [esta seção](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Entenda a arquitetura de mensagens transacionais no [esta página](../dev/architecture.md).

## Definir permissões

Para criar novos usuários para as instâncias de execução do Centro de mensagens hospedadas na Adobe Cloud, você precisará entrar em contato com o Atendimento ao cliente da Adobe. Os usuários do Centro de mensagens são operadores específicos que exigem permissões dedicadas para acessar pastas de &quot;eventos em tempo real&quot; (nmsRtEvent).

## Extensões de schema

Todas as extensões de schema feitas nos schemas usados por **Workflows técnicos do Centro de mensagens** em instâncias de controle ou de execução precisam ser duplicadas nas outras instâncias usadas pelo módulo de mensagens transacionais do Adobe Campaign.

![](../assets/do-not-localize/book.png) Saiba mais sobre os workflows técnicos do Centro de mensagens em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## Enviar notificações transacionais por push

Quando combinadas com o módulo Canal de aplicativo móvel, as mensagens transacionais permitem que você envie mensagens transacionais por meio de notificações em dispositivos móveis.

![](../assets/do-not-localize/book.png) O canal de aplicativo móvel é detalhado em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

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
