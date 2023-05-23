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


# Configurar as contas externas

O Adobe Campaign vem com um conjunto de contas externas predefinidas. Para configurar conexões com sistemas externos, você pode criar novas contas externas.

As contas externas são usadas por processos técnicos, como workflows técnicos ou workflows da campanha. Por exemplo, ao configurar uma transferência de arquivos em um workflow ou uma troca de dados com qualquer outro aplicativo (Adobe Target, Experience Manager, etc.), você precisa selecionar uma conta externa.

Você pode acessar contas externas do Adobe Campaign **[!UICONTROL Explorer]**: navegue até **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* Como um usuário Cloud Services gerenciado, as contas externas são configuradas para sua instância pelo Adobe e não devem ser modificadas.
>
>* No contexto de um [Implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), um **[!UICONTROL Full FDA]** A conta externa do (ffda) gerencia a conexão entre o banco de dados local do Campaign e o banco de dados da nuvem ([!DNL Snowflake]).
>


## Contas externas específicas de campanha

As contas técnicas a seguir são usadas pela Adobe Campaign para ativar e executar processos específicos.

### Mensagens de rejeição {#bounce-mails-external-account}

>[!NOTE]
>
>A autenticação OAuth 2.0 do Microsoft Exchange Online para o recurso POP3 está disponível a partir do Campaign v8.3. Para verificar sua versão, consulte [nesta seção](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).

A conta externa de **Bounce mails** especifica a conta POP3 externa a ser usada para se conectar ao serviço de email. Todos os servidores configurados para acesso POP3 podem ser usados para receber emails de retorno.

Saiba mais sobre emails de entrada no [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html).

![](assets/bounce_external_1.png)

Para configurar a conta externa do **[!UICONTROL Bounce mails (defaultPopAccount)]**:

* **[!UICONTROL Server]** - URL do servidor POP3.

* **[!UICONTROL Port]** - Número da porta de conexão POP3. A porta padrão é 110.

* **[!UICONTROL Account]** -  Nome do usuário.

* **[!UICONTROL Password]** - Senha da conta do usuário.

* **[!UICONTROL Encryption]** - Tipo de criptografia escolhida entre **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** ou **[!UICONTROL POP3S]**.

   A conta externa de **Bounce mails** especifica a conta POP3 externa a ser usada para se conectar ao serviço de email. Todos os servidores configurados para acesso POP3 podem ser usados para receber emails de retorno.

