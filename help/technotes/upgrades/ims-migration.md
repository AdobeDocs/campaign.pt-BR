---
title: Migração de usuários técnicos para o console do Adobe Developer
description: Saiba como migrar operadores técnicos do Campaign para a conta técnica no console do Adobe Developer
feature: Technote
role: Admin
exl-id: 775c5dbb-ef73-48dd-b163-23cfadc3dab8
source-git-commit: 07c2a7460c407a0afb536d8b64f4105d8bc547f4
workflow-type: tm+mt
source-wordcount: '1547'
ht-degree: 0%

---

# Migração de operadores técnicos do Campaign para o Console do Adobe Developer {#migrate-tech-users-to-ims}

Como parte do esforço para reforçar a segurança e o processo de autenticação, a partir do Campaign v8.5, o processo de autenticação para o Campaign v8 está sendo aprimorado. Os operadores técnicos agora podem usar o [Sistema Adobe Identity Management (IMS)](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"} para se conectar ao Campaign. Saiba mais sobre o novo processo de autenticação de servidor para servidor no [Documentação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Um operador técnico é um perfil de usuário do Campaign que foi explicitamente criado para integração com a API. Este artigo detalha as etapas necessárias para migrar um operador técnico para uma conta técnica por meio do console do Adobe Developer.


## Você será afetado?{#ims-impacts}

Se você estiver fazendo chamadas de API de um sistema externo ao Campaign para a instância de Marketing do Campaign ou para a instância do Centro de mensagens em tempo real, será necessário migrar o(s) operador(es) técnico(s) para a(s) conta(s) técnica(s) por meio do Console do Adobe Developer, conforme detalhado abaixo.

Essa alteração é aplicável a partir do Campaign v8.5 e será **obrigatório** a partir do Campaign v8.6.


## Processo de migração {#ims-migration-procedure}

Siga as etapas abaixo para criar contas técnicas no Console do Adobe Developer e, em seguida, use essas contas recém-criadas para alterar os métodos de autenticação de todos os sistemas externos que fazem chamadas de API no Adobe Campaign.

Uma visão geral das etapas são:

* Criação de um projeto no Console do Adobe Developer
* Atribuir as APIs apropriadas ao projeto recém-criado
* Conceder os Perfis de produto do Campaign necessários ao projeto
* Atualização das APIs para usar as credenciais de conta técnica recém-criadas
* Remover os operadores técnicos herdados da instância do Campaign

### Pré-requisitos para a migração{#ims-migration-prerequisites}

<!--To be able to create the technical accounts which replace the technical operators, the prerequisite that the proper Campaign Product Profiles exist within the Admin Console for all Campaign instances need to be validated. You can learn more about Product Profiles within the Adobe Console in [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.-->

Para chamadas de API nas instâncias do Centro de mensagens, um perfil de produto deve ter sido criado durante a atualização para o Campaign v8.5 ou durante o provisionamento da instância. Este perfil de produto é nomeado como:

`campaign - <your campaign instance> - messagecenter`

Se você já estiver usando a autenticação baseada em IMS para acesso de usuários ao Campaign, os perfis de produto necessários para as chamadas de API já deverão existir no Admin Console. Se você usar um grupo de operadores personalizado no Campaign para as chamadas de API para a instância de marketing, deverá criar esse perfil de produto no Admin Console.

Para outros casos, entre em contato com o Gerenciador de transição de Adobe para que as equipes técnicas de Adobe possam migrar seus grupos de operadores e direitos nomeados existentes para os Perfis de produto dentro do Admin Console.


### Etapa 1 — criação do projeto do Campaign no console do Adobe Developer {#ims-migration-step-1}

As integrações são criadas como parte de um **Projeto** no console do Adobe Developer. Saiba mais sobre Projetos em [Documentação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

Você pode usar qualquer projeto criado anteriormente por você ou criar um novo projeto. As etapas para criar um projeto estão detalhadas na [Documentação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}. Você pode encontrar as principais etapas abaixo

<!--
For this migration, you must add below APIs in your project: **I/O Management API** and **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)-->

Para criar um novo projeto, clique **Criar novo projeto** na tela principal do Console do Adobe Developer.

![](assets/New-Project.png)

Você pode usar o **Editar projeto** botão para renomear este projeto.


### Etapa 2 - Adicionar APIs ao projeto {#ims-migration-step-2}

Na tela do projeto recém-criado, adicione as APIs necessárias para usar esse projeto como uma conta técnica para suas chamadas de API para o Adobe Campaign.

Para adicionar APIs ao seu projeto, siga estas etapas:

1. Clique em **Adicionar API** para selecionar as APIs a serem adicionadas ao projeto.
   ![](assets/do-not-localize/ims-updates-01.png)
1. Selecione e adicione a API do Adobe Campaign ao seu projeto marcando a caixa no canto superior direito do cartão Adobe Campaign, que aparece ao passar o mouse sobre o cartão
   ![](assets/do-not-localize/ims-updates-02.png)
1. Clique em **Próxima** na parte inferior da tela.

### Etapa 3 - Selecionar o tipo de autenticação  {#ims-migration-step-3}

No **Configurar API** selecione o tipo de autenticação necessário. **Servidor OAuth para servidor** A autenticação é necessária para este projeto. Verifique se está selecionado e clique em **Próxima** na parte inferior da tela.

![](assets/do-not-localize/ims-updates-03.png)

<!--
Once your project is created in the Adobe Developer Console, add an API that uses Server-to-Server authentication. Learn how to set up the OAuth Server-to-Server credential in [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

When the API has been successfully connected, you can access the newly generated credentials including Client ID and Client Secret, as well as generate an access token.-->

### Etapa 4 - Selecionar os perfis de produto {#ims-migration-step-4}

Conforme descrito na seção pré-requisitos, você deve atribuir os perfis de produto apropriados a serem usados pelo projeto. Nesta etapa, você deve selecionar o perfil ou os perfis de produto a serem usados pela conta técnica que está sendo criada.

Se essa conta técnica for usada para fazer chamadas de API para a instância do Centro de mensagens, selecione o perfil de produto Adobe create que termina com `messagecenter`.

Para chamadas de API para as instâncias de Marketing, selecione o perfil de produto correspondente à instância e ao Grupo de operadores.

Após selecionar os perfis de produto necessários, clique em **Salvar API configurada** na parte inferior da tela.

<!--
You can now add your Campaign product profile to the project, as detailed below:

1. Open the Adobe Campaign API.
1. Click the **Edit product profiles** button

    ![](assets/do-not-localize/ims-edit-api.png)

1. Assign all the relevant Product Profiles to the API, for example 'messagecenter', and save your changes.
1. Browse to the **Credential details** tab of your project, and copy the **Technical Account Email** value.-->

### Etapa 5 - Adicionar a API de gerenciamento de E/S ao projeto {#ims-migration-step-5}


Na tela do projeto, clique na guia **[!UICONTROL + Add to Project]** e escolha **[!UICONTROL API]** no canto superior esquerdo da tela para poder adicionar a API de gerenciamento de E/S a este projeto.

![](assets/do-not-localize/ims-updates-04.png)

No **Adicionar uma API** , role para baixo para encontrar a **API de gerenciamento de E/S** cartão. Selecione-a clicando na caixa de seleção exibida ao passar o mouse sobre o cartão. Clique em **Próxima** na parte inferior da tela.

![](assets/do-not-localize/ims-updates-05.png)


No **Configurar API** , a autenticação de servidor para servidor do OAuth já existe. Clique em **Salvar API configurada** na parte inferior da tela.


![](assets/do-not-localize/ims-updates-06.png)

Isso leva você de volta à tela Projeto na API de gerenciamento de E/S do projeto recém-criado. Clique no nome do projeto na navegação estrutural na parte superior da tela a ser retornada à página principal Detalhes do projeto.


### Etapa 6 - Verificar a configuração do projeto {#ims-migration-step-6}

Revise seu projeto para garantir que ele seja semelhante ao mostrado abaixo com o **API de gerenciamento de E/S** e **API do Adobe Campaign** visível na seção Produtos e serviços e **Servidor OAuth para servidor** na seção Credenciais.

![](assets/do-not-localize/ims-updates-07.png)


### Etapa 7 — validação da configuração {#ims-migration-step-7}

Para experimentar a conexão, siga as etapas detalhadas na [Guia de credenciais do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} para gerar um token de acesso e copiar o comando cURL de amostra fornecido. Você pode criar uma chamada soap usando essas credenciais para testar se é possível autenticar e se conectar às instâncias do Adobe Campaign corretamente. Recomendamos fazer essa validação antes de fazer todas as alterações nas integrações de API de terceiros.

### Etapa 8 - Atualizar as integrações de API de terceiros {#ims-migration-step-8}

Agora você deve atualizar todas as integrações de API que fazem chamadas para o Adobe Campaign para usar a conta técnica recém-criada.

Para obter mais detalhes sobre as etapas de integração da API, incluindo um código de amostra para uma integração suave, consulte [Documentação de autenticação do console do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Abaixo estão exemplos de chamadas SOAP mostrando as chamadas de antes e depois da migração para os sistemas de terceiros.

Ao usar a autenticação do Adobe Identity Management System (IMS), para gerar um arquivo WSDL, você deve adicionar o `Authorization: Bearer <IMS_Technical_Token_Token>` na chamada do carteiro:

```
curl --location --request POST 'https://<instance_url>/nl/jsp/schemawsdl.jsp?schema=nms:rtEvent' \--header 'Authorization: Bearer <Technical account access token>'
```

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

### Etapa 9 - (opcional) Atualizar o operador de conta técnica no console do cliente do Campaign {#ims-migration-step-9}

Esta etapa é opcional e só está disponível nas Instâncias de marketing, não em nenhuma instância do Centro de mensagens. Se permissões específicas de pasta ou direitos nomeados tiverem sido definidos para o Operador técnico, não por meio dos Grupos de operadores atribuídos. Agora, seria necessário atualizar o usuário recém-criado da Conta técnica no Admin Console para conceder as permissões da pasta ou os direitos nomeados necessários.

Observe que o usuário da conta técnica NÃO existirá no Adobe Campaign até que pelo menos uma chamada à API seja feita para a instância do Campaign, momento em que o IMS criará o usuário no Campaign. Se não conseguir localizar os usuários técnicos no Campaign, certifique-se de enviar uma chamada à API como descrito [na Etapa 7](#ims-migration-step-7).

1. Para aplicar as alterações necessárias para o novo Usuário da conta técnica, localize-as no console do cliente do Campaign por endereço de email. Esse endereço de email foi criado durante as etapas de Criação e autenticação de projeto acima.

   Você pode localizar esse endereço de email clicando no link **Servidor OAuth para servidor** no cabeçalho **Credenciais** seção do Projeto.

   ![](assets/do-not-localize/ims-updates-07.png)

   Na tela Credenciais, role para baixo para localizar o **Email da conta técnica** e clique no link **Copiar** botão.

   ![](assets/do-not-localize/ims-updates-08.png)

1. Agora é necessário atualizar o operador técnico recém-criado no console do cliente do Adobe Campaign. Você deve aplicar as permissões existentes da pasta do operador técnico ao novo operador técnico.

   Para atualizar esse operador, siga estas etapas:

   1. No explorador do console do cliente do Campaign, navegue até o **Administração > Gerenciamento de acesso > Operadores**.
   1. Acesse o operador técnico existente usado para APIs.
   1. Navegue até as permissões da pasta e verifique os direitos.
   1. Aplique as mesmas permissões ao operador técnico recém-criado. O email deste operador é o **Email da conta técnica** valor copiado anteriormente.
   1. Salve as alterações.


>[!CAUTION]
>
>O novo operador técnico deve ter feito pelo menos uma chamada à API para ser adicionada ao console do cliente do Campaign.
>

### Etapa 10 - Remover o operador técnico antigo do Adobe Campaign {#ims-migration-step-10}

Depois de migrar todos os sistemas de terceiros para usar a nova conta técnica com autenticação IMS, é possível excluir o operador técnico antigo do console do cliente do Campaign.

Para fazer isso, faça logon no console do cliente do Campaign, navegue até **Administração > Gerenciamento de acesso > Operadores** e localizar os usuários técnicos antigos e excluí-los.
