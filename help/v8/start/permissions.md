---
title: Conceder permissões ao Campaign v8
description: Saiba como conceder permissões ao Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 13%

---

# Introdução a permissões

No Adobe Campaign, os usuários são **operadores** e **grupos de operadores** representar funções de usuário.

Um operador é um usuário do Adobe Campaign que tem permissões para fazer o login e executar ações. Por padrão, os operadores são armazenados no nó **[!UICONTROL Administration > Access management > Operators]**.

O Adobe Campaign é fornecido com grupos de operadores integrados, como Gerentes de Campanha ou Supervisores de Workflow. Todos os grupos incorporados estão listados em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}.

Como membro de um grupo de operadores, um usuário tem direitos para executar operações, chamadas de &quot;Direitos nomeados&quot;, e tem acesso aos dados, que estão contidos nas pastas na **Explorer** exibir. Um operador pode ser membro de vários grupos de operadores: direitos e permissões de acesso são aditivos.

Permissões de concessão de direitos nomeados para:

* Executar operações Por exemplo, a variável **Analisar** no Editor de delivery é ativado para membros do **Operador Delivery** grupo que tem o **Preparar entrega** Nomeado à direita

* Acesso a pastas A associação de grupos de operadores pode conceder ou restringir direitos de acesso a pastas, alterando as configurações de segurança em pastas. [Saiba mais na documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}. Por exemplo, pode afetar: **Acesso de gravação** para criar novas entidades (como deliveries, perfis etc.), **Acesso de leitura** para usar entidades, **Excluir acesso** para excluir entidades.

## Zonas de segurança

Cada operador precisa ser vinculado a uma zona para fazer logon em uma instância e o IP do operador deve ser incluído nos endereços ou conjuntos de endereços definidos na zona de segurança. A configuração da zona de segurança é realizada no arquivo de configuração do servidor do Adobe Campaign.

Os operadores são vinculados a uma zona de segurança a partir do seu perfil no console, acessível na **[!UICONTROL Administration > Access management > Operators]** nó .

![](../assets/do-not-localize/speech.png)  Como usuário do Managed Cloud Services, o Adobe define as zonas de segurança para você. Para obter mais informações, [Adobe de contato](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}.

**Saiba mais na documentação do Campaign Classic v7**

* [Direitos nomeados embutidos](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [Grupos de operadores incorporados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [Etapas para configurar permissões](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}
