---
title: Espaços de oferta de interação de campanha
description: Saiba como criar Espaços de oferta
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 48%

---

# Criar espaços de oferta{#creating-offer-spaces}

O conteúdo do catálogo de ofertas é configurado em espaços de oferta. Por padrão, o conteúdo pode incluir os seguintes campos: **[!UICONTROL Title]**, **[!UICONTROL Destination URL]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** e **[!UICONTROL Text content]**. A sequência de campos é configurada no espaço de oferta.

Como **administrador técnico**, você pode criar espaços de oferta no ambiente Design. É necessário ter acesso à subpasta de espaço de ofertas. Depois de criados, esses espaços de ofertas são duplicados automaticamente no ambiente Live durante a aprovação da oferta.

A renderização do HTML é criada por meio de uma função de renderização. A seqüência dos campos definidos na função de renderização deve ser idêntica à sequência configurada no conteúdo.

![](assets/offer_space_create_009.png)

Para criar um novo espaço de ofertas, siga as etapas abaixo:

1. Na lista de espaços de oferta, clique em **[!UICONTROL New]**.

   ![](assets/offer_space_create_001.png)

1. Selecione o canal que deseja usar e altere o rótulo do espaço de oferta.

   ![](assets/offer_space_create_002.png)

1. Marque a opção **[!UICONTROL Enable unitary mode]**

1. Vá para a janela **[!UICONTROL Content field]** e clique em **[!UICONTROL Add]**.

   ![](assets/offer_space_create_003.png)

1. Vá para o nó **[!UICONTROL Content]** e selecione os campos na seguinte ordem: **[!UICONTROL Title]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** e **[!UICONTROL Destination URL]**.

   ![](assets/offer_space_create_004.png)

1. Marque a opção **[!UICONTROL Required]** para tornar cada campo obrigatório.

   >[!NOTE]
   >
   >Essa opção é usada na pré-visualização e oferece espaços de oferta inválidos ao publicar se um dos campos obrigatórios não estiver presente na oferta. No entanto, se uma oferta já estiver disponível em um espaço de oferta, esses critérios não serão levados em consideração.

   ![](assets/offer_space_create_005.png)

1. Clique em **[!UICONTROL Edit functions]** para criar uma função de renderização.

   Essas funções são usadas para gerar representações de ofertas em um espaço de oferta. Há vários formatos possíveis: HTML ou texto.

   **Observação** - o formato XML está restrito às interações de entrada que não estão disponíveis nesta versão do produto. [Saiba mais](../start/v7-to-v8.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. Acesse a guia **[!UICONTROL HTML rendering]** e selecione **[!UICONTROL Overload the HTML rendering function]**.
1. Insira a função de renderização.

   ![](assets/offer_space_create_007.png)

## Status da apresentação de oferta {#offer-proposition-statuses}

O status da apresentação da oferta varia dependendo das interações com a população direcionada. O módulo de Interação do Campaign vem com um conjunto de valores que podem ser aplicados à apresentação de oferta durante todo o ciclo de vida. É necessário configurar a plataforma para que o status seja alterado quando a apresentação de oferta for criada e aceita.

>[!NOTE]
>
>A atualização de status é um processo **assíncrono**. Ele é realizado pelo workflow de rastreamento que é acionado a cada hora.

### Lista de status da oferta {#status-list}

Os status de oferta disponíveis são:

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

Esses valores não são aplicados por padrão: eles precisam ser configurados.

>[!NOTE]
>
>O status de uma apresentação de oferta será alterado automaticamente para &quot;Presented&quot; se a oferta estiver vinculada a uma entrega com o status &quot;Sent&quot;.

### Status da oferta quando a proposta é criada {#configuring-the-status-when-the-proposition-is-created}

Quando uma apresentação de oferta é **criada**, seu status é atualizado.

No ambiente **[!UICONTROL Design]**, para cada espaço de oferta, configure o status para ser aplicado quando uma proposta for criada, dependendo das informações que você deseja exibir nos relatórios de oferta.

Para fazer isso, siga as etapas abaixo:

1. Vá para a guia **[!UICONTROL Storage]** do espaço desejado.
1. Selecione o status a ser aplicado à proposta quando ela for criada.

   ![](assets/offer_update_status_001.png)

### Status da oferta quando a proposta for aceita {#configuring-the-status-when-the-proposition-is-accepted}

Depois que uma apresentação de oferta for **aceita**, use um dos valores fornecidos por padrão para configurar o novo status da apresentação. A atualização é aplicada quando um recipient clica em um link na oferta.

Para fazer isso, siga as etapas abaixo:

1. Vá para a guia **[!UICONTROL Storage]** do espaço desejado.
1. Selecione o status que deseja aplicar à proposta quando for aceita.

   ![](assets/offer_update_status_002.png)


**Interação de entrada**

A guia **[!UICONTROL Storage]** permite definir os status somente para propostas de ofertas **proposed** e **accepted**. Para interação de entrada, o status das apresentações de oferta deve ser especificado diretamente na URL para chamar o Mecanismo de oferta, em vez da interface. Dessa forma, é possível especificar qual status aplicar em outros casos, por exemplo, se uma apresentação de oferta for rejeitada.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

Por exemplo, a proposta (identificador **40004**) que corresponde à oferta **seguro residencial** exibida no site **Neobank** contém a seguinte URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

Assim que um visitante clica na oferta, e portanto na URL, o status **[!UICONTROL Accepted]** (valor **3**) é aplicado à proposta e o visitante é redirecionado para uma nova página do site **Neobank** para apresentar o contrato de seguro.

>[!NOTE]
>
>Se desejar especificar outro status na url (por exemplo, se uma apresentação de oferta for rejeitada), use o valor correspondente ao status desejado. Exemplo: **[!UICONTROL Rejected]** = &quot;5&quot;, **[!UICONTROL Presented]** = &quot;1&quot; e assim por diante.
>
>Os status e seus valores podem ser recuperados no esquema de dados **[!UICONTROL Offer propositions (nms)]**. Para obter mais informações, consulte [esta página](../dev/create-schema.md).

**Interação de saída**

Você pode aplicar automaticamente o status **[!UICONTROL Interested]** a uma apresentação de oferta quando a entrega contiver um link. Basta adicionar o valor **_urlType=&quot;11&quot;** ao link:

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## Visualização de oferta por espaço {#offer-preview-per-space}

Na guia **[!UICONTROL Preview]**, é possível exibir as ofertas para as quais o destinatário está qualificado por meio de um método escolhido. No exemplo abaixo, o destinatário está qualificado para três propostas de ofertas por e-mail.

![](assets/offer_space_overview_002.png)

Se um recipient não estiver qualificado para ofertas, isso será mostrado na visualização.

![](assets/offer_space_overview_001.png)


A visualização pode ignorar contextos quando eles são restritos a um espaço. Esse é o caso quando o schema de interação foi estendido para adicionar campos referenciados em um espaço usando um canal de entrada.

Para obter mais informações, consulte esta amostra na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/advanced-parameters/extension-example.html?lang=pt-BR){target="_blank"}.