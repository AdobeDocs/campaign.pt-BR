---
title: SMS em uma infraestrutura de mid-sourcing
description: Saiba como configurar uma entrega de SMS em uma infraestrutura de mid-sourcing
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: b5eb9eaa-0ca8-478c-9ed5-e5006e9b5609
TQID: 'https://experienceleague.adobe.com/JMj3tFG6i-bWXlEGyvFzlNpAj4fZoqZC4mdej5N3Qcw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 11%
---
# SMS em uma infraestrutura de mid-sourcing {#sms-mid}

O envio de deliveries de SMS com uma infraestrutura de mid-sourcing requer:

1. Um Operador SMS no Mid-server. [Saiba como criá-lo aqui](#sms-operator-mid)
1. Uma conta externa de SMS no servidor de marketing que usará o operador criado anteriormente. [Saiba como criá-lo aqui](#sms-external-account)
1. Uma conta externa SMPP no servidor Mid, especificando o modo de Entrega Channel e Mid-sourcing. [Saiba como criá-lo aqui](#smpp-external-account-mid)
1. Um modelo de entrega que faça referência à conta externa para simplificar o processo de envio. [Saiba como criá-lo aqui](#sms-delivery-template)

## Criar o operador SMS no Mid-server {#sms-operator-mid}

Primeiro, é necessário criar um operador SMS no Mid-server, que será usado pela conta externa de SMS no servidor de marketing.

Para criar sua operadora de SMS, siga as etapas abaixo:

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Access management]** > **[!UICONTROL Operators]**, clique no **[!UICONTROL New]** e preencha o formulário na nova janela aberta.

   * **[!UICONTROL Name (login)]** e **[!UICONTROL Label]** são obrigatórios.
   * A senha não é obrigatória, mas é altamente recomendada para segurança.

   Observe que o Nome (logon) deverá ser usado posteriormente para nomear sua conta externa SMPP no servidor intermediário.

   ![Novo formulário de operador SMS no mid-server com Nome (logon), Senha e Rótulo e o botão Adicionar para direitos](assets/smsoperator_mid.png){zoomable="yes"}

1. Na parte **[!UICONTROL Groups and named rights]**, clique no botão **[!UICONTROL Add]**.
Na nova janela aberta, escolha **[!UICONTROL Named rights]** na lista **[!UICONTROL Folder]** e selecione **[!UICONTROL ADMINISTRATION]** na lista direita.

1. Clique no botão **[!UICONTROL Ok]**.

   ![Caixa de diálogo Adicionar grupos ou direitos nomeados com o direito nomeado ADMINISTRATION selecionado](assets/smsoperator_rights.png){zoomable="yes"}

1. Clique no botão **[!UICONTROL Save]** para finalizar a criação do operador SMS.

   ![Formulário do operador SMS com o direito ADMINISTRATION adicionado e o botão Salvar realçado](assets/smsoperator_save.png){zoomable="yes"}

Você pode vê-lo na lista de operadores agora.

![Lista de operadores mostrando o novo operador Mid sms (smsOperator)](assets/smsoperator_list.png){zoomable="yes"}

## Criar uma conta externa de SMS no servidor de marketing {#sms-external-account}

Em uma infraestrutura intermediária, é necessário criar uma conta externa de SMS no servidor de Marketing conforme abaixo

>[!IMPORTANT]
>
>Usar a mesma conta e senha para várias contas externas de SMS pode resultar em conflitos e sobreposição entre as contas. Saiba mais na [página de solução de problemas de SMS](smpp-connection.md#sms-troubleshooting).

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**, clique no ícone **[!UICONTROL New]**

   ![Lista de Contas Externas em Administração > Plataforma com o ícone Novo realçado](assets/sms_extaccount.png){zoomable="yes"}

1. Configure o **[!UICONTROL Label]** e o **[!UICONTROL Internal name]** da sua conta externa. Defina o tipo de conta como **[!UICONTROL Routing]**, marque a caixa **[!UICONTROL Enabled]**, selecione **[!UICONTROL Mobile (SMS)]** para o canal e **[!UICONTROL Mid-sourcing]** para o modo de entrega.

   ![Guia Geral da conta externa: Tipo de roteamento, Habilitado, canal Móvel (SMS) e modo de entrega Mid-sourcing](assets/mid_smsextaccount.png){zoomable="yes"}

1. Na guia **[!UICONTROL Mid-sourcing]**, preencha o formulário com a URL do servidor mid-sourcing e o operador de SMS criado anteriormente no servidor mid-sourcing.

   Confirme a conexão clicando no botão **[!UICONTROL Test the connection]**.

   ![Guia Mid-sourcing com URL do servidor, conta de operador SMS, senha e botão Testar conexão](assets/midtab_smsextaccount.png){zoomable="yes"}

1. Clique em **[!UICONTROL Save]**.

## Criar uma conta externa de SMPP no mid-server {#smpp-external-account-mid}

>[!IMPORTANT]
>
>Usar a mesma conta e senha para várias contas externas de SMS pode resultar em conflitos e sobreposição entre as contas. Consulte a [Página de solução de problemas de SMS](smpp-connection.md#sms-troubleshooting).

O objetivo agora é estabelecer sua conta externa SMPP no Mid-server.

Para fazer isso, siga as etapas abaixo:

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]** do Servidor intermediário, clique no ícone **[!UICONTROL New]**

1. Configure o **[!UICONTROL Label]** e o **[!UICONTROL Internal name]** da sua conta externa.

   >[!WARNING]
   >
   >Ao atribuir um nome Interno, siga a convenção de nomenclatura especificada: `SMS Operator Name_Internal Name of the Marketing SMS external account`.
   >

   Defina o tipo de conta como **[!UICONTROL Routing]**, marque a caixa **[!UICONTROL Enabled]**, selecione **[!UICONTROL Mobile (SMS)]** para o canal e **[!UICONTROL Bulk delivery]** para o modo de entrega.
   ![Guia Geral da conta externa de mid-server: Tipo de roteamento, Habilitado, Canal móvel (SMS) e Modo de entrega em massa](assets/mid_extaccount.png){zoomable="yes"}

1. Na guia **[!UICONTROL Mobile]**, mantenha **[!UICONTROL Extended generic SMPP]** na lista suspensa **[!UICONTROL Connector]**.

   A caixa **[!UICONTROL Send messages through a dedicated process]** está marcada por padrão.

   ![Guia Mobile com o conector SMPP genérico estendido e Enviar mensagens por meio de um processo dedicado marcado](assets/sms_extaccount_connector.png){zoomable="yes"}

   Para configurar a conexão, você precisa preencher as guias deste formulário. Para obter detalhes, [saiba mais sobre a conta externa SMPP](smpp-external-account.md#smpp-connection-settings).

## Configurar o template do delivery {#sms-delivery-template}

Para facilitar a criação do delivery de SMS, crie um template do delivery de SMS no qual todas as configurações sejam referenciadas.

Em **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** no servidor de marketing, clique com o botão direito do mouse no modelo de entrega para dispositivos móveis existente e escolha **[!UICONTROL Duplicate]**.

![Lista de modelos de entrega com Duplicata selecionada no menu de contexto para o modelo de SMS (Mobile)](assets/sms_template_duplicate.png){zoomable="yes"}

Altere o **[!UICONTROL Label]** e o **[!UICONTROL Internal name]** do seu modelo para reconhecê-lo facilmente, e clique no botão **[!UICONTROL Properties]**.

![Modelo de entrega duplicado com os campos Rótulo e Nome interno, e o botão Propriedades realçado](assets/sms_template_name.png){zoomable="yes"}

Na guia **[!UICONTROL General]**, em **[!UICONTROL Routing]**, selecione a conta externa SMPP.

![Guia Geral de propriedades de entrega com o campo Roteamento definido para a conta externa SMPP](assets/mid_template.png){zoomable="yes"}

Na guia **[!UICONTROL SMS]**, é possível adicionar parâmetros opcionais ao modelo.

![Guia SMS de propriedades de entrega com parâmetros gerais e parâmetros SMPP opcionais (TLV)](assets/sms_template_properties.png){zoomable="yes"}

[Saiba mais sobre esta configuração da guia SMS](sms-delivery-settings.md).
