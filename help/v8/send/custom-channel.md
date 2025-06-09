---
title: Introdução a canais externos personalizados
description: Saiba como criar e enviar entregas de canal externo personalizadas com o Adobe Campaign Web
role: User
level: Beginner, Intermediate
exl-id: d2d92de6-3974-41c5-a0fd-09bbf6cf0020
source-git-commit: f94074d954137c4db39b2ef9f85141b79fe3356b
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---

# Introdução a canais externos personalizados {#gs-custom-channel}

O Adobe Campaign permite criar canais externos personalizados integrados com terceiros. Em seguida, você pode orquestrar e executar deliveries com base nesses canais.

A criação e o envio do delivery podem ser executados no Console do cliente e na interface do usuário da Web. No entanto, o canal externo personalizado só é executado no Console do cliente.

Para saber como criar e enviar uma entrega com base em um canal externo personalizado, consulte esta [página](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html).

Estas são as etapas para criar um novo canal personalizado externo no Console do cliente:

1. Configurar o esquema, [leia mais](#configure-schema)
1. Crie uma nova conta externa, [leia mais](#create-ext-account)
1. Criar um novo modelo de entrega, [leia mais](#create-template)

## Configurar o esquema{#configure-schema}

Primeiro, é necessário configurar o schema para adicionar o novo canal à lista de canais disponíveis.

1. No Campaign Explorer, selecione **Administração** > **Configuração** > **Esquemas de dados**.

1. Crie uma extensão de esquema para estender a enumeração messageType com o novo canal.

   Por exemplo:

   ```
   <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
   <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
          value="122"/>
   </enumeration>
   ```

   ![](assets/cus-schema.png){zoomable="yes"}

## Criar uma nova conta externa{#create-ext-account}

Em seguida, é necessário criar uma nova conta externa de roteamento.

1. No Campaign Explorer, selecione **Administração** > **Plataforma** > **Contas externas**.

1. Crie uma nova conta externa.

1. Selecione o canal e altere o modo de entrega para **Externo**.

   ![](assets/cus-ext-account.png){zoomable="yes"}

## Criar um novo modelo de entrega{#create-template}

Agora, vamos criar o novo modelo associado ao novo canal.

1. No Campaign Explorer, selecione **Recursos** > **Modelos** > **Modelos de entrega**.

1. Crie um novo modelo.

1. Clique em **Propriedades** e selecione a pasta correta e o roteamento.

   ![](assets/cus-template.png){zoomable="yes"}

O novo canal agora está disponível. Você pode criar e executar deliveries com base neste canal.
