---
title: Conceder e restringir permissões em pastas do Campaign
description: Saiba como conceder ou restringir permissões em pastas
feature: Permissions
role: User, Admin
level: Beginner
source-git-commit: 857445d7d7d8080e479bdc596fb3162c2b4a2b6b
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 12%

---

# Gerenciar permissões da pasta{#manage-folder-permissions}

## Restringir acesso a uma pasta{#restrict-access-to-a-folder}

Use permissões em pastas para organizar e controlar o acesso aos dados do Campaign.

O gerenciamento de pastas é detalhado em [esta página](../audiences/folders-and-views.md).

Para editar permissões em uma pasta específica do Campaign, siga as etapas abaixo:

1. Clique com o botão direito do mouse na pasta e selecione **[!UICONTROL Properties...]**.
1. Navegue até o **[!UICONTROL Security]** para visualizar as autorizações nessa pasta.

   ![](assets/folder-permissions.png)

* Para **autorizar um grupo ou um operador**, clique no botão **[!UICONTROL Add]** e selecione o grupo ou operador para atribuir autorizações para essa pasta.
* Para **proibir um grupo ou operador**, clique em **[!UICONTROL Delete]** e selecione o grupo ou operador para remover a autorização para essa pasta.
* Para **selecione os direitos atribuídos a um grupo ou a um operador**, selecione o grupo ou operador, selecione os direitos de acesso que deseja conceder e desmarque os outros.

## Propagar permissões {#propagate-permissions}

Para propagar autorizações e direitos de acesso, selecione o **[!UICONTROL Propagate]** nas propriedades da pasta.

As autorizações definidas nessa janela serão aplicadas a todas as subpastas do nó atual. É sempre possível sobrecarregar essas autorizações para cada uma das subpastas.

>[!NOTE]
>
>Desmarcando o **[!UICONTROL Propagate]** A opção para uma pasta não a limpa para as subpastas: você deve limpá-la explicitamente para cada uma das subpastas.

## Conceder acesso a todos os operadores {#grant-access-to-all-operators}

No **[!UICONTROL Security]** selecione a guia **[!UICONTROL System folder]** para permitir acesso a todos os operadores, independentemente de suas permissões.

Se essa opção estiver desmarcada, você deverá adicionar explicitamente o operador (ou seu grupo) de volta à lista de autorizações para que ele tenha acesso.
