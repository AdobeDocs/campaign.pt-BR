---
title: Adicionar campos de personalização
description: Saiba como inserir dados de personalização no conteúdo da mensagem
feature: Personalization
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 14a741dd-794e-4760-bfa3-bafbe993a3f7
source-git-commit: 25ee55d5327e0ba7f2192f7b462853269c8cbf46
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 41%

---

# Adicionar campos de personalização{#personalization-fields}

Use campos de personalização para fornecer conteúdo personalizado individualmente, com base nas regras definidas para cada recipient.

Um campo de personalização é uma única referência de campo de dados usada ao personalizar uma entrega para um destinatário específico. O valor de dados real é inserido durante a fase de análise da entrega.

![amostra de personalização da mensagem](assets/perso-name-sample.png)

## Sintaxe

Uma marca de personalização sempre usa a seguinte sintaxe: `<%=table.field%>`.

Por exemplo, para inserir o nome do recipient, armazenado na tabela de recipients, o campo de personalização usa a sintaxe `<%= recipient.lastName %>`.

>[!CAUTION]
>
>O conteúdo dos campos de personalização é limitado a 1024 caracteres.

## Inserir um campo de personalização {#insert-a-personalization-field}

Para inserir campos de personalização, clique no ícone suspenso que está acessível a partir de qualquer campo de cabeçalho, assunto ou corpo da mensagem.

![inserir um campo de personalização](assets/perso-field-insert.png)

Os campos de personalização são inseridos e prontos para serem interpretados pelo Adobe Campaign: durante a preparação da mensagem, os campos são substituídos por seu valor para um determinado recipient.

![campos de personalização em um email](assets/perso-fields-in-msg.png)

Essa substituição pode ser testada na guia **[!UICONTROL Preview]**.

<!--Learn more about message preview in [this page]().-->

## Caso de uso: personalizar assunto do email {#personalization-fields-uc}

No caso de uso abaixo, saiba como personalizar um assunto e um corpo de email com dados do recipient:

1. Criar um novo delivery ou abrir um delivery de email existente.
1. Navegue até o link **[!UICONTROL Subject]** para editar o assunto da mensagem.
1. Insira &quot;**Special offer for**&quot; e use o botão na barra de ferramentas para inserir um campo de personalização. Selecione **[!UICONTROL Recipients>Title]**.
1. Repita a operação para inserir o nome do destinatário. Insira espaços entre todos os campos de personalização.
1. Clique em **[!UICONTROL OK]** para validar.
1. Insira a personalização no corpo da mensagem. Para fazer isso, clique no conteúdo da mensagem e clique no botão de inserção de campo.
1. Selecione **[!UICONTROL Recipient>Other...]**.
1. Selecione o campo com as informações que serão exibidas e clique em **[!UICONTROL OK]**.
1. Clique na guia **[!UICONTROL Preview]** para exibir o resultado personalizado. Você deve selecionar um destinatário para exibir a mensagem dele.



## Tutorial em vídeo {#personalization-field-video}

Saiba como adicionar um campo de personalização à linha de assunto e ao conteúdo de um delivery de email no vídeo a seguir.

>[!VIDEO](https://video.tv.adobe.com/v/24925?quality=12)
