---
product: Adobe Campaign
title: Contas externas do Campaign
description: Contas externas do Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
source-git-commit: ff2c49a2b4f22cde7ebb798d9f565e133c0268fc
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 33%

---


# Configurar contas externas

O Adobe Campaign vem com um conjunto de contas externas predefinidas. Para configurar conexões com sistemas externos, você pode criar novas contas externas.

As contas externas são usadas por processos técnicos, como workflows técnicos ou workflows da campanha. Por exemplo, ao configurar uma transferência de arquivos em um workflow ou uma troca de dados com qualquer outro aplicativo (Adobe Target, Experience Manager etc.), é necessário selecionar uma conta externa.

Você pode acessar contas externas do Adobe Campaign **[!UICONTROL Explorer]**: navegue até **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>Uma conta externa específica **[!UICONTROL Full FDA]** (ffda) gerencia a conexão entre o banco de dados local do Campaign e o banco de dados do Cloud ([!DNL Snowflake]).
>
>Como um usuário do Managed Cloud Services, essa conta externa é configurada para sua instância pelo Adobe. Ele não deve ser modificado.


## Contas externas específicas de campanha

As contas técnicas a seguir são usadas pela Adobe Campaign para habilitar e executar processos específicos.

[!DNL :speech_balloon:] Como usuário do Managed Cloud Services, o Adobe configura todas as contas externas específicas da campanha para você.

* **Emails de devolução (POP3)**

   A conta externa de **Bounce mails** especifica a conta POP3 externa a ser usada para se conectar ao serviço de email. Todos os servidores configurados para acesso POP3 podem ser usados para receber emails de retorno.

   [!DNL :arrow_upper_right:] Saiba mais sobre emails de entrada na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html)

* **Roteamento**

   A conta externa **[!UICONTROL Routing]** permite configurar cada canal disponível no Adobe Campaign, dependendo dos pacotes instalados.

   >[!CAUTION]
   >
   >A conta externa **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) **não deve** ser ativada no Adobe Campaign v8.

