---
title: Conceder permissões ao Campaign v8
description: Saiba como conceder permissões ao Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: c3ed24e16d5a8bc67b8a8c959bbf485ea0fd919c
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 13%

---

# Introdução a permissões

No Adobe Campaign, os usuários são **operadores** e **grupos de operadores** representam funções de usuário.

Um operador é um usuário do Adobe Campaign que tem permissões para fazer o login e executar ações. Por padrão, os operadores são armazenados no nó **[!UICONTROL Administration > Access management > Operators]**.

O Adobe Campaign é fornecido com grupos de operadores integrados, como Gerentes de Campanha ou Supervisores de Workflow. Todos os grupos incorporados são listados na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}.

Como membro de um grupo de operadores, um usuário tem direitos para executar operações, chamadas de &quot;Direitos nomeados&quot;, e tem acesso a dados, que estão contidos em pastas na visualização **Explorer**. Um operador pode ser membro de vários grupos de operadores: direitos e permissões de acesso são aditivos.

Permissões de concessão de direitos nomeados para:

* Executar operações
Por exemplo, o botão **Analisar** no Editor de Delivery é ativado para membros do grupo **Operador de Delivery** que têm o **Preparar Delivery** Direito Nomeado

* Acesso a pastas
A associação de grupos de operadores pode conceder ou restringir direitos de acesso a pastas, alterando as configurações de segurança em pastas. [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}. Por exemplo, pode afetar: **Write access** para criar novas entidades (como remessas, perfis etc.), **Read access** para usar entidades, **Delete access** para excluir entidades.

## Zonas de segurança

Cada operador precisa ser vinculado a uma zona para fazer logon em uma instância e o IP do operador deve ser incluído nos endereços ou conjuntos de endereços definidos na zona de segurança. A configuração da zona de segurança é realizada no arquivo de configuração do servidor do Adobe Campaign.

Os operadores são vinculados a uma zona de segurança a partir do seu perfil no console, acessível no nó **[!UICONTROL Administration > Access management > Operators]**.

?? Como usuário do Managed Cloud Services, o Adobe define as zonas de segurança para você. Para obter mais informações, [entre em contato com o Adobe](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}.

**Saiba mais na documentação do Campaign Classic v7**

* [Direitos nomeados incorporados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [Grupos de Operadores Integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [Etapas para configurar permissões](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}
