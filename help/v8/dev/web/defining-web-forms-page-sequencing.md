---
product: campaign
title: Definir sequenciamento de páginas dos formulários web
description: Definir sequenciamento de páginas dos formulários web
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: c5b5c398-c13b-4ebe-88b2-8ff84741422e
TQID: 'https://experienceleague.adobe.com/G1sd0NfOozlAyvMZpi6R8IEbfr6ZHE2ibhnfttEd7J8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 75%
---
# Definir sequenciamento de páginas dos formulários web{#defining-web-forms-page-sequencing}



O formulário pode conter uma ou mais páginas. Ele é criado por meio de um diagrama que permite o sequenciamento de páginas e testes, execução de scripts e estágios de gravação de jump da página. O modo de construção do diagrama global é o mesmo que para um fluxo de trabalho do Campaign.

## Sobre a página anterior e a próxima página {#about-previous-page-and-next-page}

Para cada página, você pode excluir os botões **[!UICONTROL Next]** ou **[!UICONTROL Previous]**. Para fazer isso, selecione a página relevante e a opção **[!UICONTROL Disable next page]** ou **[!UICONTROL Disallow returning to the previous page]** .

![Propriedades da página, guia Geral, com a opção Desabilitar próxima página selecionada na seção Navegação.](assets/s_ncs_admin_survey_no_next_page.png)

