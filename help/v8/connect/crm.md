---
solution: Campaign Classic
product: campaign
title: Trabalhe com o Campaign e seu CRM
description: 'Saiba como trabalhar com o Campaign e seu CRM '
feature: Visão geral
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8c9f59067cd0e5a39e84315e5836a32bdf7a0864
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 31%

---

# Conecte seu CRM com o Campaign {#gs-crm}

O Adobe Campaign fornece vários conectores de CRM para vincular sua plataforma a sistemas de terceiros. Esses conectores de CRM permitem sincronizar contatos, contas, compras, etc. Eles facilitam a integração de seu aplicativo com vários aplicativos de terceiros e corporativos.

Esses conectores permitem uma integração rápida e fácil de dados: O Adobe Campaign fornece um assistente dedicado para coletar e selecionar entre as tabelas disponíveis no CRM. Isso garante a sincronização bidirecional para assegurar que os dados estejam sempre atualizados em todos os sistemas.

>[!NOTE]
>
>Esse recurso está disponível no Adobe Campaign através dos **conectores dedicados do CRM**.

## Sistemas compatíveis {#compatible-crm-systems-and-limitations}

O CRM e as versões compatíveis estão detalhados na [Matriz de compatibilidade](../start/compatibility-matrix.md) do Campaign.

**NOTA**  - Os conectores CRM funcionam somente com um URL seguro (https).

## Etapas de implementação {#crm-implementation-steps}

:seta_upper_right: Saiba mais sobre o procedimento passo a passo para conectar o Campaign e o Microsoft Dynamics em [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)

:seta_upper_right: Saiba mais sobre o procedimento passo a passo para conectar o Campaign e o Salesforce na [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


A sincronização de dados entre o Adobe Campaign e o CRM é realizada por meio de uma atividade dedicada de workflow. Crie seus workflows para automatizar a sincronização entre o Campaign e seu CRM. Você pode criar um workflow que importa contatos por meio do Microsoft Dynamics, sincroniza com os dados existentes do Adobe Campaign, exclui contatos duplicados e atualiza o banco de dados do Adobe Campaign.

:seta_upper_right: Saiba mais em [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)

