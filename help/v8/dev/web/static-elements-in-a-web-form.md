---
product: campaign
title: Elementos estáticos em um formulário web
description: Elementos estáticos em um formulário web
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 364d90af-4b18-4104-8b6a-be80cfde3b0b
TQID: 'https://experienceleague.adobe.com/X32IQAVVq68tRjHIXaHN99S-EbL3vqP0j7gTL0fvmNA'
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
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1364'
ht-degree: 76%
---
# Elementos estáticos em um formulário web{#static-elements-in-a-web-form}



É possível incluir elementos com os quais o usuário não tem nenhuma interação nas páginas do formulário; trata-se de elementos estáticos, como imagens, conteúdo HTML, uma barra horizontal ou um link de hipertexto. Esses elementos são criados por meio do primeiro botão na barra de ferramentas, clicando em **[!UICONTROL Static elements]**.

![Menu da barra de ferramentas da página para elementos estáticos: Valor, Link, HTML, Imagem, Barra horizontal, Marca de rastreamento e Script](assets/s_ncs_admin_survey_add_static_element.png)

Os seguintes tipos de campo estão disponíveis:

* Valor baseado nas respostas fornecidas anteriormente (no contexto do formulário) ou no banco de dados.
* Link de hipertexto, HTML, barra horizontal. Consulte [Inserção de conteúdo HTML](#inserting-html-content).
* Imagem salva na biblioteca de recursos ou em um servidor acessível por usuários. Consulte [Inserção de imagens](#inserting-images).
* Script executado no lado do cliente e/ou servidor. Ele deve ser escrito em JavaScript e ser compatível com a maioria dos navegadores para garantir a execução correta no lado do cliente.

  >[!NOTE]
  >
  >No lado do servidor, o script pode usar as funções definidas na [documentação do Campaign JSAPI](https://experienceleague.adobe.com/pt-br/tools/campaign-api).

## Inserir conteúdo HTML {#inserting-html-content}

É possível incluir conteúdo HTML em uma página de formulário: links de hipertexto, imagens, parágrafos formatados, vídeos, etc.

O editor HTML permite digitar o conteúdo a ser inserido na página de formulário. Para abrir o editor, clique em **[!UICONTROL Static elements]** > **[!UICONTROL HTML]** .

É possível inserir e formatar seu conteúdo diretamente ou exibir a janela do código-fonte para colar em algum conteúdo externo. Para alternar para o modo &quot;código-fonte&quot;, clique no primeiro ícone na barra de ferramentas:

![Editor HTML de uma página com o botão Exibir código-fonte realçado e a fonte do HTML exibida](assets/s_ncs_admin_survey_html_editor.png)

Para inserir um campo de banco de dados, use o botão de personalização.

![Menu de personalização do editor do HTML oferecendo campos de Destinatários como Nome, Sobrenome e Chave primária](assets/webapp_perso_button_in_html.png)

>[!NOTE]
>
>As strings inseridas no editor HTML só serão traduzidas se forem definidas na subguia **[!UICONTROL Texts]**. Caso contrário, elas não serão coletadas. Para obter mais informações, consulte [Tradução de um formulário web](translating-a-web-form.md).

### Inserir um link {#inserting-a-link}

Preencha os campos na janela de edição, como mostrado no seguinte exemplo:

Para adicionar um link de hipertexto, vá para **[!UICONTROL Static elements]** > **[!UICONTROL Link]**.

![Propriedades do link: Rótulo, Ação definida como URL, URL mailto, Janela, Dica de Ferramenta e configurações de exibição](assets/s_ncs_admin_survey_add_link.png)

* O **[!UICONTROL Label]** é o conteúdo do link de hipertexto como ele será exibido na página do formulário.
* O **[!UICONTROL URL]** é o endereço desejado, por exemplo: [https://www.adobe.com](https://www.adobe.com) no caso de um site ou [info@adobe.com](mailto:info@adobe.com) para enviar uma mensagem.
* O campo **[!UICONTROL Window]** permite selecionar o modo de exibição do link no caso de um site. Você pode optar por abrir o link em uma nova janela, a janela atual ou outra janela.
* Você pode adicionar uma ToolTip, como mostrado abaixo:

  ![Renderizado Enviar um link de mensagem com a dica de ferramenta Clique aqui para nos enviar um email](assets/s_ncs_admin_survey_send_an_email.png)

* Você pode escolher exibir o link como um botão ou uma imagem. Para fazer isso, selecione o tipo de exibição no campo **[!UICONTROL Type]**.

### Tipos de links {#types-of-links}

Por padrão, os links são associados a uma ação do tipo URL para que um endereço de destino de link possa ser inserido no campo URL.

![Vincular propriedades com uma URL mailto, o campo Janela definido como Criar uma nova janela e uma ToolTip](assets/s_ncs_admin_survey_link_url.png)

Você pode definir outras ações para o link, para que o usuário possa clicar no link e fazer o seguinte:

* Atualizar a página

  Para fazer isso, selecione a opção **[!UICONTROL Refresh page]** na caixa suspensa do campo **[!UICONTROL Action]**.

  ![Lista suspensa Ação de link Nenhum, URL, Exibir, Atualizar página, Próxima página e Habilitar uma transição, com a opção Atualizar página escolhida](assets/s_ncs_admin_survey_link_refresh.png)

* Exibir a página seguinte/anterior

  Para fazer isso, selecione a opção **[!UICONTROL Next page]** ou **[!UICONTROL Previous page]** na caixa suspensa do campo **[!UICONTROL Action]**.

  ![Lista suspensa Ação de link com Próxima página selecionada para um link chamado Próxima página](assets/s_ncs_admin_survey_link_next.png)

  Você pode ocultar os botões **[!UICONTROL Next]** e/ou **[!UICONTROL Back]** se eles forem substituídos por um link. Consulte esta [página](defining-web-forms-page-sequencing.md).

  O link substituirá o botão **[!UICONTROL Next]** usado por padrão.

  ![Página de formulário com campos de Nome, Sobrenome e Senha e um link Próximo mostrando uma dica de ferramenta de validação](assets/s_ncs_admin_survey_link_next_ex.png)

* Exibir outra página

  A opção **[!UICONTROL Enable a transition]** permite exibir uma página específica associada à transição de saída selecionada no campo **[!UICONTROL Transition]**.

  ![Link com Ação definido para Habilitar uma transição e a lista de Transição oferecendo Próximo e Enviado para um amigo](assets/s_ncs_admin_survey_link_viral.png)

  Por padrão, uma página tem apenas uma transição de saída. Para criar novas transições, selecione a página e clique no botão **[!UICONTROL Add]** na seção **[!UICONTROL Output transitions]**, conforme mostrado abaixo:

  ![Propriedades da página de boas-vindas com transições de saída habilitadas, listando Próximo e Viral (Enviado para um amigo) e o botão Adicionar](assets/s_ncs_admin_survey_add_transition.png)

  No diagrama, essa adição terá esta aparência:

  ![Fluxo de formulários web no qual Seus contratos levam à Sua conta, ou via Enviado a um amigo para o Patrocinador, depois Armazenamento e Fim](assets/s_ncs_admin_survey_add_transition_graph.png)

  >[!NOTE]
  >
  >Para obter mais informações sobre a sequência de páginas em um formulário web, consulte [Definição de sequenciamento de páginas de formulários web](defining-web-forms-page-sequencing.md).

### Personalizar conteúdo HTML {#personalizing-html-content}

Você pode personalizar o conteúdo HTML de uma página de formulário com dados registrados em uma página anterior. Por exemplo, você pode criar um formulário web de seguro de carro cuja primeira página permite fornecer informações de contato e a marca do carro.

![Página de formulário 1 de 2 solicitando título, nome, email, identificador e marca de carro, com um botão Avançar](assets/s_ncs_admin_survey_tag_ctx_1.png)

Use campos de personalização para reinjetar o nome de usuário e marca selecionada na próxima página. A sintaxe a ser usada depende do modo de armazenamento de informações. Para obter mais informações, consulte [Uso das informações coletadas](web-forms-answers.md#using-collected-information).

>[!NOTE]
>
>Por motivos de segurança, o valor inserido na fórmula **`<%=`** é substituído por caracteres de escape.

No nosso exemplo, o nome e o sobrenome do destinatário são armazenados em um campo do banco de dados, enquanto a marca do carro é armazenada em uma variável. A sintaxe da mensagem personalizada na página 2 será a seguinte:

![HTML de mensagem personalizada com nome, sobrenome e uma variável de marca de carro do destinatário inserida usando a sintaxe de marca](assets/webapp_perso_vars_include.png)

```xml
<P>Welcome <%= ctx.recipient.@firstName %> <%= ctx.recipient.@lastName %>,</P>
<P>To start your customized study, please select your car <%=ctx.vars.marque%> and its year of purchase.</P>
```

Isso produz o seguinte resultado:

![Página de formulário 2 de 2 saudando o destinatário por nome e marca, com as listas Selecionar modelo e Ano dos carros](assets/s_ncs_admin_survey_tag_ctx_2.png)

### Usar variáveis de texto {#using-text-variables}

A guia **[!UICONTROL Text]** permite criar campos variáveis que podem ser usados no HTML entre os caracteres &lt;%= and %> com a seguinte sintaxe: **$(IDENTIFIER)**.

Use esse método para localizar facilmente suas strings. Consulte [Tradução de um formulário web](translating-a-web-form.md)

Por exemplo, você pode criar um campo **Contato** que permitirá exibir a string &quot;Data do último contato:&quot; para o conteúdo HTML. Para fazer isso, siga as etapas abaixo:

1. Clique na guia **[!UICONTROL Text]** do texto HTML.
1. Clique no ícone **[!UICONTROL Add]**.
1. Na coluna **[!UICONTROL Identifier]**, digite o nome da variável
1. Na coluna **[!UICONTROL Text]**, digite o valor padrão.

   ![Identificadores de lista da guia Textos do elemento HTML Country e DateFormat com seus valores de texto](assets/s_ncs_admin_survey_html_text.png)

1. No conteúdo HTML, insira essa variável de texto pela sintaxe **&lt;%= $(Contact) %>** .

   ![Editor de conteúdo do HTML com o identificador de texto Contato inserido ao lado do campo de data da última modificação](assets/s_ncs_admin_survey_html_content.png)

   >[!CAUTION]
   >
   >Se você inserir esses caracteres no editor de HTML, os campos **&lt;** e **>** serão substituídos por seus caracteres de escape. Nesse caso, você precisa corrigir o código-fonte clicando no ícone **[!UICONTROL Display source code]** do editor de texto HTML.

1. Abra o rótulo **[!UICONTROL Preview]** do formulário para exibir o valor inserido no HTML:

   ![Página de formulário 2 de 2 exibindo a Data do último contato com o identificador de texto traduzido](assets/s_ncs_admin_survey_html_content_preview.png)

Esse modo operacional permite que você defina o texto de formulários web e gerencie traduções usando a ferramenta de tradução integrada. Para obter mais informações, consulte [Tradução de um formulário Web](translating-a-web-form.md).

## Inserir imagens {#inserting-images}

Para que as imagens sejam incluídas em formulários, elas devem ser salvas em um servidor acessível externamente.

Selecione o menu **[!UICONTROL Static elements]** > **[!UICONTROL Image]**

Selecione a fonte da imagem a ser inserida: ela pode vir da biblioteca de recurso público ou ser armazenada em um servidor externo acessível de fora.

![Propriedades do elemento de imagem para um Logotipo, com a Biblioteca de ofertas da lista de origem da imagem e Externo](assets/s_ncs_admin_survey_add_img.png)

Se essa for uma imagem da biblioteca, selecione-a na caixa de combinação do campo; se estiver localizada em um arquivo externo, insira o caminho de acesso. O rótulo será exibido passando o cursor sobre a imagem (coincide com um campo ALT em HTML) ou quando a imagem não for exibida.

A imagem pode ser visualizada na seção central do editor.