* **[!UICONTROL Function]** - Email de entrada ou roteador SOAP

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Antes de configurar sua conta externa POP3 usando o Microsoft OAuth 2.0, primeiro é necessário registrar seu aplicativo no portal do Azure. Para obter mais informações, consulte esta [página](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

Para configurar um POP3 externo usando o Microsoft OAuth 2.0, verifique o **[!UICONTROL Microsoft OAuth 2.0]** e preencha os seguintes campos:

* **[!UICONTROL Azure tenant]** - A ID do Azure (ou a ID do diretório (locatário)) pode ser encontrada no **Fundamentos** lista suspensa da visão geral do aplicativo no portal do Azure.

* **[!UICONTROL Azure Client ID]** - A ID do cliente (ou a ID do aplicativo (cliente)) pode ser encontrada no **Fundamentos** lista suspensa da visão geral do aplicativo no portal do Azure.

* **[!UICONTROL Azure Client secret]** - A ID do segredo do cliente pode ser encontrada no **Segredos do cliente** coluna da **Certificados e segredos** do aplicativo no portal do Azure.

* **[!UICONTROL Azure Redirect URL]** - O URL de redirecionamento pode ser encontrado no **Autenticação** do aplicativo no portal do Azure. Ela deve terminar com a seguinte sintaxe `nl/jsp/oauth.jsp`, por exemplo, `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

   Depois de inserir suas credenciais diferentes, você pode clicar em **[!UICONTROL Setup the connection]** para concluir a configuração da conta externa.

### Roteamento {#routing}

A conta externa **[!UICONTROL Routing]** permite configurar cada canal disponível no Adobe Campaign, dependendo dos pacotes instalados.

>[!CAUTION]
>
>A variável **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) conta externa **não deve** estar ativado no Adobe Campaign v8.

### Instância de execução {#execution-instance}

No contexto de mensagens transacionais, as instâncias de execução são vinculadas à instância de controle e as conectam. Os templates de mensagem transacional são implantados nas instâncias de execução. Saiba mais sobre a arquitetura do Centro de mensagens em [esta página](../architecture/architecture.md#transac-msg-archi).

## Acesso a contas externas de Sistemas Externos

* **Banco de dados externo (FDA)** - A **Banco de dados externo** A conta externa do tipo é usada para se conectar a um banco de dados externo por meio do FDA (Federated Data Access — Acesso a Dados Federados). Saiba mais sobre a opção Federated Data Access (FDA) no [nesta seção](../connect/fda.md).

   Os bancos de dados externos compatíveis com o Adobe Campaign v8 estão listados na [Matriz de compatibilidade](../start/compatibility-matrix.md)

* **Twitter** - A **Twitter** A conta externa do tipo é usada para conectar o Campaign à sua conta da twitter, para postar mensagens em seu nome. Saiba mais sobre a integração do Twitter no [nesta seção](../connect/ac-tw.md).

## Contas externas de Integração de soluções Adobe

* **Adobe Experience Cloud** - A **[!UICONTROL Adobe Experience Cloud]** a conta externa é usada para implementar o Adobe Identity Management Service (IMS) para se conectar à Adobe Campaign. Saiba mais sobre o Adobe Identity Management Service (IMS) em [nesta seção](../start/connect.md#logon-to-ac).

* **Web Analytics** - A **[!UICONTROL Web Analytics (Adobe Analytics)]** a conta externa do é usada para configurar a transferência de dados do Adobe Analytics para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Adobe Analytics no [esta página](../connect/ac-aa.md).

* **Adobe Experience Manager** - A **[!UICONTROL AEM]** a conta externa do permite gerenciar o conteúdo dos deliveries de email, bem como os formulários diretamente no Adobe Experience Manager. Saiba mais sobre a integração Adobe Campaign - Adobe Analytics no [esta página](../connect/ac-aem.md).


## Contas externas do Conector CRM

* **Microsoft Dynamics CRM** - A **[!UICONTROL Microsoft Dynamics CRM]** conta externa do permite importar e exportar dados do Microsoft Dynamics para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Microsoft Dynamics CRM no [esta página](../connect/ac-ms-dyn.md).

* **Salesforce.com** - A **[!UICONTROL Salesforce CRM]** conta externa permite importar e exportar dados do Salesforce para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Salesforce.com CRM no [esta página](../connect/ac-sfdc.md).

## Contas externas de Dados de Transferência

Essas contas externas podem ser usadas para importar ou exportar dados para o Adobe Campaign usando um **[!UICONTROL Transfer file]** atividade de workflow. Saiba mais sobre **Transferência de arquivo** em fluxos de trabalho no [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html).

* **FTP e SFTP** - A **FTP** a conta externa do permite configurar e testar o acesso a um servidor fora do Adobe Campaign. Para configurar conexões com sistemas externos, como servidores SFTP ou FTP 898 usados para transferências de arquivos, você pode criar suas próprias contas externas.

   Para fazer isso, especifique nesta conta externa o endereço e as credenciais usadas para estabelecer a conexão com o servidor SFTP ou FTP.

* **Serviço de armazenamento simples Amazon (S3)** - A **AWS S3** conector pode ser usado para importar ou exportar dados para o Adobe Campaign usando um **[!UICONTROL Transfer file]** atividade de workflow. Como você está configurando essa nova conta externa, é necessário fornecer os seguintes detalhes:

   * **[!UICONTROL AWS S3 Account Server]**: o URL do servidor, preenchido da seguinte maneira:   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**: saiba como encontrar a ID da chave de acesso do AWS no [Documentação do Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: saiba como encontrar a chave de acesso secreta para o AWS no [Documentação do Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: saiba mais sobre regiões do AWS em [Documentação do Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * A caixa de seleção **[!UICONTROL Use server side encryption]** permite armazenar o arquivo no modo criptografado S3. Saiba como encontrar a ID da chave de acesso e a chave de acesso secreta no [Documentação do Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Armazenamento Azure Blob** - A **Azure** conta externa pode ser usada para importar ou exportar dados para o Adobe Campaign usando uma **[!UICONTROL Transfer file]** atividade de workflow. Para configurar o **Azure** para trabalhar com a Adobe Campaign, é necessário fornecer os seguintes detalhes:

   * **[!UICONTROL Server]**: a URL do seu servidor de armazenamento Azure Blob.

   * **[!UICONTROL Encryption]**: Tipo de criptografia entre **[!UICONTROL None]** ou **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: saiba como encontrar o seu **[!UICONTROL Access key]** in [Documentação do Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
