---
title: Oferta de interação de campanha
description: Saiba como criar uma oferta
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 4dc2008d-681c-4a79-8fc8-c270c9224ab9
TQID: 'https://experienceleague.adobe.com/RcdMeKFZIeitseKyZb72sz6O1y7lhtwajxwAr5V9vLo'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 45%
---
# Criar uma oferta

Para criar uma oferta, siga as etapas abaixo:

1. Navegue até a guia **[!UICONTROL Campaigns]** e clique no link **[!UICONTROL Offers]**.

1. Clique no botão **[!UICONTROL Create]**.

1. Altere o rótulo e selecione a categoria à qual a oferta deve pertencer.

1. Clique em **[!UICONTROL Save]** para criar a oferta.

   A oferta está disponível na plataforma e seu conteúdo pode ser configurado.

## Configurações de qualificação

Agora você pode usar a guia **[!UICONTROL Eligibility]** para definir:

* O período de qualificação da oferta. [Saiba mais](#eligibility-period)
* Filtros no público-alvo da oferta. [Saiba mais](#filters-on-the-target)
* O peso da oferta. [Saiba mais](#offer-weight)

### Período de qualificação da oferta{#eligibility-period}

Na guia **[!UICONTROL Eligibility]** da oferta, defina o período de qualificação da oferta. Use as listas suspensas para selecionar uma data de início e término no calendário.

![Guia de qualificação com o calendário suspenso de datas de início e término do período de qualificação de oferta.](assets/offer_eligibility_create_002.png)

Fora desse período, a oferta não será selecionada. Se também tiver configurado datas de elegibilidade para a categoria de oferta, o período mais restritivo será aplicado.

### Adicionar filtros no target {#filters-on-the-target}

Na guia **[!UICONTROL Eligibility]** da oferta, aplique filtros ao destino da oferta.

Para fazer isso, clique no link **[!UICONTROL Edit query]** e selecione o filtro que deseja aplicar.

![Selecione o assistente de condições de filtragem de direcionamento, aberto a partir do link Editar consulta na guia Qualificação.](assets/offer_eligibility_create_003.png)

Se os filtros predefinidos já tiverem sido criados, é possível selecioná-los na lista de filtros de usuário. [Saiba mais](interaction-predefined-filters.md)

![Lista de filtros de usuário no assistente de direcionamento, com o filtro selecionado aplicado e uma visualização dos destinatários correspondentes.](assets/offer_eligibility_create_004.png)

### Definir o peso da oferta {#offer-weight}

Para permitir que o mecanismo decida entre várias ofertas que o target está qualificado, é necessário atribuir um ou mais pesos à oferta. Também é possível aplicar filtros ao target se necessário ou restringir o espaço de oferta ao qual o peso será aplicado. Uma oferta com um peso mais significativo será preferível sobre uma oferta com menos peso.

É possível configurar vários pesos para a mesma oferta, por exemplo, para distinguir subperíodos, alvos específicos ou até mesmo um espaço de oferta.

Por exemplo, uma oferta pode ter um peso de A para contatos com idade entre 18 e 25 e um peso de B para contatos acima desse intervalo. Se uma oferta estiver qualificada para o verão todo, ela também poderá ter um peso de A em julho e um peso de B em agosto.

>[!NOTE]
>
>O peso atribuído pode ser modificado temporariamente de acordo com os parâmetros da categoria à qual a oferta pertence. [Saiba mais](interaction-offer-catalog.md#creating-offer-categories)

Para criar um peso em uma oferta, aplique as seguintes etapas:

1. Na guia **[!UICONTROL Eligibility]**, clique em **[!UICONTROL Add]**.

   ![Guia Qualificação com o botão Adicionar, abrindo a caixa de diálogo Peso para criar um peso de oferta.](assets/offer_weight_create_001.png)

1. Altere o rótulo e atribua um peso. O valor padrão é 1.

   ![Caixa de diálogo de Peso com o campo Rótulo e o valor de Peso na seção Arbitragem.](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >Se nenhum peso for inserido (0), o target não será considerado qualificado para a oferta.

1. Se desejar que o peso seja aplicado por um determinado período, defina datas de elegibilidade.

   ![Caixa de diálogo de peso com data de Início e data de Término definidas na seção Datas de qualificação.](assets/offer_weight_create_002.png)

1. Se necessário, restrinja o peso a um espaço de oferta específico.

   ![Caixa de diálogo de peso com o menu suspenso Espaço de ofertas listando os espaços aos quais o peso pode ser restrito.](assets/offer_weight_create_003.png)

1. Aplique um filtro a um target.

   ![Caixa de diálogo de peso com o link Editar consulta em Filtros no destino realçada.](assets/offer_weight_create_004.png)

1. Clique em **[!UICONTROL OK]** para salvar o peso.

   ![Tabela de peso da guia de qualificação listando o novo peso Premium com suas datas e filtro.](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >Se um target for elegível para vários pesos de uma oferta selecionada, o mecanismo manterá o melhor (mais alto) peso. Ao chamar o Mecanismo de oferta, uma oferta é selecionada no máximo uma vez por contato.

### Resumo das regras de elegibilidade de oferta {#a-summary-of-offer-eligibility-rules}

Quando a configuração for concluída, um resumo das regras de elegibilidade estará disponível no painel de ofertas.

Para fazer isso, clique no link **[!UICONTROL Schedule and eligibility rules]**.

![Painel de ofertas com o link de regras de agendamento e qualificação realçado.](assets/offer_eligibility_create_005.png)

## Criar o conteúdo da oferta {#creating-the-offer-content}

Use a guia **[!UICONTROL Content]** para definir o conteúdo da oferta.

![Guia Conteúdo da oferta com os campos Título, URL de Destino, URL da Imagem e o editor de conteúdo do HTML.](assets/offer_content_create_001.png)

1. Defina os vários parâmetros do conteúdo da oferta.

   * **[!UICONTROL Title]**: especifique o título que quer que apareça em sua oferta. Aviso: não se refere ao rótulo da oferta, que é definido na guia **[!UICONTROL General]**.
   * **[!UICONTROL Destination URL]**: especifique a URL da sua oferta. Deve começar com &quot;http://&quot; ou &quot;https://&quot;.
   * **[!UICONTROL Image URL]**: especifique uma URL ou um caminho de acesso para a imagem da sua oferta.
   * **[!UICONTROL HTML content]** / **[!UICONTROL Text content]**: digite o corpo da oferta na guia desejada. Para gerar o rastreamento, o **[!UICONTROL HTML content]** deve ser composto de elementos HTML que podem ser colocados em um elemento de tipo `<div>`. Por exemplo, o resultado de um elemento `<table>` na página do HTML será o seguinte:

   ```xml
      <div> 
       <table>
        <tr>
         <th>Month</th>
         <th>Savings</th>   
        </tr>   
        <tr>    
         <td>January</td>
         <td>$100</td>   
        </tr> 
       </table> 
      </div>
   ```

   Saiba como definir a URL de aceitação no [Status da oferta quando a proposta for aceita](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted).

   ![A guia Conteúdo foi preenchida com um título, uma URL de destino e uma URL de imagem, além do link Definições de conteúdo.](assets/offer_content_create_002.png)

   Para localizar os campos obrigatórios conforme foram definidos durante a configuração do espaço de oferta, clique no link **[!UICONTROL Content definitions]** para exibir a lista. [Saiba mais](interaction-offer-spaces.md)

   ![Listagem da caixa de diálogo de definições de conteúdo, para cada espaço de oferta, os campos de conteúdo necessários.](assets/offer_content_create_003.png)

   Neste exemplo, a oferta deve incluir um título, uma imagem, conteúdo HTML e uma URL de destino.

## Pré-visualizar a oferta {#previewing-the-offer}

Após configurar o conteúdo da oferta, é possível pré-visualizar a oferta como ela aparecerá para o recipient.

Para isso:

1. Clique na guia **[!UICONTROL Preview]**.

   ![Guia Preview da oferta, listando as representações a serem visualizadas para cada espaço de oferta.](assets/offer_preview_create_001.png)

1. Selecione a representação da oferta que deseja visualizar.

   ![A guia Visualizar com a representação Email /clients foi expandida para mostrar o conteúdo da oferta renderizada.](assets/offer_preview_create_002.png)

1. Se tiver personalizado o conteúdo da oferta, selecione o target da oferta para visualizar a personalização.

<!--
## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

You can create hypotheses on your offer propositions. This lets you determine the impact of your offers on purchases carried out for the product concerned.

>[!NOTE]
>
>These hypotheses are carried out via Response Manager. Please check your license agreement.

Hypotheses carried out on an offer proposition are referenced in their **[!UICONTROL Measure]** tab.

Creating hypotheses is detailed in [this page](../../automation/response/about-response-manager.md).
-->

## Aprovar e ativar uma oferta{#approve-offers}

Agora você pode aprovar e ativar a oferta para disponibilizá-la no ambiente **Live**.

Para obter mais informações, consulte [Aprovação do conteúdo da oferta](approving-and-activating-an-offer.md#approving-offer-content).

## Gerenciar apresentação de ofertas{#offer-presentation}

O Campaign permite controlar o fluxo de apresentações de oferta usando regras de apresentação. Essas regras, que são específicas à Interação do Campaign, são **regras de tipologia**. Elas permitem excluir ofertas com base no histórico de apresentações já feitas a um destinatário. Eles são referenciados no ambiente.

Para obter mais informações, consulte [Gestão de apresentação de ofertas](managing-offer-presentation.md).

## Simulação de oferta

O módulo **Simulation** permite testar a distribuição de ofertas pertencentes a uma categoria ou um ambiente antes de enviar sua proposta para os destinatários.

A simulação leva em consideração os contextos e as regras de qualificação aplicadas anteriormente às ofertas e suas regras de apresentação. Isso permite testar e refinar várias versões da apresentação de oferta sem realmente usar uma oferta ou sobrecarregar ou não um destino, já que a simulação não tem impacto nos destinatários de destino.

Para obter mais informações sobre a Simulação de oferta, consulte [Sobre a simulação de ofertas](about-offers-simulation.md).
