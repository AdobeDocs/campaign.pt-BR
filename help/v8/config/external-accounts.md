---
title: Contas externas do Campaign
description: Contas externas do Campaign
feature: Application Settings
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: c46eaa73deed643a4e92928b6ce2b1beb1596d73
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 19%

---


# Configurar contas externas

O Adobe Campaign vem com um conjunto de contas externas predefinidas. Para configurar conexões com sistemas externos, você pode criar novas contas externas.

As contas externas são usadas por processos técnicos, como workflows técnicos ou workflows da campanha. Por exemplo, ao configurar uma transferência de arquivos em um workflow ou uma troca de dados com qualquer outro aplicativo (Adobe Target, Experience Manager etc.), é necessário selecionar uma conta externa.

Você pode acessar contas externas do Adobe Campaign **[!UICONTROL Explorer]**: navegue até **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* Como um usuário do Managed Cloud Services, as contas externas são configuradas para sua instância pelo Adobe e não devem ser modificadas.
>
>* No contexto de um [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), um **[!UICONTROL Full FDA]** (ffda) a conta externa gerencia a conexão entre o banco de dados local do Campaign e o banco de dados do Cloud ([!DNL Snowflake]).
>


## Contas externas específicas de campanha

As contas técnicas a seguir são usadas pela Adobe Campaign para habilitar e executar processos específicos.

### Mensagens de rejeição {#bounce-mails-external-account}

>[!NOTE]
>
>A autenticação OAuth 2.0 do Microsoft Exchange Online para o recurso POP3 está disponível a partir do Campaign v8.3. Para verificar sua versão, consulte [esta seção](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).

A conta externa de **Bounce mails** especifica a conta POP3 externa a ser usada para se conectar ao serviço de email. Todos os servidores configurados para acesso POP3 podem ser usados para receber emails de retorno.

Saiba mais sobre emails de entrada em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html).

![](assets/bounce_external_1.png)

Para configurar a conta externa do **[!UICONTROL Bounce mails (defaultPopAccount)]**:

* **[!UICONTROL Server]** - URL do servidor POP3.

* **[!UICONTROL Port]** - Número da porta de conexão POP3. A porta padrão é 110.

* **[!UICONTROL Account]** -  Nome do usuário.

* **[!UICONTROL Password]** - Senha da conta do usuário.

* **[!UICONTROL Encryption]** - Tipo de criptografia escolhida entre **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** ou **[!UICONTROL POP3S]**.

   A conta externa de **Bounce mails** especifica a conta POP3 externa a ser usada para se conectar ao serviço de email. Todos os servidores configurados para acesso POP3 podem ser usados para receber emails de retorno.

