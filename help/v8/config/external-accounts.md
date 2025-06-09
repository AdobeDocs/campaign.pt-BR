---
title: Contas externas do Campaign
description: Contas externas do Campaign
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 42241364c1a23ae75d8f0aaf18a2cb1c04ce5b0c
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 14%

---


# Configurar as contas externas {#config-external-accounts}

O Adobe Campaign vem com um conjunto de contas externas predefinidas. Para configurar conexões com sistemas externos, você pode criar novas contas externas.

As contas externas são usadas por processos técnicos, como workflows técnicos ou workflows da campanha. Por exemplo, ao configurar uma transferência de arquivos em um workflow ou uma troca de dados com qualquer outro aplicativo (Adobe Target, Experience Manager etc.), você precisa selecionar uma conta externa.

Você pode acessar contas externas do Adobe Campaign **[!UICONTROL Explorer]**: navegue até **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* Como usuário do Managed Cloud Services, as contas externas são configuradas para sua instância pelo Adobe e não devem ser modificadas.
>
>* No contexto de uma [implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), uma conta externa **[!UICONTROL Full FDA]** (FDA) específica gerencia a conexão entre o banco de dados local do Campaign e o banco de dados da nuvem ([!DNL Snowflake]).
>

## Contas externas específicas de campanha {#ac-external-accounts}

As contas técnicas a seguir são usadas pela Adobe Campaign para ativar e executar processos específicos.

### Emails rejeitados {#bounce-mails-external-account}

>[!NOTE]
>
>A autenticação OAuth 2.0 do Microsoft Exchange Online para o recurso POP3 está disponível a partir do Campaign v8.3. Para verificar sua versão, consulte [esta seção](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

A conta externa de **Bounce mails** especifica a conta POP3 externa a ser usada para se conectar ao serviço de email. Todos os servidores configurados para acesso POP3 podem ser usados para receber emails de retorno.

Saiba mais sobre emails de entrada em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html){target="_blank"}.

![](assets/bounce_external_1.png)

Para configurar a conta externa do **[!UICONTROL Bounce mails (defaultPopAccount)]**:

* **[!UICONTROL Server]** - URL do servidor POP3.

* **[!UICONTROL Port]** - Número da porta de conexão POP3. A porta padrão é 110.

* **[!UICONTROL Account]** - Nome do usuário.

* **[!UICONTROL Password]** - Senha da conta de usuário.

* **[!UICONTROL Encryption]** - Tipo de criptografia escolhida entre **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** ou **[!UICONTROL POP3S]**.

  A conta externa de **Bounce mails** especifica a conta POP3 externa a ser usada para se conectar ao serviço de email. Todos os servidores configurados para acesso POP3 podem ser usados para receber emails de retorno.

