---
title: Trabalhar com o Campaign e o SFDC
description: Saiba como trabalhar com o Campaign e o Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 34%

---

# Trabalhar com o Campaign e o SFDC{#crm-sfdc}

Saiba como configurar o conector do CRM do Campaign para conectar o Campaign v8 ao **Salesforce.com**.

Quando a configuração for concluída, a sincronização de dados entre sistemas será realizada por meio de uma atividade dedicada de fluxo de trabalho. [Saiba mais](crm-data-sync.md).

>[!NOTE]
>
>As versões do SFDC compatíveis estão detalhadas no Campaign [Matriz de compatibilidade](../start/compatibility-matrix.md).

Siga as etapas abaixo para configurar uma conta externa dedicada para importar e exportar dados do Salesforce para o Adobe Campaign.

## Criar a conexão{#new-sfdc-external-account}

Primeiro, você deve criar a conta externa do Salesforce.

1. Navegue pelo **[!UICONTROL Administration > Platform > External accounts]** do explorador do Campaign e criar uma conta externa.
1. Selecionar **[!UICONTROL Salesforce.com]** conta externa no **Tipo** seção.
1. Digite as configurações para habilitar a conexão.

   ![](assets/sfdc-external-account.png)

   Para configurar a conta externa do Salesforce CRM para funcionar com o Adobe Campaign, você precisa fornecer os seguintes detalhes:

   * Insira seu logon do Salesforce no **[!UICONTROL Account]** campo.
   * Insira sua senha do Salesforce.
   * Você pode ignorar o **[!UICONTROL Client identifier]** campo.
   * Copie/cole seu Salesforce **[!UICONTROL Security token]**
   * Selecione o **[!UICONTROL API version]**. As versões da API SFDC compatíveis estão listadas no Campaign [Matriz de compatibilidade](../start/compatibility-matrix.md).

1. Selecione o **Ativar** opção para ativar a conta no Campaign.

>[!NOTE]
>
>Para aprovar a configuração, você precisa fazer logoff e voltar ao console do Adobe Campaign.

## Selecionar tabelas para sincronizar{#sfdc-create-tables}

Agora você pode configurar tabelas para sincronizar.

1. Clique em **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. Selecione as tabelas para sincronizar e iniciar o processo.
1. Verifique o schema gerado no Adobe Campaign no nó **[!UICONTROL Administration > Configuration > Data schemas]**.

   Exemplo de a **Salesforce** esquema importado no Campaign:

   ![](assets/sfdc-schemas.png)

## Sincronize as enumerações{#sfdc-enum-sync}

Após a criação do esquema, você pode sincronizar enumerações automaticamente do Salesforce para o Adobe Campaign.

1. Abra o assistente no  **[!UICONTROL Synchronizing enumerations...]** link.
1. Selecione a lista discriminada do Adobe Campaign que corresponde à lista discriminada do Salesforce.
É possível substituir todos os valores de uma lista discriminada do Adobe Campaign pelos valores do CRM: para fazer isso, selecione **[!UICONTROL Yes]** na coluna **[!UICONTROL Replace]**.

   ![](assets/sfdc-enum.png)

1. Clique em **[!UICONTROL Next]** e depois **[!UICONTROL Start]** para começar a importar as listas discriminadas.

1. Navegue pelo **[!UICONTROL Administration > Platform > Enumerations]** nó para verificar valores importados. Saiba mais sobre enumerações em [esta página](../config/ui-settings.md#enumerations).

O Adobe Campaign e o Salesforce.com agora estão conectados. Você pode configurar a sincronização de dados entre os dois sistemas.

Para sincronizar dados entre o Adobe Campaign e o SFDC, crie um fluxo de trabalho e use o **[!UICONTROL CRM connector]** atividade.

Saiba mais sobre a sincronização de dados [nesta página](crm-data-sync.md).
