---
title: Conteúdo condicional
description: Saiba como criar conteúdo condicional
feature: Personalization
role: User
level: Beginner
exl-id: bcbf3101-d43c-4ed3-ab02-a9936ec55b71
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 52%

---

# Criação de conteúdo condicional{#conditional-content}

Ao configurar campos de conteúdo condicional, você pode criar personalização avançada. Quando uma determinada condição é atendida, blocos de texto e/ou imagens completas são substituídas.


## Usar condições em um email {#conditions-in-an-email}

No exemplo abaixo, saiba como criar uma mensagem, personalizada dinamicamente na cidade e interesses do recipient.

* Alterar a mensagem dependendo da cidade do recipient,
* Personalize o conteúdo da oferta de acordo com os interesses do recipient.

Para criar conteúdo condicional de acordo com o valor de um campo, siga as seguintes etapas:

1. Abra um delivery existente ou crie um novo delivery de email.
1. No editor de conteúdo de email, clique no ícone de personalização e selecione **[!UICONTROL Conditional content > If]**.

   ![Inserir uma condição](assets/condition-insert.png)

   Os elementos de personalização são inseridos no corpo da mensagem. Devem ser configurados agora.

1. Preencha os parâmetros da expressão **if**.

   * Selecione o primeiro elemento da expressão, **`<FIELD>`**, e clique no ícone de personalização para substituí-lo pelo campo de teste.
   * Substitua **`<VALUE>`** pelo valor do campo para o qual a condição será atendida. Esse valor deve estar entre aspas.
   * Especifique o conteúdo a ser inserido quando a condição for atendida. Pode ser um texto, uma imagem, um formulário, um link de hipertexto etc.

   ![Condição em um email](assets/condition-in-email.png)

1. Clique na guia **[!UICONTROL Preview]** para exibir o conteúdo da mensagem de acordo com o recipient do delivery. Selecione um recipient para o qual a condição seja verdadeira para verificar o conteúdo. Em seguida, selecione outro recipient para o qual ele é falso e verifique novamente.

Você pode adicionar outros casos e definir outro conteúdo de acordo com os valores de um ou mais campos. Para fazer isso, use **[!UICONTROL Conditional content > Else]** e **[!UICONTROL Conditional content > Else if]**. Essas expressões são configuradas da mesma maneira que a expressão **se**.

>[!CAUTION]
>
>Os caracteres **%> &lt;%** devem ser excluídos após adicionar as condições **Else** e **Else if**.


## Caso de uso: criar um email multilíngue {#creating-multilingual-email}

No exemplo abaixo, saiba como criar um email multilíngue. O conteúdo é exibido em um idioma ou em outro, dependendo da preferência de idioma do recipient.

1. Crie um email e selecione o público alvo. Neste exemplo, a condição para exibir uma versão ou outra será baseada no valor **Idioma** do perfil do destinatário. Estes valores estão definidos como **EN**, **FR**, **ES**.
1. No conteúdo HTML de email, clique na guia **[!UICONTROL Source]** e cole o seguinte código:

   ```
   <% if (language == "EN" ) { %>
   <DIV id=en-version>Hello <%= recipient.firstName %>,</DIV>
   <DIV>Discover your new offers!</DIV>
   <DIV><a href="https://www.adobe.com/products/en">www.adobe.com/products/en</A></FONT></DIV><%
    } %>
   <% if (language == "FR" ) { %>
   <DIV id=fr-version>Bonjour <%= recipient.firstName %>,</DIV>
   <DIV>Découvrez nos nouvelles offres !</DIV>
   <DIV><a href="https://www.adobe.com/products/fr">www.adobe.com/products/fr</A></DIV><%
    } %>
    <% if (language == "ES" ) { %>
   <DIV id=es-version><FONT face=Arial>
   <DIV>Olà <%= recipient.firstName %>,</DIV>
   <DIV>Descubra nuestros nuevas ofertas !</DIV>
   <DIV><a href="https://www.adobe.com/products/es">www.adobe.com/products/es</A></DIV>
   <% } %>
   ```

1. Teste o conteúdo do email na guia **[!UICONTROL Preview]** selecionando os destinatários com as diferentes preferências de idioma.

   >[!NOTE]
   >
   >Como nenhuma versão alternativa foi definida no conteúdo do email, filtre o público-alvo antes de enviar o email.

## Tutorial em vídeo {#conditionnal-content-video}

Saiba como adicionar conteúdo condicional a uma entrega no caso de um informativo multilíngue.

>[!VIDEO](https://video.tv.adobe.com/v/3446716?quality=12&captions=por_br)