* **[!UICONTROL Function]** - Email de entrada ou roteador SOAP

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Antes de configurar sua conta externa POP3 usando o Microsoft OAuth 2.0, primeiro é necessário registrar seu aplicativo no portal do Azure. Para obter mais informações, consulte esta [página](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

Para configurar um POP3 externo usando o Microsoft OAuth 2.0, marque a opção **[!UICONTROL Microsoft OAuth 2.0]** e preencha os seguintes campos:

* **[!UICONTROL Azure tenant]** - A ID do Azure (ou a ID do Diretório (locatário)) pode ser encontrada no menu suspenso **Essentials** da visão geral do seu aplicativo no portal do Azure.

* **[!UICONTROL Azure Client ID]** - A ID do Cliente (ou a ID do Aplicativo (cliente)) pode ser encontrada no menu suspenso **Essentials** da visão geral do seu aplicativo no portal do Azure.

* **[!UICONTROL Azure Client secret]** - A ID do segredo do cliente pode ser encontrada na coluna **Segredos do cliente** do menu **Certificados e segredos** do seu aplicativo no portal do Azure.

* **[!UICONTROL Azure Redirect URL]** - A URL de redirecionamento pode ser encontrada no menu **Autenticação** do seu aplicativo no portal do Azure. Ele deve terminar com a seguinte sintaxe `nl/jsp/oauth.jsp`, ex.: `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

  Depois de inserir suas credenciais diferentes, você pode clicar em **[!UICONTROL Setup the connection]** para concluir a configuração da conta externa.

### Roteamento {#routing}

A conta externa **[!UICONTROL Routing]** permite configurar cada canal disponível no Adobe Campaign, dependendo dos pacotes instalados.

Saiba mais sobre gerenciamento de conta externa e execução de entrega em [esta seção](../architecture/architecture.md#split).

### Instância de execução {#execution-instance}

No contexto de mensagens transacionais, as instâncias de execução são vinculadas à instância de controle e as conectam. Os templates de mensagem transacional são implantados na instância de execução. Saiba mais sobre a arquitetura do Centro de Mensagens em [esta página](../architecture/architecture.md#transac-msg-archi).

## Acesso a contas externas de Sistemas Externos {#external-syst-external-accounts}

* **Banco de dados externo (FDA)** - A conta externa do tipo **Banco de dados externo** é usada para se conectar a um banco de dados externo por meio do Federated Data Access (FDA). Saiba mais sobre a opção Federated Data Access (FDA) em [esta seção](../connect/fda.md).

  Os bancos de dados externos compatíveis com o Adobe Campaign v8 estão listados na [Matriz de compatibilidade](../start/compatibility-matrix.md)

* **X (anteriormente conhecido como Twitter)** - A conta externa do tipo **Twitter** é usada para conectar o Campaign à sua conta X e postar mensagens em seu nome. Saiba mais sobre a integração do X em [esta seção](../connect/ac-tw.md).

## Contas externas da Integração de soluções da Adobe {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - A conta externa **[!UICONTROL Adobe Experience Cloud]** é usada para implementar o Adobe Identity Management Service (IMS) para conexão com a Adobe Campaign. Saiba mais sobre o Adobe Identity Management Service (IMS) em [esta seção](../start/connect.md#logon-to-ac).

* **Web Analytics** - A conta externa **[!UICONTROL Web Analytics (Adobe Analytics)]** é usada para configurar a transferência de dados do Adobe Analytics para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Adobe Analytics em [esta página](../connect/ac-aa.md).

* **Adobe Experience Manager** - A conta externa do **[!UICONTROL AEM]** permite gerenciar o conteúdo dos emails entregues, bem como seus formulários diretamente no Adobe Experience Manager. Saiba mais sobre a integração Adobe Campaign - Adobe Analytics em [esta página](../connect/ac-aem.md).


## Contas externas do Conector CRM {#crm-external-accounts}

* **Microsoft Dynamics CRM** - A conta externa **[!UICONTROL Microsoft Dynamics CRM]** permite importar e exportar dados do Microsoft Dynamics para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Microsoft Dynamics CRM em [esta página](../connect/ac-ms-dyn.md).

* **Salesforce.com** - A conta externa **[!UICONTROL Salesforce CRM]** permite importar e exportar dados do Salesforce para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Salesforce.com CRM em [esta página](../connect/ac-sfdc.md).

## Contas externas de Dados de Transferência {#transfer-data-external-accounts}

Essas contas externas podem ser usadas para importar ou exportar dados para o Adobe Campaign usando uma atividade de fluxo de trabalho **[!UICONTROL Transfer file]**. Saiba mais sobre **Transferência de arquivos** em fluxos de trabalho em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html){target="_blank"}.

* **FTP e SFTP** - A conta externa **FTP** permite configurar e testar o acesso a um servidor fora do Adobe Campaign. Para configurar conexões com sistemas externos, como servidores SFTP ou FTP 898 usados para transferências de arquivos, você pode criar suas próprias contas externas.

  Para fazer isso, especifique nesta conta externa o endereço e as credenciais usadas para estabelecer a conexão com o servidor SFTP ou FTP.

  >[!NOTE]
  >
  >A partir da versão 8.5, agora é possível autenticar com segurança usando uma chave privada ao configurar a conta externa SFTP. [Saiba mais sobre o gerenciamento de chaves](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html){target="_blank"}.

* **Serviço de Armazenamento Simples da Amazon (S3)** - O conector do **AWS S3** pode ser usado para importar ou exportar dados para o Adobe Campaign usando uma atividade de fluxo de trabalho **[!UICONTROL Transfer file]**. Como você está configurando essa nova conta externa, é necessário fornecer os seguintes detalhes:

   * **[!UICONTROL AWS S3 Account Server]**: URL do servidor, preenchido da seguinte maneira:   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**: Saiba como encontrar sua ID da chave de acesso do AWS na [documentação do Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: Saiba como encontrar sua chave de acesso secreta para o AWS na [documentação do Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: Saiba mais sobre regiões do AWS em [documentação do Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * A caixa de seleção **[!UICONTROL Use server side encryption]** permite armazenar o arquivo no modo criptografado S3. Saiba como encontrar a ID da chave de acesso e a chave de acesso secreta na [documentação do Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Armazenamento Azure Blob** - A conta externa do **Azure** pode ser usada para importar ou exportar dados para a Adobe Campaign usando uma atividade de fluxo de trabalho **[!UICONTROL Transfer file]**. Para configurar a conta externa do **Azure** para funcionar com a Adobe Campaign, você precisa fornecer os seguintes detalhes:

   * **[!UICONTROL Server]**: URL do seu servidor de armazenamento Azure Blob.

   * **[!UICONTROL Encryption]**: Tipo de criptografia entre **[!UICONTROL None]** ou **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Saiba como encontrar seu **[!UICONTROL Access key]** na [documentação do Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
