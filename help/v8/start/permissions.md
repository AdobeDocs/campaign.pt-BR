---
product: Adobe Campaign
title: Conceder permissões ao Campaign v8
description: Saiba como conceder permissões ao Campaign v8
feature: Públicos
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 4bd67cd3e4e88015d8044f07ca95927b6d7867f3
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 1%

---

# Introdução a permissões

No Adobe Campaign, os usuários são **operadores** e **grupos de operadores** representam funções de usuário.

O Adobe Campaign é fornecido com grupos de operadores integrados, como Gerentes de Campanha ou Supervisores de Workflow. Todos os grupos incorporados estão listados na documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

Como membro de um grupo de operadores, um usuário tem direitos para executar operações, chamadas de &quot;Direitos nomeados&quot;, e tem acesso a dados, que estão contidos em pastas na visualização **Explorer**. Um operador pode ser membro de vários grupos de operadores: direitos e permissões de acesso são aditivos.

Permissões de concessão de direitos nomeados para:

* Executar operações
Por exemplo, o botão **Analisar** no Editor de Delivery é ativado para membros do grupo **Operador de Delivery** que têm o **Preparar Delivery** Direito Nomeado

* Acesso a pastas
A associação de grupos de operadores pode conceder ou restringir direitos de acesso a pastas, alterando as configurações de segurança em pastas. [Saiba mais na documentação](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder) do Campaign Classic v7. Por exemplo, pode afetar: **Write access** para criar novas entidades (como remessas, perfis etc.), **Read access** para usar entidades, **Delete access** para excluir entidades.

**Saiba** mais sobre a documentação do Campaign Classic v7:

[!DNL :arrow_upper_right:] [Direitos nomeados embutidos](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html)

[!DNL :arrow_upper_right:] [Grupos de operadores incorporados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

[!DNL :arrow_upper_right:] [Etapas para configurar permissões](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html)

[!DNL :arrow_upper_right:] [Configurações de segurança em pastas](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder).