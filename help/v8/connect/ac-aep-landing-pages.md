---
title: Páginas de aterrissagem de campanha e atributos de perfil
description: Saiba como sincronizar páginas de aterrissagem do Adobe Campaign e atributos de perfil do Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 79faf36db774239477089c13c98cbf48a66752a3
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 1%

---

# Atualizar perfis do Adobe Experience Platform a partir de páginas de aterrissagem do Adobe Campaign

A integração entre o Adobe Campaign e o Adobe Experience Platform permite sincronizar dados facilmente entre suas páginas de aterrissagem do Adobe Campaign e o Adobe Experience Platform. Com essa integração, você pode:

* Recupere atributos de perfil do Adobe Experience Platform para exibir informações atualizadas nas páginas de aterrissagem do Adobe Campaign,
* Envie de volta os atributos de perfil atualizados para o Adobe Experience Platform para atualizar os atributos correspondentes com base no que foi preenchido e enviado nas landing pages.

As principais etapas para configurar essa integração são as seguintes:

<table>
<tr>
<td><img src="../assets/do-not-localize/icon-connection.svg" width="60px"><p><a href="#oauth">Configurar uma conexão OAuth</a></p></td>
<td><img src="../assets/do-not-localize/icon-source.svg" width="60px"><p><a href="#source">Criar uma conexão HTTP de origem de API</a></p></td>
<td><img src="../assets/do-not-localize/icon-options.svg" width="60px"><p><a href="#xtk">Adicionar opções de autenticação no Campaign</a></p></td>
<td><img src="../assets/do-not-localize/icon-javascript.svg" width="60px"><p><a href="#javascript">Adicionar códigos JavaScript no Campaign</a></p></td>
<td><img src="../assets/do-not-localize/icon-workflow.svg" width="60px"><p><a href="#script">Configurar o fluxo de trabalho da landing page</a></p></td>
</table>

## Configurar uma conexão Oauth {#oauth}

As APIs do Adobe Cloud Platform usam o protocolo OAuth 2.0 para autenticação e autorização. Para conectar o Adobe Experience Platform ao Adobe Campaign usando chamadas de API, é necessário gerar um token de acesso usando a Integração OAuth criada no console do Adobe Developer.

Para fazer isso, siga estes passos:

1. Acesse o console Adobe Developer.
1. Crie uma nova conexão de API usando o produto Adobe Experience Platform API. As etapas detalhadas sobre como obter um token de acesso OAuth 2.0 estão disponíveis na [Documentação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/Tools/OAuthPlayground/).
1. Depois que a conexão for criada, navegue até o **[!UICONTROL OAuth Server-to-Server]** e copie os detalhes abaixo, que são necessários na autenticação do Campaign:

   * ID DO CLIENTE
   * SEGREDO DO CLIENTE
   * ID DA ORGANIZAÇÃO

   ![](assets/ac-lp-oauth.png){width="70%"}

Agora que sua conexão OAuth está configurada, crie e configure um novo **[!UICONTROL HTTP API]** Conexão de origem para vincular o Adobe Campaign com o Adobe Experience Platform.

## Criar uma conexão HTTP de origem de API {#source}

Com a conexão OAuth em vigor, a próxima etapa é criar uma **[!UICONTROL HTTP API]** Conexão de origem no Adobe Experience Platform. Essa conexão permite transmitir dados para o Adobe Experience Platform usando APIs. Siga estas etapas:

1. Navegar até o Adobe Experience Platform **[!UICONTROL Sources]**, pesquise por **[!UICONTROL HTTP API]** origem e clique em **[!UICONTROL Add data]**.

   ![](assets/ac-lp-source.png){width="70%"}

1. Configure a conexão de acordo com suas necessidades. Informações detalhadas sobre como configurar uma conexão HTTP API estão disponíveis em [Documentação de origens do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/streaming/http.html).

   No **[!UICONTROL Authentication]** etapa, alternar no **[!UICONTROL Enable authentication]** opção para autenticar usando o token de acesso gerado anteriormente pela integração OAuth.

   ![](assets/ac-lp-source-authentication.png){width="70%"}

1. Depois que a conexão de origem é configurada, o endpoint de transmissão é exibido. Esse endpoint é necessário para assimilar dados na Adobe Experience Platform.

   ![](assets/ac-lp-endpoint.png){width="70%"}

   Você também pode acessar uma amostra do formato de dados assimilado na Adobe Experience Platform abrindo o fluxo de dados recém-criado na **[!UICONTROL Dataflows]** guia.

   ![](assets/ac-lp-schema.png){width="70%"}

