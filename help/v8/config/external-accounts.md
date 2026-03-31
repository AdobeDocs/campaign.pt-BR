---
title: Contas externas do Campaign
description: Configure contas externas para conectar o Campaign a sistemas externos, como bancos de dados POP3, FDA, CRM, armazenamento e soluções da Adobe.
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: fce4f85386c18d0919a85e938d3c1f2cca8d79b9
workflow-type: tm+mt
source-wordcount: '1758'
ht-degree: 5%

---


# Configurar as contas externas {#config-external-accounts}

O Adobe Campaign vem com um conjunto de contas externas predefinidas. Para configurar conexões com sistemas externos, você pode criar novas contas externas.

As contas externas são usadas por processos técnicos, como fluxos de trabalho técnicos ou fluxos de trabalho da campanha. Por exemplo, ao configurar uma transferência de arquivos em um workflow ou uma troca de dados com qualquer outro aplicativo (Adobe Target, Experience Manager etc.), você precisa selecionar uma conta externa.

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

Saiba mais sobre emails de entrada em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html?lang=pt-BR){target="_blank"}.

![](assets/bounce_external_1.png)

Para configurar a conta externa do **[!UICONTROL Bounce mails (defaultPopAccount)]**:

* **[!UICONTROL Server]** - URL do servidor POP3.

* **[!UICONTROL Port]** - Número da porta de conexão POP3. A porta padrão é 110.

* **[!UICONTROL Account]** - Nome do usuário.

* **[!UICONTROL Password]** - Senha da conta de usuário.

* **[!UICONTROL Encryption]** - Tipo de criptografia escolhida entre **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** ou **[!UICONTROL POP3S]**.

