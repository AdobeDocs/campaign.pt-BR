---
title: Conceder permissões para o Campaign v8
description: Saiba como conceder permissões para o Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 13%

---

# Introdução a permissões

No Adobe Campaign, os usuários são **operadores** e **grupos de operadores** representar funções de usuário.

Um operador é um usuário do Adobe Campaign que tem permissões para fazer logon e executar ações. Por padrão, os operadores são armazenados no nó **[!UICONTROL Administration > Access management > Operators]**.

O Adobe Campaign vem com grupos de operadores integrados, como Gerentes de campanha ou Supervisores de fluxo de trabalho. Saiba mais sobre permissões no [nesta seção](../start/gs-permissions.md)

Como membro de um grupo de operadores, um usuário tem direitos para executar operações, chamadas de &quot;Direitos nomeados&quot;, e acesso aos dados, que estão contidos nas pastas na **Explorer** exibição. Um operador pode ser membro de vários grupos de operadores: direitos e permissões de acesso são aditivos.

Os direitos nomeados concedem permissões a:

* Executar operações Por exemplo, a variável **Analisar** no Editor de entrega é ativado para membros da **Operador de Entrega** grupo que tem o **Preparar entrega** Nomeado à direita

* O acesso a pastas Associação de grupos de operadores pode conceder ou restringir direitos de acesso a pastas, alterando as configurações de segurança nas pastas. Saiba mais [nesta página](../start/folder-permissions.md). Por exemplo, pode afetar: **Acesso de gravação** para criar novas entidades (como deliveries, perfis etc.), **Acesso de leitura** para usar entidades, **Excluir acesso** para excluir entidades.

## Zonas de segurança

Cada operador precisa ser vinculado a uma zona para fazer logon em uma instância e o operador IP deve ser incluído nos endereços ou conjuntos de endereços definidos na zona de segurança. A configuração da zona de segurança é realizada no arquivo de configuração do servidor do Adobe Campaign.

Os operadores são vinculados a uma zona de segurança a partir de seu perfil no console, acessível no **[!UICONTROL Administration > Access management > Operators]** nó.

![](../assets/do-not-localize/speech.png)  Como um usuário Cloud Services gerenciado, o Adobe define as zonas de segurança para você. Para obter mais informações, [Adobe de contato](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Saiba mais**

* [Direitos nomeados embutidos](../start/gs-permissions.md)

* [Etapas para configurar permissões](../start/manage-permissions.md)