Agora que a conexão HTTP API Source está configurada, é necessário adicionar opções específicas no Adobe Campaign para habilitar a conexão com o Adobe Experience Platform.

## Adicionar opções de autenticação no Adobe Campaign {#xtk}

Depois que a conexão de Origem da API HTTP for configurada, é necessário adicionar opções específicas no Adobe Campaign para habilitar a conexão com o Adobe Experience Platform. Isso pode ser feito no menu Administração do Campaign ou ao executar o fluxo de trabalho da página de aterrissagem adicionando um **[!UICONTROL JavaScript code]** atividade.

Navegue pelas guias abaixo para descobrir os dois métodos:

>[!BEGINTABS]

>[!TAB Adicionar opções do menu Administração]

1. Navegue até a **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**  menu.
1. Adicione as seguintes opções com os valores correspondentes do Console do Adobe Developer:

   * IMS_CLIENT_ID = cryptString(CLIENT ID)
   * IMS_CLIENT_SECRET = cryptString(CLIENT SECRET)
   * IMS_ORG_ID = ID DA ORGANIZAÇÃO
   * IMS_CLIENT_API_KEY = cryptString(CLIENT ID)

   ![](assets/ac-lp-xtk.png){width="70%"}

   >[!NOTE]
   >
   >A função cryptString() é usada para criptografar os dados de autenticação.

>[!TAB Adicionar opções usando uma atividade JavaScript code]

