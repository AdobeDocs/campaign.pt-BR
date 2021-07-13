---
product: Adobe Campaign
title: Conceder permissões ao Campaign v8
description: Saiba como conceder permissões ao Campaign v8
feature: Públicos
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 7%

---

# Introdução a permissões

No Adobe Campaign, os usuários são **operadores** e **grupos de operadores** representam funções de usuário.

O Adobe Campaign é fornecido com grupos de operadores integrados, como Gerentes de Campanha ou Supervisores de Workflow. Todos os grupos incorporados estão listados na documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

Como membro de um grupo de operadores, um usuário tem direitos para executar operações, chamadas de &quot;Direitos nomeados&quot;, e tem acesso a dados, que estão contidos em pastas na visualização **Explorer**. Um operador pode ser membro de vários grupos de operadores: direitos e permissões de acesso são aditivos.

Permissões de concessão de direitos nomeados para:

* Executar operações
Por exemplo, o botão **Analisar** no Editor de Delivery é ativado para membros do grupo **Operador de Delivery** que têm o **Preparar Delivery** Direito Nomeado

* Acesso a pastas
A associação de grupos de operadores pode conceder ou restringir direitos de acesso a pastas, alterando as configurações de segurança em pastas. [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}. Por exemplo, pode afetar: **Write access** para criar novas entidades (como remessas, perfis etc.), **Read access** para usar entidades, **Delete access** para excluir entidades.

**Saiba mais na documentação do Campaign Classic v7:**

↗️ [Direitos Nomeados Incorporados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

↗️ [Grupos de Operadores Incorporados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

↗️ [Etapas para configurar permissões](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}

↗️ [Configurações de segurança em pastas](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}