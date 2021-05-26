---
solution: Campaign v8
product: Adobe Campaign
title: Configurações de mensagens transacionais de campanha
description: Configurações de mensagens transacionais de campanha
feature: Visão geral
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 21%

---

# Configurações de mensagens transacionais

:voice_balloon: Como um usuário do Managed Cloud Services, [entre em contato com o Adobe](../start/campaign-faq.md#support) para instalar e configurar mensagens transacionais do Campaign no seu ambiente.

[!DNL :bulb:] Os recursos de mensagens transacionais são detalhados  [nesta seção](../send/transactional.md).

[!DNL :bulb:] Entenda a arquitetura de mensagens transacionais  [nesta página](../dev/architecture.md).

## Definir permissões

Para criar novos usuários para as instâncias de execução do Centro de mensagens hospedadas na Adobe Cloud, você precisará entrar em contato com o Atendimento ao cliente da Adobe. Os usuários do Centro de mensagens são operadores específicos que exigem permissões dedicadas para acessar pastas de &quot;eventos em tempo real&quot; (nmsRtEvent).

## Extensões de schema

Todas as extensões de schema feitas nos schemas usados pelos **workflows técnicos do Centro de Mensagens** em instâncias de controle ou de execução precisam ser duplicadas nas outras instâncias usadas pelo módulo de mensagens transacionais do Adobe Campaign.

:[!DNL :arrow_upper_right:]: Saiba mais sobre os workflows técnicos do Centro de mensagens na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)

## Enviar notificações transacionais por push

Quando combinadas com o módulo Canal de aplicativo móvel, as mensagens transacionais permitem que você envie mensagens transacionais por meio de notificações em dispositivos móveis.

:[!DNL :arrow_upper_right:]: O canal Mobile app é detalhado na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

Para enviar notificações transacionais por push, é necessário executar as seguintes configurações:

1. Instale o pacote **Canal de aplicativo móvel** nas instâncias de controle e de execução.

   >[!CAUTION]
   >
   >Verifique o contrato de licença antes de instalar um novo pacote integrado do Campaign.

1. Replique o serviço **Mobile application** e os aplicativos móveis associados nas instâncias de execução.

Para que o Campaign envie notificações transacionais por push, o evento deve conter os seguintes elementos:

* A ID do dispositivo móvel: **registrationId** para Android e **deviceToken** para iOS. Essa ID representa o &quot;endereço&quot; para o qual a notificação será enviada.
* O link para o aplicativo móvel ou a chave de integração (**uuid**) que permite recuperar informações de conexão específicas para o aplicativo.
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