Para configurar essas opções automaticamente na execução do workflow das landing pages, adicione uma **[!UICONTROL JavaScript code]** atividade ao seu workflow com o código abaixo. [Saiba como configurar uma atividade de código JavaScript](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-JavaScript-code.html#JavaScript-code).

Na execução do workflow, as opções são criadas automaticamente no console do Campaign com os valores fornecidos.

    &quot;
    loadLibrary(&quot;xtk:shared/nl.js&quot;);
    loadLibrary(&quot;xtk:shared/xtk.js&quot;);
    loadLibrary(&quot;xtk:shared/json2.js&quot;);
    loadLibrary(&quot;xtk:common.js&quot;);
    
    função setAuthCredentials()
    {
    setOption(&quot;IMS_CLIENT_ID&quot;, cryptString(&#39;CLIENT ID&#39;));
    setOption(&quot;IMS_CLIENT_SECRET&quot;, cryptString(&#39;CLIENT SECRET&#39;));
    setOption(&quot;IMS_ORG_ID&quot;, cryptString(&#39;ID DA ORGANIZAÇÃO&#39;));
    setOption(&quot;IMS_CLIENT_API_KEY&quot;, cryptString(&#39;CLIENT ID&#39;));
    }
    &quot;

>[!ENDTABS]

Agora que as opções de autenticação estão configuradas no Campaign, é necessário criar códigos JavaScript personalizados para permitir a sincronização de dados entre o Campaign e o Adobe Experience Platform a partir da página de aterrissagem.

## Adicionar opções na execução do fluxo de trabalho {#javacript}

Para permitir a sincronização de dados entre landing pages e o Adobe Experience Platform, códigos JavaScript personalizados devem ser adicionados ao Adobe Campaign. Siga estas etapas:

1. Navegue até a **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL JavaScript codes]** menu.
1. Crie novos códigos JavaScript e copie e cole os trechos abaixo.

   >[!NOTE]
   >
   >O token de acesso e os dados de autenticação são recuperados automaticamente das opções configuradas anteriormente.

   ![](assets/ac-lp-script.png){width="70%"}

+++  Script 1 - Carregar atributos de perfil do Experience Platform

   Esse código verifica se o perfil existe no Adobe Experience Platform antes de carregar a landing page. Ele recupera os atributos do perfil e os exibe nos campos correspondentes da landing page.

   ```
   // API implementation to read profile from AEP
   function getProfileInfo(email)
   {
   var accessToken = getAccessToken();
   var request = new HttpClientRequest(('https://platform-stage.adobe.io/data/core/ups/access/entities?schema.name=_xdm.context.profile&entityId=' + email + '&entityIdNS=email&fields=identities,consents.marketing'));
   request.method = 'GET';
   request.header["Content-Type"] = "application/json";
   request.header["sandbox-name"] = "prod";
   request.header["x-gw-ims-org-id"] = getOption('IMS_ORG_ID');
   request.header["x-api-key"] = getOption('IMS_CLIENT_API_KEY');
   request.header["Authorization"] = "Bearer " + accessToken;
   request.execute();
   return request.response;
   }
   ```

+++

+++ Script 2 - Atualizar atributos de perfil de Experience Platform

   Esse código atualiza os atributos de perfil no Adobe Experience Platform com os valores enviados na landing page.

   ```
   // API implementation to update profile in AEP
   loadLibrary("xtk:shared/nl.js");
   loadLibrary("xtk:shared/xtk.js");
   loadLibrary("xtk:shared/json2.js");
   loadLibrary("xtk:common.js");
   
   function updateProfileInAEP(profileUpdatePayload)
   {
   var accessToken = getAccessToken();
   var request = new HttpClientRequest('https://dcs-stg.adobedc.net/collection/64a300b84d61c0bcea4f0cd4ecaaa224a19477026d14f7e08b5408ffaf5e6162?syncValidation=false');
   request.method = 'POST';
   request.header["Content-Type"] = "application/json";
   request.header["sandbox-name"] = "prod";
   request.header["Authorization"] = "Bearer " + accessToken;
   var body = '{"header":{"schemaRef":{"id":"https://ns.adobe.com/campdev/schemas/35d8e567772e1a1093ed6cf9e41d2c1fec22eeb3a89583e1","contentType":"application/vnd.adobe.xed-full+json;version=1.0"},"imsOrgId":"A1F66F0D5C47D1950A494133@AdobeOrg","datasetId":"63c7fa2a20cce11b98cccb41","source":{"name":"testHTTPSourcesVinay - 03/06/2023 5:43 PM"}},"body":{"xdmMeta":{"schemaRef":{"id":"https://ns.adobe.com/campdev/schemas/35d8e567772e1a1093ed6cf9e41d2c1fec22eeb3a89583e1","contentType":"application/vnd.adobe.xed-full+json;version=1.0"}},"xdmEntity":' + profileUpdatePayload +'}}';
   request.body = body;
   request.execute();
   return request.response;
   }
   
   
   // Get Access token from OAuth-Server-to-server API call
   function getAccessToken() {
   var clientId = decryptString(getOption('IMS_CLIENT_ID'));
   var clientSecret = decryptString(getOption('IMS_CLIENT_SECRET'));
   var request = new HttpClientRequest(('https://ims-na1-stg1.adobelogin.com/ims/token/v2?grant_type=client_credentials' + '&client_id=' + clientId + '&client_secret=' + clientSecret + '&scope=openid,session,AdobeID,read_organizations,additional_info.projectedProductContext'));
   request.method = 'POST';
   request.execute();
   var response = request.response;
   if(response.code != 200){
   logError('GetAccessToken failed,', response.code, response.body);
   return;
   }
   var body = ''+response.body;
   var parsedResponse = JSON.parse(body);
   var accessToken = parsedResponse.access_token;
   logInfo("Access token generated successfully");
   return accessToken;
   }
   ```

+++

Agora que os códigos JavaScript personalizados são criados no Adobe Campaign, você pode configurar o fluxo de trabalho que contém sua página de aterrissagem para usar esses códigos JavaScript para a sincronização de dados.

## Configurar o fluxo de trabalho da landing page {#script}

Com os códigos JavaScript adicionados ao Adobe Campaign, você pode aproveitá-los no fluxo de trabalho da página de destino usando **[!UICONTROL JavaScript code]** atividades:

* Para carregar dados do Experience Platform antes de carregar a landing page, adicione um **[!UICONTROL JavaScript code]** atividade antes da atividade de landing page e copiar e colar Script 1.

+++ Script 1 - Carregar atributos de perfil do Experience Platform

  ```
  // Script code to read profile from AEP.
  
  logInfo("Loading profile from AEP");
  loadLibrary("cus:aepAPI");
  var recipient=ctx.recipient;
  var email = recipient.@email;
  var response = getProfileInfo(email);
  ctx.isAEPProfileExists = 1;
  
  if(response.code == 404){
  ctx.isAEPProfileExists = 0
  logInfo("Profile with email" + email + " not found in AEP, ignoring the update activity");
  }
  else if(response.code == 200){
  var body = ''+response.body;
  var parsedResponse = JSON.parse(body);
  for (var key in parsedResponse) {
      var value =  parsedResponse[key];
      var marketing = value.entity.consents.marketing;
      logInfo("User Consent Details : " + JSON.stringify(marketing));   
      if(marketing.hasOwnProperty('email')&&marketing.email.hasOwnProperty('val')&&marketing.email.val=='n'){
      ctx.recipient.@blackListEmail = 1;
      }
      if(marketing.hasOwnProperty('sms')&&marketing.sms.hasOwnProperty('val')&&marketing.sms.val=='n'){
      ctx.recipient.@blackListMobile = 1;
      }
      if(marketing.hasOwnProperty('push')&&marketing.push.hasOwnProperty('val')&&marketing.push.val=='n'){
      ctx.recipient.@blackListPostalMail = 1;
      }
  } 
  }
  ```

+++

* Para atualizar os atributos do perfil de Experience Platform com os dados enviados na landing page, adicione um **[!UICONTROL JavaScript code]** atividade após a atividade de landing page e copy cole Script 2.

+++ Script 2 - Atualizar atributos de perfil de Experience Platform

  ```
  // Script code to update profile in AEP and ACC.
  
  logInfo("Executing script to update AEP profile.");
  
  // Loading aepAPI library JS code
  loadLibrary("cus:aepAPI");
  
  var recipient=ctx.recipient
  
  // Update profile only if it exists in AEP
  if(ctx.isAEPProfileExists==1){
  
  var email = recipient.@email
  logInfo(email);
  logInfo(recipient.@blackListEmail);
  logInfo(recipient.@blackListMobile);
  logInfo(recipient.@blackListPostalMail);
  
  var optOutPayload = new Array();
  
  if(recipient.@blackListEmail==1){
      optOutPayload.push('"email":{"val":"n"}');
  }
  else
      optOutPayload.push('"email":{"val":"y"}');
  
  if(recipient.@blackListMobile==1){
      optOutPayload.push('"sms":{"val":"n"}');
  }
  else
      optOutPayload.push('"sms":{"val":"y"}');
  
  if(recipient.@blackListPostalMail==1){
      optOutPayload.push('"push":{"val":"n"}');
  }
  else
      optOutPayload.push('"push":{"val":"y"}');
  
  var profileUpdatePayload = '{'+ '"personalEmail":{"address":' + '\"' + email + '\"' + '},' +'"consents":{"marketing":{' + optOutPayload.toString() + '}}}';
  
  var response = updateProfileInAEP(profileUpdatePayload);
  if(response.code == 200){
  var body = '' + response.body;
  logInfo("AEP Profile Updated successfully, Response " + body);
  // Update ACC profile 
  recipient.@xtkschema = "nms:recipient";
  recipient.@_operation = "update";
  recipient.@_key="@id";
  xtk.session.Write(recipient);
  logInfo("ACC Profile Updated successfully");
  }
  else{
      logError('Server Error: ', response.code, response.body);
  } 
  }
  else {
  logInfo("Ignoring AEP profile update as profile doesn't exists.");
  
  // Update ACC profile   
  recipient.@xtkschema = "nms:recipient";
  recipient.@_operation = "update";
  recipient.@_key="@id";  
  xtk.session.Write(recipient);
  logInfo("ACC Profile Updated successfully");
  }
  ```

+++

>[!CAUTION]
>
>Certifique-se de personalizar a carga em cada script com base em suas necessidades específicas.
>
>Se você não adicionar nenhum script antes da atividade de landing page, nenhuma verificação de existência de perfil será executada no Adobe Experience Platform. Quando a landing page for enviada e o perfil não existir, ela será criada no Adobe Experience Platform com os atributos da landing page.

Este é um exemplo de fluxo de trabalho usando as atividades de código JavaScript antes e depois de uma página de aterrissagem:

![](assets/ac-lp-wkf.png){width="70%"}

Este é um exemplo de uma página de aterrissagem e uma atividade de código JavaScript configurada para atualizar atributos de perfil no Adobe Experience Platform:

![](assets/ac-lp-example.png){width="70%"}

![](assets/ac-lp-code.png){width="70%" zoomable="yes"}

### Mais informações

* [Configurar uma atividade de código JavaScript](../../automation/workflow/sql-code-and-javascript-code.md#javascript-code)
* [Criar uma landing page](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/creating-a-landing-page.html)
* [Gerenciar assinaturas e cancelamentos de assinaturas](../start/subscriptions.md)