Você pode substituir esses botões por links. Consulte [Inserção de conteúdo HTML](static-elements-in-a-web-form.md#inserting-html-content).

## Inserção de um jump {#inserting-a-jump}

O objeto **[!UICONTROL Jump]** dá acesso a outra página ou outro formulário quando o usuário clica em **[!UICONTROL Next]**.

O destino pode ser:

* Outra página do formulário. Para fazer isso, selecione **[!UICONTROL Internal activity]** e especifique a página desejada, conforme abaixo:

  ![Caixa de diálogo de salto com atividade Interna selecionada e a lista Atividade mostrando as páginas do formulário para as quais ir.](assets/s_ncs_admin_jump_param1.png)

* Outro formulário. Para fazer isso, clique na opção **[!UICONTROL Explicit]** e especifique o formulário de destino.

  ![Caixa de diálogo de salto com a opção Explícito selecionada e um formulário de destino escolhido no campo Aplicativo Web de destino.](assets/s_ncs_admin_jump_param2.png)

* O destino pode ser armazenado em uma variável. Nesse caso, selecione-o na lista suspensa, conforme mostrado abaixo:

  ![Caixa de diálogo de salto com a opção Armazenado em uma variável selecionada e a lista suspensa Variável local aberta.](assets/s_ncs_admin_jump_param3.png)

* A guia **[!UICONTROL Comment]** permite inserir informações que serão visíveis pelo operador quando clicarem no objeto no diagrama.

  ![Guia Comentário da caixa de diálogo Saltar; o texto aparece como uma dica de ferramenta no objeto Saltar no diagrama de formulário.](assets/s_ncs_admin_survey_jump_comment.png)

## Exemplo: acessar outro formulário de acordo com um parâmetro do URL {#example--accessing-another-form-according-to-a-parameter-of-the-url}

No exemplo a seguir, queremos configurar um formulário web que, quando aprovado, exibirá outro formulário designado por um parâmetro da URL. Para fazer isso, siga as etapas abaixo:

1. Insira um jump no final de um formulário: isto substitui a caixa **[!UICONTROL End]**.

   ![Diagrama de formulário com um objeto Jump inserido após Storage no final do formulário, substituindo a caixa End.](assets/s_ncs_admin_survey_jump_sample1.png)

1. Nas propriedades do formulário, adicione um parâmetro (**próximo**) armazenado em uma variável local (**próximo**). As variáveis locais são detalhadas em [Armazenamento de dados em uma variável local](web-forms-answers.md#storing-data-in-a-local-variable).

   ![Guia Parâmetros de propriedades de formulário adicionando o próximo parâmetro, armazenado na variável local próximo.](assets/s_ncs_admin_survey_jump_sample2.png)

1. Edite o objeto **[!UICONTROL Jump]**, selecione a opção **[!UICONTROL Stored in a variable]** e selecione a variável **next** na caixa suspensa.

   ![Caixa de diálogo de salto com a opção Armazenado em uma variável selecionada e a próxima variável escolhida na lista de variáveis Locais.](assets/s_ncs_admin_survey_jump_sample3.png)

1. A URL da entrega deve incluir o nome interno do formulário de destino, por exemplo:

   ```text
   https://[myserver]/webForm/APP62?&next=APP22
   ```

   Quando o usuário clica no botão **[!UICONTROL Approve]**, o formulário **APP22** é exibido.

## Inserção de um link para outra página do formulário {#inserting-a-link-to-another-page-of-the-form}

Você pode inserir links para outras páginas do formulário. Para fazer isso, adicione um elemento estático tipo **[!UICONTROL Link]** à página. Para obter mais informações, consulte [Inserção de um link](static-elements-in-a-web-form.md#inserting-a-link).

## Exibição de página condicional {#conditional-page-display}

### Exibir com base em respostas {#display-based-on-responses}

A caixa **[!UICONTROL Test]** permite determinar a condição do sequenciamento de páginas em um formulário. Ela permite definir várias linhas de filial, dependendo dos resultados do teste. Isso permite exibir páginas diferentes dependendo das respostas fornecidas pelos usuários.

Por exemplo, você pode exibir uma página diferente para clientes que já solicitaram online e outra para aqueles que fizeram mais de dez pedidos. Para fazer isso, na primeira página do formulário, insira um campo de entrada do tipo **[!UICONTROL Number]** para o usuário que indique quantos pedidos eles fizeram.

![Página do formulário Seus detalhes e pedidos com título, nome, campos de email e a Com que frequência você faz pedidos na pergunta da Web.](assets/s_ncs_admin_survey_test_ex0.png)

Você pode armazenar essas informações em um campo do banco de dados ou usar uma variável local.

>[!NOTE]
>
>Os modos de armazenamento são detalhados em [Campos de armazenamento de resposta](web-forms-answers.md#response-storage-fields).

No nosso exemplo, queremos usar uma variável:

![Campo Contagem de pedidos da página com seu armazenamento definido como a opção Variável e a variável Pedidos selecionados.](assets/s_ncs_admin_survey_test_ex1.png)

No diagrama do formulário, insira uma caixa de teste para definir as condições. Para cada condição, uma nova ramificação será adicionada na saída da caixa de teste.

![Testa a caixa de diálogo com as ramificações Pedidos +10 e Pedidos 1—>9 e a caixa de diálogo Editar ramificação definindo suas condições.](assets/s_ncs_admin_survey_test_ex2.png)

Selecione a opção **[!UICONTROL Activate the default branching]** para adicionar uma transição para casos em que nenhuma das condições é verdadeira. Essa opção é desnecessária se cada caso possível for coberto pelas condições definidas.

Em seguida, defina o sequenciamento de página quando uma ou outra das condições for verdadeira, por exemplo:

![Diagrama de formulário: os Pedidos? clientes potenciais de teste para páginas New, Standard ou Gold, que levam a Storage e End.](assets/s_ncs_admin_survey_test_ex3.png)

### Exibir com base em parâmetros {#display-based-on-parameters}

Você também pode personalizar o sequenciamento de página de acordo com os parâmetros de inicialização do formulário web ou de acordo com os valores armazenados no banco de dados. Consulte [Parâmetros da URL do formulário](defining-web-forms-properties.md#form-url-parameters).

## Adição de scripts {#adding-scripts}

O objeto **[!UICONTROL Script]** permite inserir um script JavaScript diretamente, por exemplo, para modificar o valor de um campo, recuperar dados do banco de dados ou chamar uma API do Adobe Campaign.

## Personalização da página final {#personalizing-the-end-page}

Você deve colocar uma página final no final do diagrama. A página final é exibida quando o usuário clica no botão **[!UICONTROL Approve]** no formulário web.

Para personalizar essa página, clique duas vezes em **[!UICONTROL End]** e insira o conteúdo da página no editor central.

![Encerre a caixa de diálogo com o título da página final e o editor de conteúdo, mostrando uma mensagem de agradecimento por concluir a pesquisa.](assets/s_ncs_admin_survey_end_page_edit.png)

* Você pode copiar e colar conteúdo HTML existente. Para fazer isso, clique em **[!UICONTROL Display source code]** e insira o código HTML.
* Você pode usar uma URL externa; para fazer isso, selecione a opção correspondente e digite a URL da página a ser exibida.
