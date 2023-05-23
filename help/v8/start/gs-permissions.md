---
title: Introdução a permissões no Campaign v8
description: Saiba mais sobre as etapas para definir permissões no Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: b63dc1616bc7ce1387a7bd0590c289b59f11b33f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 15%

---

# Introdução a permissões{#gs-permissions}

O Adobe Campaign permite definir e gerenciar os direitos atribuídos aos usuários. Veja um conjunto de direitos e restrições que autorizam ou negam:

* Acesso a determinados recursos
* O acesso a certos dados
* Acesso a determinadas ações (criar, modificar, excluir)

Essas permissões são definidas combinando permissões de grupo de operadores, direitos nomeados e permissões em pastas.

No Adobe Campaign, os usuários são **operadores** e **grupos de operadores** representar funções de usuário. Um operador é um usuário do Adobe Campaign que tem permissões para fazer logon e executar ações. Os usuários são criados no Admin Console. As permissões se aplicam a perfis de usuário ou grupos de usuários. Há dois tipos de permissões que você pode conceder:

* Você pode definir grupos de operadores para atribuir direitos e, em seguida, associar os operadores a um ou mais grupos. Isso permite que você reutilize os direitos e torne os perfis de operadores mais consistentes. Também facilita o gerenciamento e a manutenção de perfis de usuário.
* Você pode atribuir direitos nomeados diretamente aos usuários, em alguns casos para sobrecarregar os direitos alocados por meio de grupos.

## Etapas principais para conceder permissões{#key-steps-permissions}

Como administrador de produto, você pode conceder permissões aos usuários da organização. As permissões são concedidas por meio do console do cliente Adobe Admin Console e Campaign. Os usuários fazem logon no Adobe Campaign com a Adobe ID. Saiba como se conectar ao Adobe Campaign no [esta página](connect.md).

As principais etapas são:

* **Etapa 1**: defina os grupos de operadores e atribua a eles permissões no console do cliente do Campaign. [Saiba mais](manage-permissions.md#create-product-profile).
Observe que você também pode usar grupos de operadores integrados para começar. Esses grupos padrão e suas permissões são listados em [nesta seção](manage-permissions.md#ootb-productprofiles).
* **Etapa 2**: crie perfis de produto no Admin Console que correspondam a esses grupos. [Saiba mais](manage-permissions.md#create-product-profile).
Você pode usar perfis de produto integrados para começar. [Saiba mais](manage-permissions.md#ootb-productprofiles).
* **Etapa 3**: crie usuários no Admin Console e atribua-os a um perfil de produto. [Saiba mais](manage-permissions.md#add-users).
* **Etapa 4** (opcional): atribuir permissões em pastas. [Saiba mais](manage-permissions.md#ootb-productprofiles).

## Sobre o Admin Console{#gs-admin-console}

A Adobe Admin Console é um local central para gerenciar os direitos de Adobe em sua organização. Ele pode ser acessado somente por administradores de produtos.

Use o Admin Console para adicionar usuários, criar e atribuir perfis de produto (que são grupos de funções de operador).

Saiba como adicionar usuários no [esta página](manage-permissions.md#add-users).

## Sobre perfis de produto{#ootb-product-profiles}

Perfis de produto são grupos de produtos e serviços que podem ser atribuídos a usuários. No Adobe Experience Cloud, as permissões se baseiam no perfil de um produto, não no usuário. No entanto, você pode delegar direitos administrativos a usuários específicos.

No Admin Console, cada Adobe Experience Cloud **perfil do produto** for Campaign está associado a um **grupo de operadores** no console do cliente do Campaign.

Saiba como criar e atribuir perfis de produto no [esta página](manage-permissions.md#create-a-product-profile).

## Direitos nomeados da campanha{#named-rights}

Como membro de um perfil de produto (ou seja, grupo de operadores), um usuário tem direitos para executar operações, chamadas de &quot;Direitos nomeados&quot;, e tem acesso de leitura e/ou gravação aos dados. Um operador pode ser membro de vários grupos de operadores: direitos e permissões de acesso são aditivos.

Saiba mais sobre direitos nomeados no [nesta seção](manage-permissions.md#use-named-rights).
