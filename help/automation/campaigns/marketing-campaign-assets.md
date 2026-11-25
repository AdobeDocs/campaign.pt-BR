---
product: campaign
title: Ativos, documentos e delivery outlines da campanha de marketing
description: Saiba mais sobre documentos de campanha de marketing e descrições da entrega
feature: Campaigns
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
TQID: 'https://experienceleague.adobe.com/snshYvtbT3wG1N5-A4VHjl1bylxlXObi-97yVwuKAXk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 55%
---
# Gerenciar ativos e documentos {#manage-assets-documents}

Você pode associar vários documentos a uma campanha: relatórios, fotos, páginas da Web, diagramas etc. Esses documentos podem estar em qualquer formato.

Em uma campanha também é possível consultar outros itens, como cupons promocionais, ofertas especiais relacionadas a uma marca específica, uma loja etc. Quando esses elementos estão incluídos em uma descrição, é possível associá-los a uma entrega de correspondência direta. [Saiba mais](#associating-and-structuring-resources-linked-via-a-delivery-outline).


>[!CAUTION]
>
>Esse recurso foi projetado para ativos e documentos pequenos.

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## Adicionar documentos {#add-documents}

Os documentos podem ser associados no nível da campanha (documentos contextuais) ou no nível do programa (documentos gerais).

Para uma campanha, a guia **[!UICONTROL Documents]** contém:

* A lista de todos os documentos necessários para o conteúdo (modelo, imagens etc.) que podem ser baixados localmente por operadores do Adobe Campaign com direitos adequados,
* Documentos contendo informações para o roteador, se houver.

Os documentos são vinculados ao programa ou à campanha através da guia **[!UICONTROL Edit > Documents]**.

![Guia Editar da campanha, subguia Documentos: lista de documentos anexados com os botões Adicionar, Excluir e Detalhar.](assets/op_add_document.png)

Você também pode adicionar um documento a uma campanha no link dedicado no painel.

![Painel de campanha com o link Adicionar um documento e a caixa de diálogo Documento de marketing para carregar um arquivo.](assets/add_a_document_in_op.png)

Clique no ícone **[!UICONTROL Detail...]** para exibir o conteúdo de um arquivo e adicionar informações:

![Caixa de diálogo do documento aberta de Detalhes: rótulo, versão, natureza, link e descrição do arquivo carregado.](assets/add_document_details.png)

No painel, os documentos associados à campanha são agrupados na seção **[!UICONTROL Document(s)]**, como no exemplo a seguir:

![Painel de campanha com a seção Documento(s) destacando os documentos anexados à campanha.](assets/edit_documents.png)

Eles também podem ser editados e modificados nessa visualização.

## Usar delivery outlines {#delivery-outlines}

Um delivery outline é um conjunto estruturado de elementos (documentos, lojas, cupons promocionais etc.) criados pela empresa e para uma campanha específica. Ela é usada no contexto de entregas de correspondência direta.

Esses elementos são agrupados em descrições da entrega, e cada descrição da entrega será associada a uma entrega; ela será referenciada no arquivo de extração enviado para o **provedor de serviço** para ser anexada à entrega. Por exemplo, você pode criar um delivery outline que se refere a uma unidade e aos folhetos de marketing que ela usa.

Para uma campanha, delivery outlines permitem que você estruture elementos externos a serem associados ao delivery de acordo com determinados critérios: unidade relacionada, oferta promocional concedida, convite para um evento local etc.

>[!CAUTION]
>
>Delivery outlines são restritos a campanhas de correspondência direta.

### Criar um delivery outline {#create-an-outline}

Para criar um delivery outline, clique na guia **[!UICONTROL Edit > Documents]** da campanha relacionada e depois clique na subguia **[!UICONTROL Delivery outlines]**.

![Guia Editar da campanha, Documentos, subguia Delivery outlines com o link Adicionar um delivery outline.](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>Se não for possível ver essa guia, significa que esse recurso não está disponível para essa campanha ou que o delivery de correspondência direta não está ativado em sua instância. Consulte a [configuração do modelo de campanha](marketing-campaign-templates.md#campaign-templates) ou o contrato de licença.

Em seguida, clique em **[!UICONTROL Add a delivery outline]** e crie a hierarquia de outlines para a campanha:

1. Clique com o botão direito do mouse na raiz da árvore e selecione **[!UICONTROL New > Delivery outlines]**.
1. Clique com o botão direito do mouse no outline recém criado e selecione **[!UICONTROL New > Item]** ou **[!UICONTROL New > Personalization fields]**.

![Árvore de delivery outlines com o menu do botão direito do mouse: Novo > Item, Campos de personalização ou Oferta.](assets/del-outline-add-new-item.png)

Uma estrutura pode conter itens, campos de personalização e ofertas:

* Os itens podem ser documentos físicos, por exemplo, que são referenciados e descritos aqui e serão anexados à entrega.
* Os campos de personalização permitem que você crie elementos de personalização relacionados a remessas em vez de destinatários. Assim, é possível criar valores a serem utilizados em entregas para um público-alvo específico (oferta de boas-vindas, desconto etc.) Elas são criadas no Adobe Campaign e importadas para a estrutura por meio do link **[!UICONTROL Import personalization fields...]**.

  ![Selecione a caixa de diálogo de campos de personalização Pack, Gold e Premium, aberta em Importar campos de personalização.](assets/del-outline-perso-field.png)

  Eles também podem ser criados diretamente na estrutura clicando no ícone **[!UICONTROL Add]** à direita da zona de lista.

  ![Lista de campos de personalização em uma estrutura de entrega com valores inseridos e o ícone Adicionar à direita da lista.](assets/add-del-outline-button.png)


### Selecionar um outline {#select-an-outline}

Para cada entrega, você pode selecionar o outline para associar na seção reservada para o outline da extração, como no exemplo a seguir:

![Guia Correspondência Direta de uma entrega com a caixa de diálogo Selecionar uma estrutura de entrega listando Unidade B, Unidade C e Unidade A.](assets/select-delivery-outline.png)

A estrutura selecionada é então exibida na seção inferior da janela. Ele pode ser editado usando o ícone à direita do campo ou alterado usando a lista suspensa:

![Guia Correspondência Direta de uma entrega com o campo Estrutura de entrega destacado e mostrando a Unidade C.](assets/delivery-outline-selected.png)

A guia **[!UICONTROL Summary]** da entrega também exibe essas informações:

![Guia Resumo da Entrega com uma seta apontando para o valor da Estrutura de Entrega, Unidade C.](assets/delivery-outline-in-dashboard.png)

### Resultado da extração {#extraction-result}

No arquivo extraído e enviado ao provedor de serviços, o nome da estrutura e, quando apropriado, suas características (custo, descrição etc.) são adicionados ao conteúdo de acordo com as informações no modelo de exportação associado ao provedor de serviços.

No seguinte exemplo, o rótulo, custo estimado e descrição do outline associado à entrega serão adicionados no arquivo de extração.

![Dados para extrair a etapa do modelo de exportação com a coluna de saída Rótulo (Estrutura de Entrega/Entrega) realçada.](assets/campaign-export-template.png)

O modelo de exportação deve estar associado ao provedor de serviços selecionado para a entrega. Consulte [esta seção](providers-stocks-and-budgets.md#create-service-providers-and-their-cost-structures).
