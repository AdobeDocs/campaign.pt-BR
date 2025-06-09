---
title: Conceder permissões para o Campaign v8
description: Saiba como conceder permissões para o Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 10%

---

# Introdução a permissões

No Adobe Campaign, os usuários são **operadores** e os **grupos de operadores** representam funções de usuário.

Um operador é um usuário do Adobe Campaign que tem permissões para fazer logon e executar ações. Por padrão, os operadores são armazenados no nó **[!UICONTROL Administration > Access management > Operators]**.

O Adobe Campaign vem com grupos de operadores integrados, como Gerentes de campanha ou Supervisores de fluxo de trabalho. Saiba mais sobre permissões em [esta seção](../start/gs-permissions.md)

Como membro de um grupo de operadores, um usuário tem direitos para executar operações, chamadas de &#39;Direitos Nomeados&#39;, e tem acesso aos dados, que estão contidos nas pastas na exibição **Explorer**. Um operador pode ser membro de vários grupos de operadores: direitos e permissões de acesso são aditivos.

Os direitos nomeados concedem permissões a:

* Executar operações
Por exemplo, o botão **Analisar** no editor de Entrega é ativado para membros do grupo **Operador de Entrega** que têm o direito nomeado **Preparar Entrega**

* Acesso a pastas
A associação de grupos de operadores pode conceder ou restringir direitos de acesso a pastas, alterando as configurações de segurança nas pastas. Saiba mais em [esta página](../start/folder-permissions.md). Por exemplo, isso pode afetar: **o acesso de gravação** para criar novas entidades (como entregas, perfis etc.), **o acesso de leitura** para usar entidades, **o acesso de exclusão** para excluir entidades.

## Zonas de segurança

Cada operador precisa ser vinculado a uma zona para fazer logon em uma instância e o operador IP deve ser incluído nos endereços ou conjuntos de endereços definidos na zona de segurança. A configuração da zona de segurança é realizada no arquivo de configuração do servidor do Adobe Campaign.

Os operadores são vinculados a uma zona de segurança em seu perfil no console, acessível no nó **[!UICONTROL Administration > Access management > Operators]**.

>[!NOTE]
>
>Como usuário do Managed Cloud Services, a Adobe define as zonas de segurança para você. Para obter mais informações, [contate a Adobe](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Saiba mais**

* [Direitos nomeados embutidos](../start/gs-permissions.md)

* [Etapas para configurar permissões](../start/manage-permissions.md)
