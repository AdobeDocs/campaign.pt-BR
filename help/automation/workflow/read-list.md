---
product: campaign
title: Lista de leitura
description: Saiba mais sobre a atividade de fluxo de trabalho de Lista de leitura
feature: Workflows, Targeting Activity
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 91c87f8f-bdd2-4ca1-94c2-ec9e7affc1a0
TQID: 'https://experienceleague.adobe.com/J-3G1xfCNkBVkmO0WqjHtstOGq5LE8ymd2oa8f-VSSE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 78%
---
# Lista de leitura{#read-list}

Os dados processados em um fluxo de trabalho podem vir de listas em que os dados foram preparados ou estruturados antecipadamente (após uma segmentação ou carregamento de arquivo anterior).

A atividade **[!UICONTROL Read list]** permite copiar os dados de uma lista na tabela de trabalho do fluxo de trabalho, como dados de uma consulta. Ele é então acessível através do fluxo de trabalho.

A lista a ser processada pode ser especificada explicitamente, calculada por um script ou localizada dinamicamente de acordo com as opções selecionadas e parâmetros definidos em uma atividade **[!UICONTROL Read list]**.

![Ler atividade de lista com Especificado explicitamente selecionado, uma lista escolhida e o link Editar consulta na filtragem Source](assets/list_edit_select_option_01.png)

Se a lista não for especificada explicitamente, você deve fornecer uma lista para ser usada como modelo para descobrir sua estrutura.

![Atividade de lista de leitura com o Nome calculado por um script selecionado e o menu suspenso Lista aberto](assets/s_advuser_list_template_select.png)

Após configurar a seleção da lista, é possível adicionar um filtro utilizando a opção **[!UICONTROL Edit query]** para manter uma parte da população para o próximo fluxo de trabalho.

![A atividade da lista de leitura com um filtro Editar consulta em Preço não está vazia e foi aplicada à lista selecionada](assets/wf_readlist_1.png)

>[!CAUTION]
>
>Para poder criar um filtro em uma atividade de lista de leitura, a lista relevante deve ser um tipo de &quot;arquivo&quot;.

As listas podem ser criadas diretamente no Adobe Campaign através do link **[!UICONTROL Profiles and Targets > Lists]** da página inicial. Também é possível criá-los em um fluxo de trabalho usando a atividade **[!UICONTROL List update]**.

**Exemplo: exclusão de uma lista de endereços enviados**

O exemplo a seguir permite usar uma lista de endereços de email para excluir do target de entrega de email.

![Fluxo de trabalho com uma lista de leitura e uma consulta de arquivos Novos contatos unidos em uma Exclusão, depois em uma entrega e em uma Espera por 3 dias](assets/s_advuser_list_read_sample_1.png)

Os perfis contidos na pasta **Novos Contatos** devem ser target de uma ação de entrega. Os endereços de email a serem excluídos do target são armazenados em uma lista externa. Em nosso exemplo, somente as informações sobre endereços de email são necessárias para exclusão.

1. O query de seleção da pasta **Novos Contatos** permite carregar os endereços de email dos perfis selecionados para habilitar o alinhamento com as informações na lista.

   ![Atividade de consulta de novos contatos com o campo Email adicionado em Informações complementares](assets/s_advuser_list_read_sample_0.png)

1. Aqui, a lista é armazenada na pasta **Listas** e seu rótulo é calculado.

   ![Ler atividade de lista com a pasta Listas e um rótulo calculado para o arquivo de lista negra](assets/s_advuser_list_read_sample_2.png)

1. Para excluir os endereços de email da lista externa do target principal, você deve configurar a atividade de exclusão e especificar que a pasta **New Contacts** contém os dados a serem mantidos. Os dados conjuntos entre esse conjunto e qualquer outro conjunto de entrada da atividade de exclusão serão excluídos do target.

   ![Atividade de exclusão com o arquivo Novos contatos definido como Conjunto principal e a tabela de regras de exclusão](assets/s_advuser_list_read_sample_3.png)

   As regras de exclusão são configuradas na seção central da ferramenta de edição. Clique em **[!UICONTROL Add]** para definir o tipo de exclusão a ser aplicada.

   Você pode definir várias exclusões dependendo do número de transições de entrada da atividade.

1. No campo **[!UICONTROL Exclusion set]**, selecione a atividade **[!UICONTROL Read list]**: os dados desta atividade devem ser excluídos do conjunto principal.

   No nosso exemplo, temos uma exclusão em junções: os dados contidos na lista serão reconciliados com os dados do conjunto principal através do campo com o endereço de email. Para configurar a associação, selecione **[!UICONTROL Joins]** no campo **[!UICONTROL Change dimension]**.

   ![Definição de exceção com Lista de leitura como conjunto de exclusão e a opção Joins na dimensão Change](assets/s_advuser_list_read_sample_4.png)

1. Em seguida, selecione o campo correspondente ao endereço de email nos dois conjuntos (Origem e Destino). As colunas serão vinculadas e os destinatários cujo endereço de email estiver na lista de endereços importados serão excluídos do target.
