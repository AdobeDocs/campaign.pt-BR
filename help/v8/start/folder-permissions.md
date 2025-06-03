---
title: Conceder e restringir permissões nas pastas do Campaign
description: Saiba como conceder ou restringir permissões em pastas
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 28%

---

# Gerenciar permissões da pasta{#manage-folder-permissions}

## Restringir o acesso a uma pasta{#restrict-access-to-a-folder}

Use permissões em pastas para organizar e controlar o acesso aos dados do Campaign.

O gerenciamento de pastas está detalhado em [esta página](../audiences/folders-and-views.md).

Para editar permissões em uma pasta específica do Campaign, siga as etapas abaixo:

1. Clique com o botão direito do mouse na pasta e selecione **[!UICONTROL Properties...]**.
1. Navegue até a guia **[!UICONTROL Security]** para visualizar as autorizações nessa pasta.

   ![](assets/folder-permissions.png)

* Para **autorizar um grupo ou operador**, clique no botão **[!UICONTROL Add]** e selecione o grupo ou operador para atribuir autorizações para esta pasta.
* Para **proibir um grupo ou operador**, clique em **[!UICONTROL Delete]** e selecione o grupo ou operador para remover a autorização para esta pasta.
* Para **selecionar os direitos atribuídos a um grupo ou a um operador**, selecione o grupo ou operador, selecione os direitos de acesso que deseja conceder e desmarque os outros.

>[!NOTE]
>
>Você não deve ser capaz de criar um objeto para o qual não tem pelo menos uma pasta com direitos de gravação.
>
>Não é necessário ser administrador para criar fragmentos, mas é preciso ter direitos de gravação em pelo menos uma pasta de &quot;Fragmento visual de conteúdo&quot;. Caso contrário, não será possível criar um fragmento visual.

## Propagar permissões {#propagate-permissions}

Para propagar autorizações e direitos de acesso, selecione a opção **[!UICONTROL Propagate]** nas propriedades da pasta.

As autorizações definidas nessa janela serão aplicadas a todas as subpastas do nó atual. Você sempre pode sobrecarregar essas autorizações para cada uma das subpastas.

>[!NOTE]
>
>Desmarcar a opção **[!UICONTROL Propagate]** para uma pasta não a limpa para as subpastas: você deve limpá-la explicitamente para cada uma das subpastas.

## Conceder acesso a todos os operadores {#grant-access-to-all-operators}

Na guia **[!UICONTROL Security]**, selecione **[!UICONTROL System folder]** para permitir acesso a todos os operadores, independentemente de suas permissões.

Se essa opção for desmarcada, você deverá adicionar explicitamente o operador (ou seu grupo) de volta à lista de autorizações para que ele tenha acesso.
