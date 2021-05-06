---
solution: Campaign Classic
product: campaign
title: Contas externas do Campaign
description: Contas externas do Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 0e0cd6eb9fcf656c9ba6c72cd1a782098f9399fe
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 15%

---

# Configurar contas externas

O Adobe Campaign vem com um conjunto de contas externas predefinidas. Para configurar conexões com sistemas externos, você pode criar novas contas externas.

As contas externas são usadas por processos técnicos, como workflows técnicos ou workflows da campanha. Por exemplo, ao configurar uma transferência de arquivos em um workflow ou uma troca de dados com qualquer outro aplicativo (Adobe Target, Experience Manager etc.), é necessário selecionar uma conta externa.

:seta_upper_right: Saiba como criar e configurar contas externas na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts.html)

Uma conta externa específica gerencia a conexão entre o banco de dados local do Campaign e o banco de dados do Cloud ([!DNL Snowflake]).

:voice_balloon: Como um usuário do Managed Cloud Services, [!DNL Snowflake] a conta externa é configurada para sua instância pelo Adobe.

Você pode acessar essa conta externa para verificar as configurações e executar workflows de replicação. Para fazer isso, siga as etapas abaixo:

1. Em Campanha **[!UICONTROL Explorer]**, clique em **[!UICONTROL Administration > Platform > External Accounts]**.

1. Selecione a conta externa **[!UICONTROL Full FDA]**.

![](assets/snowflake-ext-account.png)

As configurações globais são exibidas no **[!UICONTROL General tab]**.

Use a guia **[!UICONTROL Parameters]** e depois o botão **[!UICONTROL Deploy functions]** para criar funções.

![](assets/snowflake-parameters.png)

**ADICIONAR PARÂMETROS DESC AQUI**

Use a guia **[!UICONTROL Full FDA]** para forçar a execução do workflow de replicação.

![](assets/snowflake-full-fda.png)

**ADICIONAR DETALHES AQUI**

