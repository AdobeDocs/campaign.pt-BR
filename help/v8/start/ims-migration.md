---
title: Migração de usuários de tecnologia para a conta técnica no Console do desenvolvedor
description: Migração de usuários de tecnologia para a conta técnica no Console do desenvolvedor
hide: true
hidefromtoc: true
source-git-commit: 7b4942b5334826adf27c8a31dbdb9a5bfb5d50eb
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 1%

---

# Migração de usuários de tecnologia para a conta técnica no Console do desenvolvedor {#migrate-tech-users-to-ims}

A partir do Campaign v8.5, o processo de autenticação para o Campaign v8 está sendo aprimorado. Os operadores técnicos devem [Sistema Adobe Identity Management (IMS)](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"} para se conectar ao Campaign. Um operador técnico é um perfil de usuário do Campaign que foi explicitamente criado para integração com a API. Este artigo detalha as etapas necessárias para migrar um operador técnico para uma conta técnica no console do Adobe Developer.

## O que mudou?{#ims-changes}

Os usuários regulares do Campaign já se conectam ao console do Adobe Campaign usando a Adobe ID, por meio do Adobe Identity Management System (IMS). Como parte do esforço para reforçar a segurança e o processo de autenticação, o aplicativo cliente do Adobe Campaign agora chama as APIs do Campaign diretamente usando o token de conta técnica IMS.

Saiba mais sobre o novo processo de autenticação de servidor para servidor [na documentação do Console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Essa alteração é aplicável a partir do Campaign v8.5 e será **obrigatório** a partir do Campaign v8.6.


## Fui afetado?{#ims-imacts}

Se estiver usando APIs do Campaign, você precisará migrar seu operador técnico para o Console do Adobe Developer, conforme detalhado abaixo.

## Como migrar?{#ims-migration-procedure}

### Pré-requisitos{#ims-migration-prerequisites}

Antes de iniciar o processo de migração, entre em contato com o representante da Adobe para que as equipes técnicas da Adobe possam migrar seus grupos de operadores e direitos nomeados existentes para o Adobe Identity Management System (IMS).

### Etapa 1 - Criar um projeto no Console do Adobe Developer{#ims-migration-step-1}

As integrações são criadas como parte de um **Projeto** no console do Adobe Developer. Saiba mais sobre Projetos em [Documentação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

Como usuário do Campaign v8, você já deve ter um projeto no Console do Adobe Developer. Caso contrário, você deve criar um projeto. As etapas para criar um projeto são detalhadas [na documentação do Console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Depois de ter acesso ao projeto do Campaign, você pode adicionar serviços, incluindo APIs, Adobe Campaign e API de gerenciamento de E/S. Para esta migração, você deve adicionar as APIs abaixo no seu projeto: **API de gerenciamento de E/S** e **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Etapa 2 - Adicionar uma API ao projeto usando a autenticação de Servidor para Servidor{#ims-migration-step-2}

Depois que o projeto for criado no Console do Adobe Developer, adicione uma API que usa a autenticação de servidor para servidor. Saiba como configurar a credencial de servidor para servidor do OAuth no [na documentação do Console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

Quando a API tiver sido conectada com êxito, você poderá acessar as credenciais recém-geradas, incluindo a ID do cliente e o Segredo do cliente, bem como gerar um token de acesso.

### Etapa 3 - Adicionar o perfil de produto ao projeto{#ims-migration-step-3}

Agora é possível adicionar o perfil de produto do Campaign ao projeto, conforme detalhado abaixo:

1. Abra a API do Adobe Campaign.
1. Clique em **Editar perfis de produto** botão

   ![](assets/do-not-localize/ims-edit-api.png)

1. Atribua todos os perfis de produto relevantes à API, por exemplo, &quot;messagecenter&quot;, e salve as alterações.
1. Navegue até o **Detalhes da credencial** do seu projeto e copie a guia **Email da conta técnica** valor.

### Etapa 4 - Atualizar o operador técnico no console do cliente {#ims-migration-step-4}

A última etapa é atualizar o operador técnico no console do cliente do Adobe Campaign.

>[!CAUTION]
>
>Depois de atualizar o tipo de autenticação para o operador técnico, todas as integrações de API com esse operador técnico deixarão de funcionar

Para atualizar o modo de autenticação do operador técnico para IMS, siga estas etapas:

1. No explorador do console do cliente do Campaign, navegue até o **Administração > Gerenciamento de acesso > Operadores**.
1. Edite o operador técnico existente usado para APIs do Fir.
1. Substitua o **Nome (logon)** deste operador técnico pelo e-mail da conta técnica recuperado anteriormente.
1. Navegue até o **Editar** botão na parte superior esquerda ao lado **Arquivo** e selecione **Editar a origem XML**.
1. Atualize o modo de autenticação para `ims`, como se segue:

   ```javascript
   <operator 
   ...
       <access authenticationType="ims" ...
       ...
       </access>
   ...
   </operator>
   ```

1. Salve as alterações.


Você também pode atualizar o operador técnico de forma programática, usando scripts SQL ou APIs do Campaign. Esses modos ajudam a automatizar as etapas que atualizam o nome do operador com o endereço de email da conta técnica associada e/ou o tipo de autenticação.

* Use o seguinte **Script SQL** para substituir o nome do operador pelo email associado:

   ```sql
   UPDATE xtkoperator
   SET sauthenticationtype = 'ims',
           sname = '{email}'
   WHERE sname = '{name}' AND itype = 0;
   ```

* Use o seguinte `queryDef.ExecuteQuery` **API do Campaign** para buscar a id de um operador para determinado operador técnico:

   ```javascript
   <?xml version="1.0" encoding="utf-8"?>
   <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
       <soap:Body>
           <ExecuteQuery xmlns="urn:xtk:queryDef">
               <sessiontoken>{session_token}</sessiontoken>
               <entity>
                   <queryDef schema="xtk:operator" operation="select">
                       <select>
                           <node expr="@id"/>
                       </select>
                       <where>
                           <condition expr="@name='{name}'"/>
                           <condition expr="@type=0"/>
                       </where>
                   </queryDef>
               </entity>
           </ExecuteQuery>
       </soap:Body>
   </soap:Envelope>
   ```

* Use o seguinte `session.Write` **API do Campaign** para atualizar o nome com o endereço de email de conta técnica fornecido:

   ```javascript
   <?xml version="1.0" encoding="utf-8"?>
   <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
       <soap:Body>
           <Write xmlns="urn:xtk:session">
               <sessiontoken>{session_token}</sessiontoken>
               <domDoc xsi:type='ns:Element' SOAP-ENV:encodingStyle='http://xml.apache.org/xml-soap/literalxml'>
                   <operator _operation="update" id="{id}" name="{email}" xtkschema="xtk:operator">
                       <access authenticationType="ims" />
                   </operator>
               </domDoc>
           </Write>
       </soap:Body>
   </soap:Envelope>
   ```

### Etapa 5 — validação da configuração {#ims-migration-step-5}

Para experimentar a conexão, siga as etapas detalhadas na [Guia de credenciais do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} para gerar um token de acesso e copiar o comando cURL de amostra fornecido.

Para obter mais detalhes sobre as etapas de integração da API, consulte [Documentação de autenticação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.



### Exemplos de chamadas SOAP{#ims-migration-samples}

Depois que o processo de migração é alcançado e validado, as chamadas Soap são atualizadas conforme abaixo:

* Antes da migração

   ```sql
   POST /nl/jsp/soaprouter.jsp HTTP/1.1
   Host: localhost:8080
   Content-Type: application/soap+xml;
   SOAPAction: "nms:rtEvent#PushEvent"
   charset=utf-8
   
   <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:PushEvent>
           <urn:sessiontoken>SESSION_TOKEN</urn:sessiontoken>
           <urn:domEvent>
               <!--You may enter ANY elements at this point-->
               <rtEvent type="melon" email="dchavan@adobe.com"/>
           </urn:domEvent>
       </urn:PushEvent>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

* Após a migração

   ```
   POST /nl/jsp/soaprouter.jsp HTTP/1.1
   Host: localhost:8080
   Content-Type: application/soap+xml;
   SOAPAction: "nms:rtEvent#PushEvent"
   charset=utf-8
   Authorization: Bearer <IMS_Technical_Token_Token>
   
   <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:PushEvent>
           <urn:sessiontoken></urn:sessiontoken>
           <urn:domEvent>
               <!--You may enter ANY elements at this point-->
               <rtEvent type="melon" email="dchavan@adobe.com"/>
           </urn:domEvent>
       </urn:PushEvent>
   </soapenv:Body>
   </soapenv:Envelope>
   ```
