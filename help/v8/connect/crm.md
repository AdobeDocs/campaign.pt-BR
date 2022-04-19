---
title: Trabalhe com o Campaign e seu CRM
description: Saiba como trabalhar com o Campaign e seu CRM
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 9ad8623b48021eab7b53c7fbc69f3baa165afd3f
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 27%

---

# Conecte seu CRM com o Campaign {#gs-crm}

O Adobe Campaign fornece vários conectores de CRM para vincular sua plataforma a sistemas de terceiros. Esses conectores de CRM permitem sincronizar contatos, contas, compras, etc. Eles facilitam a integração de seu aplicativo com vários aplicativos de terceiros e corporativos.

Esses conectores permitem uma integração rápida e fácil de dados: O Adobe Campaign fornece um assistente dedicado para coletar e selecionar entre as tabelas disponíveis no CRM. Isso garante a sincronização bidirecional para assegurar que os dados estejam sempre atualizados em todos os sistemas.

Os principais benefícios são:

* Mensagens consistentes entre vendas e marketing: a integração do Adobe Campaign com seu CRM fornece aos dois sistemas acesso ao insight do cliente e ao histórico de marketing por email, permitindo que todas as mensagens do cliente compartilhem as mesmas mensagens consistentes.

* Visualização holística de todos os dados de cliente e prospecto: ao integrar o Adobe Campaign ao seu CRM, é possível compartilhar e acessar o histórico de marketing por email em cada contato a partir do sistema do CRM.

* Ative os dados do CRM em qualquer canal: com dados de contato sincronizados com o Adobe Campaign, as comunicações podem ser enviadas em qualquer canal online ou offline com o Campaign, incluindo push móvel, no aplicativo, email ou mala direta.


>[!NOTE]
>
>Esse recurso está disponível no Adobe Campaign através dos **conectores dedicados do CRM**.

## Sistemas compatíveis {#compatible-crm-systems-and-limitations}

O CRM e as versões compatíveis estão detalhados na [Matriz de compatibilidade](../start/compatibility-matrix.md) do Campaign.

>[!CAUTION]
>
> Os conectores CRM do Campaign funcionam somente com um URL seguro (https).

## Etapas de implementação {#crm-implementation-steps}

Saiba mais sobre o procedimento passo a passo para conectar o Campaign e o Microsoft Dynamics no [esta página](ac-ms-dyn.md).

Saiba mais sobre o procedimento passo a passo para conectar o Campaign e o Salesforce.com em [esta página](ac-sfdc.md).

A sincronização de dados entre o Adobe Campaign e o CRM é realizada por meio de uma atividade dedicada de workflow. Crie seus workflows para automatizar a sincronização entre o Campaign e seu CRM. Você pode criar um workflow que importa contatos por meio do Microsoft Dynamics, sincroniza com os dados existentes do Adobe Campaign, exclui os contatos duplicados e atualiza o banco de dados do Adobe Campaign. Saiba mais [nesta página](crm-data-sync.md).
