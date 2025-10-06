---
title: Trabalhar com o Campaign e o SFDC
description: Saiba como trabalhar com o Campaign e o Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: fbde111671fb972f6c96ba45eba4c8a88dbcac64
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 28%

---

# Trabalhar com o Campaign e o SFDC{#crm-sfdc}

Saiba como configurar o conector do Campaign CRM para conectar o Campaign v8 ao **Salesforce.com**.

Quando a configuração for concluída, a sincronização de dados entre sistemas será realizada por meio de uma atividade dedicada de fluxo de trabalho. [Saiba mais](crm-data-sync.md).

>[!NOTE]
>
>As versões do SFDC com suporte estão detalhadas na [Matriz de compatibilidade](../start/compatibility-matrix.md) do Campaign.

Siga as etapas abaixo para configurar uma conta externa dedicada para importar e exportar dados do Salesforce para o Adobe Campaign.

## Criar a conexão{#new-sfdc-external-account}

Primeiro, você deve criar a conta externa do Salesforce.

1. Navegue pelo nó **[!UICONTROL Administration > Platform > External accounts]** do explorador do Campaign e crie uma conta externa.
1. Selecione a conta externa **[!UICONTROL Salesforce.com]** na seção **Type**.
1. Digite as configurações para habilitar a conexão.

   ![](assets/sfdc-external-account.png)

   Para configurar a conta externa do Salesforce CRM para funcionar com o Adobe Campaign, você precisa fornecer os seguintes detalhes:

   * Insira seu logon do Salesforce no campo **[!UICONTROL Account]**.
   * Digite sua senha do Salesforce.
   * Você pode ignorar o campo **[!UICONTROL Client identifier]**.
   * Copiar/colar seu Salesforce **[!UICONTROL Security token]**
   * Selecione seu **[!UICONTROL API version]**. As versões da API do SFDC com suporte estão listadas na [Matriz de compatibilidade](../start/compatibility-matrix.md) do Campaign.

1. Selecione a opção **Habilitar** para ativar a conta no Campaign.

>[!NOTE]
>
>Para aprovar a configuração, você precisa fazer logoff e voltar ao Console do cliente do Adobe Campaign.

## Selecionar tabelas para sincronizar{#sfdc-create-tables}

Agora você pode configurar tabelas para sincronizar.

1. Clique no **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. Selecione as tabelas para sincronizar e iniciar o processo.
1. Verifique o esquema gerado no Adobe Campaign no nó **[!UICONTROL Administration > Configuration > Data schemas]**.

   Exemplo de um esquema **Salesforce** importado no Campaign:

   ![](assets/sfdc-schemas.png)

## Sincronize as enumerações{#sfdc-enum-sync}

Após a criação do esquema, você pode sincronizar enumerações automaticamente do Salesforce para o Adobe Campaign.

1. Abra o assistente no link **[!UICONTROL Synchronizing enumerations...]**.
1. Selecione a lista discriminada do Adobe Campaign que corresponde à lista discriminada do Salesforce.
É possível substituir todos os valores de uma enumeração do Adobe Campaign pelos valores do CRM: para fazer isso, selecione **[!UICONTROL Yes]** na coluna **[!UICONTROL Replace]**.

   ![](assets/sfdc-enum.png)

1. Clique em **[!UICONTROL Next]** e depois em **[!UICONTROL Start]** para começar a importar as listas discriminadas.

1. Navegue pelo nó **[!UICONTROL Administration > Platform > Enumerations]** para verificar os valores importados. Saiba mais sobre enumerações em [esta página](../config/ui-settings.md#enumerations).

O Adobe Campaign e o Salesforce.com agora estão conectados. Você pode configurar a sincronização de dados entre os dois sistemas.

Para sincronizar dados entre dados do Adobe Campaign e do SFDC, crie um fluxo de trabalho e use a atividade **[!UICONTROL CRM connector]**.

Saiba mais sobre a sincronização de dados [nesta página](crm-data-sync.md).

Saiba mais sobre o gerenciamento de enumeração no Campaign [nesta página](../dev/enumerations.md).
