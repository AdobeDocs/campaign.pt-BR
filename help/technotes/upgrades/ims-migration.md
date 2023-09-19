---
title: Migração de usuários técnicos para o console do Adobe Developer
description: Saiba como migrar operadores técnicos do Campaign para a conta técnica no console do Adobe Developer
source-git-commit: 43a124dd64532ffe84ca2b300113cacc545a811a
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 1%

---

# Migração de operadores técnicos do Campaign para o Console do Adobe Developer {#migrate-tech-users-to-ims}

A partir do Campaign v8.5, o processo de autenticação para o Campaign v8 está sendo aprimorado. Os operadores técnicos devem [Sistema Adobe Identity Management (IMS)](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"} para se conectar ao Campaign. Um operador técnico é um perfil de usuário do Campaign que foi explicitamente criado para integração com a API. Este artigo detalha as etapas necessárias para migrar um operador técnico para uma conta técnica no console do Adobe Developer.

## O que mudou?{#ims-changes}

Os usuários regulares do Campaign já se conectam ao console do Adobe Campaign usando a Adobe ID, por meio do Adobe Identity Management System (IMS). Como parte do esforço para reforçar a segurança e o processo de autenticação, o aplicativo cliente do Adobe Campaign agora chama as APIs do Campaign diretamente usando o token de conta técnica IMS.

Saiba mais sobre o novo processo de autenticação de servidor para servidor no [Documentação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Essa alteração é aplicável a partir do Campaign v8.5 e será **obrigatório** a partir do Campaign v8.6.


## Você será afetado?{#ims-impacts}

Se estiver usando APIs do Campaign, você precisará migrar o(s) operador(es) técnico(s) para o Adobe Developer Console, conforme detalhado abaixo.

## Como migrar?{#ims-migration-procedure}

Cada operador técnico deve ter, pelo menos, uma conta técnica.

As principais etapas são:

1. Primeiro, crie a conta técnica correspondente ao operador técnico. Por exemplo, suponha que a conta técnica (TA1) recém-criada para o operador técnico (TO1).
1. Execute as etapas detalhadas abaixo na conta técnica TA1
   [Etapa 4](#ims-migration-step-4) é opcional e só é necessário se o operador técnico tiver permissões específicas de pasta.
1. Migre toda a implementação de integração da API do Campaign para a conta técnica recém-criada TA1.
1. Quando toda a API/Integração voltada para o cliente começar a funcionar totalmente em TA1, substitua o operador técnico TO1 pela conta técnica TA1.

### Pré-requisitos{#ims-migration-prerequisites}

Antes de iniciar o processo de migração, entre em contato com o representante da Adobe para que as equipes técnicas da Adobe possam migrar seus grupos de operadores e direitos nomeados existentes para o Adobe Identity Management System (IMS).

### Etapa 1 — criar/atualizar o projeto do Campaign no console do Adobe Developer{#ims-migration-step-1}

As integrações são criadas como parte de um **Projeto** no console do Adobe Developer. Saiba mais sobre Projetos em [Documentação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

Como usuário do Campaign v8, você já deve ter um projeto no Console do Adobe Developer. Caso contrário, você deve criar um projeto. As etapas para criar um projeto são detalhadas [na documentação do Console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Depois de ter acesso ao projeto do Campaign, você pode adicionar serviços, incluindo APIs, Adobe Campaign e API de gerenciamento de E/S. Para esta migração, você deve adicionar as APIs abaixo no seu projeto: **API de gerenciamento de E/S** e **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Etapa 2 - Adicionar uma API ao projeto usando a autenticação de Servidor para Servidor{#ims-migration-step-2}

Depois que o projeto for criado no Console do Adobe Developer, adicione uma API que use autenticação de servidor para servidor. Saiba como configurar a credencial de servidor para servidor do OAuth no [Documentação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

Quando a API tiver sido conectada com êxito, você poderá acessar as credenciais recém-geradas, incluindo a ID do cliente e o Segredo do cliente, bem como gerar um token de acesso.

### Etapa 3 - Adicionar o perfil de produto ao projeto{#ims-migration-step-3}

Agora é possível adicionar o perfil de produto do Campaign ao projeto, conforme detalhado abaixo:

1. Abra a API do Adobe Campaign.
1. Clique em **Editar perfis de produto** botão

   ![](assets/do-not-localize/ims-edit-api.png)

1. Atribua todos os perfis de produto relevantes à API, por exemplo, &quot;messagecenter&quot;, e salve as alterações.
1. Navegue até o **Detalhes da credencial** do seu projeto e copie a guia **Email da conta técnica** valor.

### Etapa 4 - Atualizar o operador técnico no Console do cliente {#ims-migration-step-4}

Essa etapa só será necessária se permissões de pasta específicas ou direitos nomeados tiverem sido definidos para esse operador (não por meio do grupo do operador).

Agora é necessário atualizar o operador técnico recém-criado no Console do cliente do Adobe Campaign. Você deve aplicar as permissões existentes da pasta do operador técnico ao novo operador técnico.
Para atualizar esse operador, siga estas etapas:

1. No explorador do Console do cliente do Campaign, navegue até o **Administração > Gerenciamento de acesso > Operadores**.
1. Acesse o operador técnico existente usado para APIs.
1. Navegue até as permissões da pasta e verifique os direitos.
1. Aplique as mesmas permissões ao operador técnico recém-criado. O email deste operador é o **Email da conta técnica** valor copiado anteriormente.
1. Salve as alterações.


>[!CAUTION]
>
>O novo operador técnico deve ter feito pelo menos uma chamada à API para ser adicionada ao Console do cliente do Campaign.
>

<!--

>[!CAUTION]
>
>After updating the authentication type for the technical operator, all API integrations with this technical operator will stop working. You must [update your API integrations](#ims-migration-step-6). 

To update the technical operator authentication mode to IMS, follow these steps:

1. From Campaign Client Console explorer, browse to the **Administration > Access Management > Operators**.
1. Edit the existing technical operator used for APIs.
1. Replace the **Name (login)** of this technical operator by the technical account email retrieved earlier.
1. Browse to the **Edit** button on the top left beside **File**, and select **Edit the XML source**.
1. Update the authentication mode to `ims`, as follows:

    ```javascript
    <operator 
    ...
        <access authenticationType="ims" ...
        ...
        </access>
    ...
    </operator>
    ```

1. Save your changes.

You can also update the technical operator programmatically, using SQL scripts or Campaign APIs. These modes help you automate the steps which update operator's name with associated Technical account email address and/or authentication type. 

* Use the following **SQL Script** to replace operator's name with associated email:

    ```sql
    UPDATE xtkoperator
    SET sauthenticationtype = 'ims',
            sname = '{email}'
    WHERE sname = '{name}' AND itype = 0;
    ```

* Use the following `queryDef.ExecuteQuery` **Campaign API** to fetch id of an operator for given technical operator:

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

* Use the following `session.Write` **Campaign API** to update name with given technical account email address:

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
-->

### Etapa 5 — validação da configuração {#ims-migration-step-5}

Para experimentar a conexão, siga as etapas detalhadas na [Guia de credenciais do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} para gerar um token de acesso e copiar o comando cURL de amostra fornecido.


### Etapa 6 - Atualizar as integrações de API de terceiros {#ims-migration-step-6}

Você deve atualizar as integrações da API com seus sistemas de terceiros.

Para obter mais detalhes sobre as etapas de integração da API, incluindo um código de amostra para uma integração suave, consulte [Documentação de autenticação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Etapa 7 - Remover o operador técnico antigo {#ims-migration-step-7}


Após a migração de toda a integração de API/código personalizado com o usuário técnico da conta. Você pode excluir o operador técnico antigo do console do cliente do Campaign.

### Exemplos de chamadas SOAP{#ims-migration-samples}

Depois que o processo de migração é alcançado e validado, as chamadas Soap são atualizadas conforme abaixo:

* Antes da migração: não havia suporte para o token de acesso da conta técnica.

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
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```

* Após a migração: há suporte para o token de acesso da conta técnica. O token de acesso deve ser fornecido em `Authorization` cabeçalho como token de portador. O uso do token de sessão deve ser ignorado aqui, como mostrado na amostra de chamada soap abaixo.

  ```sql
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
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```