* **[!UICONTROL Function]** - E-mail de entrada ou roteador SOAP

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Antes de configurar sua conta externa POP3 usando o Microsoft OAuth 2.0, primeiro é necessário registrar seu aplicativo no portal do Azure. Para obter mais informações, consulte esta [página](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

Para configurar uma externa POP3 usando o Microsoft OAuth 2.0, marque a opção **[!UICONTROL Microsoft OAuth 2.0]** e preencha os seguintes campos:

* **[!UICONTROL Azure tenant]** - A ID do Azure (ou a ID do diretório (locatário) pode ser encontrada no **Fundamentos** lista suspensa da visão geral do aplicativo no portal do Azure.

* **[!UICONTROL Azure Client ID]** - A ID do cliente (ou a ID do aplicativo (cliente) pode ser encontrada no **Fundamentos** lista suspensa da visão geral do aplicativo no portal do Azure.

* **[!UICONTROL Azure Client secret]** - A ID secreta do cliente pode ser encontrada no **Segredo do cliente** da coluna **Certificados e segredos** do seu aplicativo no portal do Azure.

* **[!UICONTROL Azure Redirect URL]** - O URL de redirecionamento pode ser encontrado na função **Autenticação** do seu aplicativo no portal do Azure. Ela deve terminar com a seguinte sintaxe `nl/jsp/oauth.jsp`, por exemplo `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

   Depois de inserir suas diferentes credenciais, clique em **[!UICONTROL Setup the connection]** para concluir a configuração da conta externa.

### Roteamento {#routing}

A conta externa **[!UICONTROL Routing]** permite configurar cada canal disponível no Adobe Campaign, dependendo dos pacotes instalados.

>[!CAUTION]
>
>O **[!UICONTROL Internal email delivery routing]** Conta externa (defaultEmailBulk) **não deve** estar habilitado no Adobe Campaign v8.

### Instância de execução {#execution-instance}

No contexto de mensagens transacionais, as instâncias de execução são vinculadas à instância de controle e as conectam. Os templates de mensagem transacional são implantados nas instâncias de execução. Saiba mais sobre a arquitetura do Centro de mensagens em [esta página](../architecture/architecture.md#transac-msg-archi).

## Acesso a contas externas de sistemas externos

* **Banco de dados externo (FDA)** - O **Banco de dados externo** A conta externa do tipo é usada para se conectar a um banco de dados externo por meio do Federated Data Access (FDA). Saiba mais sobre a opção Federated Data Access (FDA) em [esta seção](../connect/fda.md).

   Os bancos de dados externos compatíveis com o Adobe Campaign v8 são listados na variável [Matriz de compatibilidade](../start/compatibility-matrix.md)

* **Twitter** - O **Twitter** A conta externa do tipo é usada para conectar o Campaign à sua conta twitter, para postar mensagens em seu nome. Saiba mais sobre a integração do Twitter no [esta seção](../connect/ac-tw.md).

## Contas externas de integração de solução Adobe

* **Adobe Experience Cloud** - O **[!UICONTROL Adobe Experience Cloud]** a conta externa é usada para implementar o Adobe Identity Management Service (IMS) para se conectar à Adobe Campaign. Saiba mais sobre o Adobe Identity Management Service (IMS) em [esta seção](../start/connect.md#logon-to-ac).

* **Web Analytics** - O **[!UICONTROL Web Analytics (Adobe Analytics)]** a conta externa é usada para configurar a transferência de dados do Adobe Analytics para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Adobe Analytics em [esta página](../connect/ac-aa.md).

* **Adobe Experience Manager** - O **[!UICONTROL AEM]** a conta externa do permite gerenciar o conteúdo dos deliveries de email, bem como seus formulários diretamente no Adobe Experience Manager. Saiba mais sobre a integração Adobe Campaign - Adobe Analytics em [esta página](../connect/ac-aem.md).


## Conector CRM Contas externas

* **Microsoft Dynamics CRM** - O **[!UICONTROL Microsoft Dynamics CRM]** a conta externa do permite importar e exportar os dados do Microsoft Dynamics para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Microsoft Dynamics CRM em [esta página](../connect/ac-ms-dyn.md).

* **Salesforce.com** - O **[!UICONTROL Salesforce CRM]** a conta externa do permite importar e exportar dados do Salesforce para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Salesforce.com CRM em [esta página](../connect/ac-sfdc.md).

## Transferir contas externas de dados

Essas contas externas podem ser usadas para importar ou exportar dados para o Adobe Campaign usando um **[!UICONTROL Transfer file]** atividade do workflow. Saiba mais sobre **Transferência de arquivos** em workflows em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html).

* **FTP e SFTP** - O **FTP** a conta externa permite configurar e testar o acesso a um servidor fora do Adobe Campaign. Para configurar conexões com sistemas externos, como servidores SFTP ou FTP 898 usados para transferências de arquivos, você pode criar suas próprias contas externas.

   Para fazer isso, especifique nesta conta externa o endereço e as credenciais usadas para estabelecer a conexão com o servidor SFTP ou FTP.

* **Serviço de Armazenamento Simples da Amazon (S3)** - O **AWS S3** O conector pode ser usado para importar ou exportar dados para o Adobe Campaign usando um **[!UICONTROL Transfer file]** atividade do workflow. Como você está configurando essa nova conta externa, é necessário fornecer os seguintes detalhes:

   * **[!UICONTROL AWS S3 Account Server]**: URL do seu servidor, preenchido da seguinte maneira:   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**: Saiba como encontrar a ID da chave de acesso do AWS em [Documentação do Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: Saiba como encontrar sua chave de acesso secreta para o AWS em [Documentação do Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: Saiba mais sobre as regiões do AWS em [Documentação do Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * A caixa de seleção **[!UICONTROL Use server side encryption]** permite armazenar o arquivo no modo criptografado S3. Saiba como encontrar a ID da chave de acesso e a chave de acesso secreta no [Documentação do Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Armazenamento Azure Blob** - O **Azure** a conta externa pode ser usada para importar ou exportar dados para o Adobe Campaign usando um **[!UICONTROL Transfer file]** atividade do workflow. Para configurar o **Azure** para funcionar com o Adobe Campaign, você precisa fornecer os seguintes detalhes:

   * **[!UICONTROL Server]**: URL do servidor de armazenamento do Azure Blob.

   * **[!UICONTROL Encryption]**: Tipo de criptografia entre **[!UICONTROL None]** ou **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Saiba como encontrar seu **[!UICONTROL Access key]** em [Documentação do Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