* **Instância de execução**

   No contexto de mensagens transacionais, as instâncias de execução são vinculadas à instância de controle e as conectam. Os templates de mensagem transacional são implantados nas instâncias de execução.

   [!DNL :bulb:] Saiba mais sobre a arquitetura do Centro de mensagens  [nesta página](../dev/architecture.md#transac-msg-archi).

## Acesso a contas externas de sistemas externos

* **Banco de dados externo (FDA)**

   Use a conta externa do tipo **External database** para se conectar a um banco de dados externo via FDA.

   Bancos de dados externos compatíveis com o Adobe Campaign v8 são listados na [Matriz de compatibilidade](../start/compatibility-matrix.md)

   [!DNL :bulb:] Saiba mais sobre a opção Federated Data Access (FDA)  [nesta seção](../connect/fda.md).

## Contas externas de integração de solução Adobe

* **Adobe Experience Cloud**

   Para se conectar ao console do Adobe Campaign por meio de uma Adobe ID, é necessário configurar a conta externa **[!UICONTROL Adobe Experience Cloud]**.

   [!DNL :bulb:] Saiba mais sobre o Adobe Identity Management Service (IMS)  [nesta seção](../start/connect.md#connect-ims).

   [!DNL :speech_balloon:] Como usuário do Managed Cloud Services,  [entre em contato com a ](../start/campaign-faq.md#support) Adobe para implementar o Adobe IMS com o Campaign.

* **Web Analytics**

   Use a conta externa **[!UICONTROL Web Analytics (Adobe Analytics)]** para configurar a transferência de dados do Adobe Analytics para o Adobe Campaign.

   [!DNL :bulb:] Saiba mais sobre a integração Adobe Campaign - Adobe Analytics  [nesta página](../connect/ac-aa.md).

   [!DNL :speech_balloon:] Como um usuário do Managed Cloud Services,  [entre em contato com a ](../start/campaign-faq.md#support) Adobe para integrar o Adobe Analytics ao Campaign.

   * **Adobe Experience Manager**
   A conta externa **[!UICONTROL AEM]** permite gerenciar o conteúdo dos deliveries de email, assim como os formulários diretamente no Adobe Experience Manager.

   [!DNL :bulb:] Saiba mais sobre a integração Adobe Campaign - Adobe Analytics  [nesta página](../connect/ac-aem.md).

   [!DNL :speech_balloon:] Como usuário do Managed Cloud Services,  [entre em contato com a ](../start/campaign-faq.md#support) Adobe para integrar o Adobe Experience Manager ao Adobe Campaign.


## Contas Externas do Conector CRM

* **Microsoft Dynamics CRM**

   A conta externa **[!UICONTROL Microsoft Dynamics CRM]** permite importar e exportar os dados do Microsoft Dynamics para o Adobe Campaign.

   [!DNL :bulb:] Saiba mais sobre a integração Adobe Campaign - Microsoft Dynamics CRM  [nesta página](../connect/crm.md).

   Com o tipo de implantação **[!UICONTROL Web API]** e autenticação **[!UICONTROL Password credentials]**, é necessário fornecer os seguintes detalhes:

   * **[!UICONTROL Account]**: Conta usada para entrar no Microsoft CRM.

   * **[!UICONTROL Server]**: A URL do servidor Microsoft CRM.

   * **[!UICONTROL Client identifier]**: ID do cliente que pode ser encontrado no portal de gerenciamento do Microsoft Azure na  **[!UICONTROL Update your code]** categoria , no  **[!UICONTROL Client ID]** campo .

   * **[!UICONTROL CRM version]**: Versão da CRM entre **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** ou **[!UICONTROL Dynamics CRM 2016]**.
   Com o tipo de implantação **[!UICONTROL Web API]** e autenticação **[!UICONTROL Certificate]**, é necessário fornecer os seguintes detalhes:

   * **[!UICONTROL Server]**: A URL do servidor Microsoft CRM.

   * **[!UICONTROL Private Key (Base64 encoded)]**: Chave privada codificada em Base64

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**: ID do cliente que pode ser encontrado no portal de gerenciamento do Microsoft Azure na  **[!UICONTROL Update your code]** categoria , no  **[!UICONTROL Client ID]** campo .

   * **[!UICONTROL CRM version]**: Versão da CRM entre **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** ou **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   A conta externa **[!UICONTROL Salesforce CRM]** permite importar e exportar dados do Salesforce para o Adobe Campaign.

   Para configurar a conta externa do Salesforce CRM para funcionar com o Adobe Campaign, você precisa fornecer os seguintes detalhes:

   * **[!UICONTROL Account]**: Conta usada para fazer logon no Salesforce CRM.

   * **[!UICONTROL Password]**: Senha usada para fazer logon no Salesforce CRM.

   * **[!UICONTROL Client identifier]**: Saiba como encontrar o identificador do cliente  [nesta página](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Security token]**: Saiba como encontrar o token de segurança  [nesta página](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL API version]**: Selecione a versão da API. Para essa conta externa, você precisa configurar o Salesforce CRM com o assistente de configuração.

## Transferir contas externas de dados

Essas contas externas podem ser usadas para importar ou exportar dados para o Adobe Campaign usando uma atividade de workflow **[!UICONTROL Transfer file]** .

[!DNL :arrow_upper_right:] Saiba mais sobre Transferência de arquivos em workflows na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html)

* **FTP e SFTP**

   A conta externa **FTP** permite configurar e testar o acesso a um servidor fora do Adobe Campaign. Para configurar conexões com sistemas externos, como servidores SFTP ou FTP 898 usados para transferências de arquivos, você pode criar suas próprias contas externas.
Para fazer isso, especifique nesta conta externa o endereço e as credenciais usadas para estabelecer a conexão com o servidor SFTP ou FTP.

* **Serviço de Armazenamento Simples da Amazon (S3)**

   O conector **AWS S3** pode ser usado para importar ou exportar dados para o Adobe Campaign usando uma atividade de workflow **[!UICONTROL Transfer file]**. Como você está configurando essa nova conta externa, é necessário fornecer os seguintes detalhes:

   * **[!UICONTROL AWS S3 Account Server]**: URL do seu servidor, preenchido da seguinte maneira:    ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**: Saiba como encontrar a ID da chave de acesso AWS na documentação do  [Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

   * **[!UICONTROL Secret access key to AWS]**: Saiba como encontrar sua chave de acesso secreta para o AWS na documentação do  [Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL AWS Region]**: Saiba mais sobre as regiões do AWS na documentação do  [Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

   * A caixa de seleção **[!UICONTROL Use server side encryption]** permite armazenar o arquivo no modo criptografado S3. Saiba como localizar a ID da chave de acesso e a chave de acesso secreta na [documentação do Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Armazenamento Azure Blob**

   A conta externa **Azure** pode ser usada para importar ou exportar dados para o Adobe Campaign usando uma atividade de workflow **[!UICONTROL Transfer file]**. Para configurar a conta externa do **Azure** para funcionar com o Adobe Campaign, você precisa fornecer os seguintes detalhes:

   * **[!UICONTROL Server]**: URL do servidor de armazenamento do Azure Blob.

   * **[!UICONTROL Encryption]**: Tipo de criptografia entre  **[!UICONTROL None]** ou  **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Saiba como encontrar seu  **[!UICONTROL Access key]** na documentação da  [Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).