* **[!UICONTROL Function]** - Email de entrada ou roteador SOAP.

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Antes de configurar sua conta externa POP3 usando o Microsoft OAuth 2.0, primeiro é necessário registrar seu aplicativo no portal do Azure. Para obter mais informações, consulte esta [página](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

Para configurar uma conta externa POP3 usando o Microsoft OAuth 2.0, marque a opção **[!UICONTROL Microsoft OAuth 2.0]** e preencha os seguintes campos:

* **[!UICONTROL Azure tenant]** - A Azure ID (ou a ID do Diretório (locatário)) pode ser encontrada na lista suspensa **Essentials** da visão geral do seu aplicativo no portal do Azure.

* **[!UICONTROL Azure Client ID]** - A ID do Cliente (ou a ID do Aplicativo (cliente)) pode ser encontrada na lista suspensa do **Essentials** da sua visão geral do aplicativo, no portal do Azure.

* **[!UICONTROL Azure Client secret]** - A ID do segredo do cliente pode ser encontrada na coluna **Segredos do cliente** do menu **Certificados e segredos** do seu aplicativo no portal do Azure.

* **[!UICONTROL Azure Redirect URL]** - A URL de redirecionamento pode ser encontrada no menu **Autenticação** do seu aplicativo no portal do Azure. Ele deve terminar com a seguinte sintaxe `nl/jsp/oauth.jsp`, ex.: `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

Depois de inserir suas credenciais, clique em **[!UICONTROL Setup the connection]** para concluir a configuração da conta externa.

### Roteamento {#routing}

A conta externa **[!UICONTROL Routing]** permite configurar cada canal disponível no Adobe Campaign, dependendo dos pacotes instalados.

Saiba mais sobre gerenciamento de conta externa e execução de entrega em [esta seção](../architecture/architecture.md#split).

### Instância de execução {#execution-instance}

No contexto de mensagens transacionais, a instância de execução é vinculada à instância de controle e a conecta. Os templates de mensagem transacional são implantados na instância de execução. Saiba mais sobre a arquitetura do Centro de Mensagens em [esta página](../architecture/architecture.md#transac-msg-archi).

## Acesso a contas externas de Sistemas Externos {#external-syst-external-accounts}

### Federated Data Access (FDA) {#fda-external-accounts}

A conta externa do tipo **Banco de dados externo** é usada para se conectar a um banco de dados externo via FDA (Federated Data Access — Acesso a Dados Federados). Saiba mais sobre a opção Federated Data Access (FDA) em [esta seção](../connect/fda.md).

>[!NOTE]
>
>Os bancos de dados externos compatíveis com o Adobe Campaign v8 estão listados na [Matriz de compatibilidade](../start/compatibility-matrix.md). As conexões FDA usam drivers ODBC; com o Adobe Campaign Managed Cloud Services, o driver ODBC e a configuração da conta externa são definidos pela Adobe.

As definições de configuração da conta externa dependem do mecanismo de banco de dados. Com o Adobe Campaign Managed Cloud Services, a configuração da conta externa é executada pelo Adobe.

Para obter a interface da Web do Campaign (v8), consulte:

* [Criar uma conta externa](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/create-external-account){target="_blank"}
* [Contas do banco de dados externo](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database){target="_blank"}

A página da interface da Web do Campaign fornece uma lista mais abrangente dos tipos de provedor de **banco de dados externo**, incluindo:

* **[Amazon Redshift](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#amazon-redshift){target="_blank"}** / **[Amazon Redshift (herdado)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#amazon-redshift-legacy){target="_blank"}** - Conecte o Campaign aos ambientes de data warehouse do AWS Redshift.
* **[Azure Synapse Analytics](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#azure-synapse-analytics){target="_blank"}** - Conecte o Campaign aos pools dedicados de SQL do Microsoft Azure Synapse.
* **[Databricks](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#databricks){target="_blank"}** - Conecte o Campaign às cargas de trabalho de SQL e de lokehouse do Databricks.
* **[Google BigQuery](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#google-bigquery){target="_blank"}** - Conectar o Campaign aos conjuntos de dados de análise do Google Cloud BigQuery.
* **[Microsoft SQL Server](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#microsoft-sql-server){target="_blank"}** - Conecte o Campaign a bancos de dados SQL Server locais ou hospedados.
* **[MySQL](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#mysql){target="_blank"}** - Conectar o Campaign aos bancos de dados MySQL para consultas e fluxos de trabalho federados.
* **[Netezza](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#netezza){target="_blank"}** - Conectar o Campaign aos sistemas IBM Netezza / Performance Server.
* **[ODBC (Sybase ASE, Sybase IQ)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#odbc-sybase-ase-sybase-iq){target="_blank"}** - Conectar o Campaign por meio do ODBC a mecanismos de banco de dados Sybase.
* **[Retransmissão HTTP para o banco de dados remoto](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#http-relay-to-remote-database){target="_blank"}** - Conecte-se a um banco de dados remoto por meio de um ponto de extremidade de retransmissão HTTP.
* **[Oracle](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#oracle){target="_blank"}** - Conecte o Campaign aos bancos de dados Oracle para casos de uso de acesso federado.
* **[PostgreSQL](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#postgresql){target="_blank"}** - Conecte o Campaign aos bancos de dados PostgreSQL usando contas externas FDA.
* **[SAP HANA](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#sap-hana){target="_blank"}** - Conecte o Campaign aos ambientes do banco de dados em memória do SAP HANA.
* **[Snowflake](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#snowflake){target="_blank"}** - Conecte o Campaign aos ambientes da plataforma de dados na nuvem da Snowflake.
* **[Teradata](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#teradata){target="_blank"}** - Conecte o Campaign aos sistemas de data warehouse corporativos da Teradata.
* **[Vertica Analytics](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#vertica-analytics){target="_blank"}** - Conecte o Campaign aos bancos de dados de análise OpenText Vertica.
* **[Microsoft Fabric](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/external-account-database#fabric){target="_blank"}** - Conectar o Campaign aos serviços Microsoft Fabric SQL e de armazenamento.

Para obter detalhes sobre o console do cliente herdado e referências adicionais, consulte a [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/pt-br/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts){target="_blank"}.

#### Conta externa de databricks {#databricks-external-accounts}

A conexão Databricks FDA usa o driver ODBC Databricks. A partir do Campaign v8.9.1, as contas externas do Databricks oferecem suporte à autenticação OAuth2 por meio da entidade de serviço (fluxo de credenciais de cliente não interativo), fornecendo autenticação segura para acesso a dados federados.

Saiba mais sobre entidades de serviço na [documentação do Microsoft](https://learn.microsoft.com/en-us/azure/databricks/admin/users-groups/service-principals){target="_blank"}.

Para configurar a autenticação OAuth2 por meio da entidade de serviço no Campaign:

1. O administrador do espaço de trabalho de Databricks ativa entidades de serviço no espaço de trabalho de Databricks e gera credenciais. Para autorizar o acesso aos recursos do Azure Databricks com OAuth, crie um segredo OAuth (usado para gerar tokens de acesso OAuth para autenticação).
2. No Adobe Campaign, crie ou edite uma conta externa de Databricks e abra a guia **OAuth**.
3. Cole as credenciais nos campos da guia OAuth da conta externa de Databricks.
4. Use **[!UICONTROL Test the connection]** para validar a configuração.

#### Conta externa do Snowflake {#snowflake-external-accounts}

A conexão FDA do Snowflake usa o driver ODBC do Snowflake. A partir do Campaign v8.9.1, as contas externas do Snowflake oferecerão suporte à autenticação OAuth2, fornecendo autenticação segura para acesso a dados federados.

Saiba mais sobre o OAuth no Snowflake na [documentação do Snowflake](https://docs.snowflake.com/en/user-guide/oauth-intro){target="_blank"}.

Primeiro, é necessário executar as seguintes etapas no Snowflake:

1. Antes de configurar a conta externa do Snowflake usando o OAuth 2.0, primeiro é necessário criar uma Integração de segurança do OAuth no Snowflake. A função **ACCOUNTADMIN** é necessária para criar a integração de segurança.

   Saiba mais sobre como criar a Integração de segurança do OAuth na [documentação do Snowflake](https://docs.snowflake.com/en/sql-reference/sql/create-security-integration-oauth-snowflake){target="_blank"}.

1. Você pode consultar a ID do cliente e o Segredo do cliente usando:

   ```
   select system$show_oauth_client_secrets('OAUTH_INTEGRATION_ABC'); // use uppercase letters
   ```

Para configurar a autenticação OAuth2 no Campaign, siga estas etapas:

1. No Adobe Campaign, crie ou edite uma conta externa do Snowflake e verifique a opção **[!UICONTROL Use OAuth 2.0]**.

1. Defina o servidor, banco de dados e esquema e abra a guia **[!UICONTROL OAuth]**.

1. Defina os parâmetros de integração de segurança **[!UICONTROL Client ID]**, **[!UICONTROL Client Secret]** e **[!UICONTROL Redirect URL]**. Esses parâmetros são obtidos em sua Integração de segurança do Snowflake OAuth. Consulte a [documentação do Snowflake](https://docs.snowflake.com/en/user-guide/oauth-custom){target="_blank"}.

1. Clique em **[!UICONTROL Proceed to Sign in]** para fazer logon manual. Uma nova janela do navegador será aberta, onde você será solicitado a inserir suas credenciais de usuário do Snowflake.

1. Após a conclusão do processo de autenticação, a conta é autenticada pelo número de dias definido na Integração de Segurança OAuth do Snowflake (usando o parâmetro `OAUTH_REFRESH_TOKEN_VALIDITY`). O token de atualização é armazenado na conta externa.

>[!CAUTION]
>
>Observe que a URL de redirecionamento deve sempre direcionar a `oauth.jsp` na máquina do servidor de aplicativos do Campaign por HTTPS (porta 443). Além disso, domínios de servidor com sublinhados não são compatíveis ao usar OAuth. Use domínios de servidor sem sublinhados se pretender usar OAuth.

### X (anteriormente conhecido como Twitter) {#twitter-external-account}

A conta externa do tipo **Twitter** é usada para conectar o Campaign à sua conta X, para postar mensagens em seu nome. Saiba mais sobre a integração do X em [esta seção](../connect/ac-tw.md).

## Contas externas de integração de soluções da Adobe {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - A conta externa **[!UICONTROL Adobe Experience Cloud]** é usada para implementar o Adobe Identity Management Service (IMS) para conexão com o Adobe Campaign. Saiba mais sobre o Adobe Identity Management Service (IMS) em [esta seção](../start/connect.md#logon-to-ac).

* **Web Analytics** - A conta externa **[!UICONTROL Web Analytics (Adobe Analytics)]** é usada para configurar a transferência de dados do Adobe Analytics para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Adobe Analytics em [esta página](../connect/ac-aa.md).

* **Adobe Experience Manager** - A conta externa do **[!UICONTROL AEM]** permite gerenciar o conteúdo dos emails entregues, bem como seus formulários diretamente no Adobe Experience Manager. Saiba mais sobre a integração Adobe Campaign - Adobe Experience Manager em [esta página](../connect/ac-aem.md).


## Contas externas do Conector CRM {#crm-external-accounts}

* **Microsoft Dynamics CRM** - A conta externa **[!UICONTROL Microsoft Dynamics CRM]** permite importar e exportar dados do Microsoft Dynamics para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Microsoft Dynamics CRM em [esta página](../connect/ac-ms-dyn.md).

* **Salesforce.com** - A conta externa **[!UICONTROL Salesforce CRM]** permite importar e exportar dados do Salesforce para o Adobe Campaign. Saiba mais sobre a integração Adobe Campaign - Salesforce.com CRM em [esta página](../connect/ac-sfdc.md).

## Transferir dados de contas externas {#transfer-data-external-accounts}

Essas contas externas podem ser usadas para importar ou exportar dados para o Adobe Campaign usando uma atividade de fluxo de trabalho **[!UICONTROL Transfer file]**. Saiba mais sobre **Transferência de arquivos** em fluxos de trabalho em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html?lang=pt-BR){target="_blank"}.

* **FTP e SFTP** - A conta externa **FTP** permite configurar e testar o acesso a um servidor fora do Adobe Campaign. Para configurar conexões com sistemas externos, como servidores SFTP ou FTP usados para transferências de arquivos, você pode criar suas próprias contas externas.

  Para fazer isso, especifique nesta conta externa o endereço e as credenciais usadas para estabelecer a conexão com o servidor SFTP ou FTP.

  >[!NOTE]
  >
  >A partir da versão 8.5, agora é possível autenticar com segurança usando uma chave privada ao configurar a conta externa SFTP. [Saiba mais sobre o gerenciamento de chaves](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=pt-BR){target="_blank"}.

* **Serviço de Armazenamento Simples da Amazon (S3)** - O conector do **AWS S3** pode ser usado para importar ou exportar dados para o Adobe Campaign usando uma atividade de fluxo de trabalho **[!UICONTROL Transfer file]**. Ao configurar essa conta externa, você precisa fornecer os seguintes detalhes:

   * **[!UICONTROL AWS S3 Account Server]**: URL do servidor, no formato `<S3bucket name>.s3.amazonaws.com/<s3object path>`.

   * **[!UICONTROL AWS access key ID]**: Saiba como encontrar sua ID da chave de acesso do AWS na [documentação do Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: Saiba como encontrar sua chave de acesso secreta para o AWS na [documentação do Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: Saiba mais sobre regiões do AWS em [documentação do Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * A caixa de seleção **[!UICONTROL Use server-side encryption]** permite armazenar o arquivo no modo criptografado S3. Saiba como encontrar a ID da chave de acesso e a chave de acesso secreta na [documentação do Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Armazenamento de Blob da Azure** - A conta externa **Azure** pode ser usada para importar ou exportar dados para a Adobe Campaign usando uma atividade de fluxo de trabalho **[!UICONTROL Transfer file]**. Para configurar a conta externa do **Azure** para funcionar com o Adobe Campaign, forneça os seguintes detalhes:

   * **[!UICONTROL Server]**: URL do servidor de armazenamento Azure Blob.

   * **[!UICONTROL Encryption]**: Tipo de criptografia: **[!UICONTROL None]** ou **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Saiba como encontrar seu **[!UICONTROL Access key]** na [documentação do Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.

* **Microsoft Fabric** - A conta externa **Microsoft Fabric** permite importar e exportar dados entre o Microsoft Fabric e o Adobe Campaign usando a atividade de fluxo de trabalho **[!UICONTROL Transfer file]**. Para configurar essa integração, forneça os seguintes detalhes:

   * **[!UICONTROL Server]**: URL do servidor de armazenamento do Microsoft Fabric.

   * **[!UICONTROL Application ID]**: o identificador exclusivo do aplicativo usado para autenticar e acessar os recursos do Microsoft Fabric.

   * **[!UICONTROL Client secret]**: a chave ou senha de autenticação associada ao aplicativo, necessária para se conectar com segurança ao Microsoft Fabric.
