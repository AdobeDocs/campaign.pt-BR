---
title: Formulários de entrada de campanha
description: Saiba como personalizar formulários de entrada
feature: Web Forms, Landing Pages
role: Developer
level: Beginner, Intermediate
exl-id: 62908bba-9cfa-42b6-b463-b601496d535b
source-git-commit: 4f9183c7f1d12feb255a0050da423647f0fce85e
workflow-type: tm+mt
source-wordcount: '2551'
ht-degree: 4%

---

# Introdução aos formulários de entrada {#gs-ac-forms}

Ao criar ou estender um esquema, é necessário criar ou modificar os formulários de entrada associados para tornar essas alterações visíveis para os usuários finais.

Um formulário de entrada permite editar uma instância associada a um esquema de dados no Console do cliente do Adobe Campaign. O formulário é identificado por seu nome e namespace.

A chave de identificação de um formulário é uma cadeia de caracteres formada pelo namespace e pelo nome separados por dois pontos, por exemplo: &quot;cus:contact&quot;.

## Editar formulários de entrada

Crie e configure formulários de entrada da pasta **[!UICONTROL Administration]> [!UICONTROL Configuration] >[!UICONTROL Input forms]** do Console do Cliente:

![](assets/form_arbo.png)

A zona de edição permite inserir o conteúdo XML do formulário de entrada:

![](assets/form_edit.png)

A pré-visualização gera uma exibição do formulário de entrada:

![](assets/form_preview.png)

## Estrutura do formulário

A descrição de um formulário é um documento XML estruturado que observa a gramática do esquema de formulário **xtk:form**.

O documento XML do formulário de entrada deve conter o elemento raiz `<form>` com os atributos **name** e **namespace** para preencher o nome e o namespace do formulário.

```
<form name="form_name" namespace="name_space">
...
</form>
```

Por padrão, um formulário é associado ao schema de dados com o mesmo nome e namespace. Para associar um formulário a um nome diferente, defina o atributo **entity-schema** do elemento `<form>` como o nome da chave do esquema. Para ilustrar a estrutura de um formulário de entrada, descrevamos uma interface usando o schema de exemplo &quot;cus:recipient&quot;:

```
<srcSchema name="recipient" namespace="cus">
  <enumeration name="gender" basetype="byte">    
    <value name="unknown" label="Not specified" value="0"/>    
    <value name="male" label="Male" value="1"/>   
    <value name="female" label="Female" value="2"/>   
  </enumeration>

  <element name="recipient">
    <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
    <attribute name="birthDate" type="datetime" label="Date"/>
    <attribute name="gender" type="byte" label="Gender" enum="gender"/>
  </element>
</srcSchema>
```

O formulário de entrada com base no schema de exemplo:

![](assets/do-not-localize/form_exemple1.png)

```
<form name="recipient" namespace="cus">
  <input xpath="@gender"/>
  <input xpath="@birthDate"/>
  <input xpath="@email"/>
</form>
```

A descrição dos controles de edição começa no elemento raiz `<form>`. Um controle de edição é inserido em um elemento **`<input>`** com o atributo **xpath** contendo o caminho do campo do schema.

O controle de edição se adapta automaticamente ao tipo de dados correspondente e usa o rótulo definido no schema.

>[!NOTE]
>
>Você pode substituir o rótulo definido em seu esquema de dados adicionando o atributo **label** ao elemento `<input>`:\
>`<input label="E-mail address" xpath="@name" />`

Por padrão, cada campo é exibido em uma única linha e ocupa todo o espaço disponível, dependendo do tipo de dados.

Todos os atributos de formulário estão listados na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/developer/campaign-api/api/control-Button.html?lang=pt-BR){target="_blank"}.

## Formatação {#formatting}

O layout dos controles é semelhante ao layout usado nas tabelas do HTML, com a possibilidade de dividir um controle em várias colunas, entrelaçar elementos ou especificar a ocupação do espaço disponível. No entanto, lembre-se de que a formatação só permite dividir a área por proporções; não é possível especificar dimensões fixas para um objeto.

Para exibir os controles do exemplo acima em duas colunas:

![](assets/do-not-localize/form_exemple2.png)

```
<form name="recipient" namespace="cus">
  <container colcount="2">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email"/>
  </container>
</form>
```

O elemento **`<container>`** com o atributo **colcount** permite forçar a exibição de controles filho em duas colunas.

O atributo **colspan** em um controle estende o controle pelo número de colunas inseridas em seu valor:

![](assets/do-not-localize/form_exemple3.png)

```
<form name="recipient" namespace="cus">
  <container colcount="2">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
</form> 
```

Ao preencher o atributo **type=&quot;frame&quot;**, o contêiner adiciona um quadro ao redor dos controles filho com o rótulo contido no atributo **label**:

![](assets/do-not-localize/form_exemple4.png)

```
<form name="recipient" namespace="cus">
  <container colcount="2" type="frame" label="General">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
</form>
```

Um elemento **`<static>`** pode ser usado para formatar o formulário de entrada:

![](assets/do-not-localize/form_exemple5.png)

```
<form name="recipient" namespace="cus">
  <static type="separator" colspan="2" label="General"/>
  <input xpath="@gender"/>
  <input xpath="@birthDate"/>
  <input xpath="@email" colspan="2"/>
  <static type="help" label="General information about recipient with date of birth, gender, and e-mail address." colspan="2"/>
</form>
```

A marca **`<static>`** com o tipo **separator** permite adicionar uma barra separadora com um rótulo contido no atributo **label**.

Um texto de ajuda foi adicionado usando a marca `<static>` com o tipo de ajuda. O conteúdo do texto é inserido no atributo **rótulo**.

## Usar contêineres {#containers}

Use **contêineres** para agrupar um conjunto de controles. Eles são representados pelo elemento **`<container>`**. Eles foram usados acima para formatar controles em várias colunas.

O atributo **xpath** em um `<container>` permite simplificar a referência a controles filho. A referência de controles é então relativa ao pai `<container>`.

Exemplo de um contêiner sem &quot;xpath&quot;:

```
<container colcount="2">
  <input xpath="location/@zipCode"/>
  <input xpath="location/@city"/>
</container>
```

Exemplo com a adição de &quot;xpath&quot; ao elemento chamado &quot;location&quot;:

```
<container colcount="2" xpath="location">
  <input xpath="@zipCode"/>
  <input xpath="@city"/>
</container>
```

Os containers são usados para construir controles complexos usando um conjunto de campos formatados em páginas.

### Adicionar guias (bloco de anotações) {#tab-container}

Use um contêiner de **bloco de anotações** para formatar dados em páginas que possam ser acessadas de guias.

![](assets/do-not-localize/form_exemple6.png)

```
<container type="notebook">
  <container colcount="2" label="General">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
  <container colcount="2" label="Location">
    ...
  </container>
</container>
```

O container principal é definido pelo atributo **type=&quot;notebook&quot;**. As guias são declaradas nos contêineres filho, e o rótulo das guias é preenchido a partir do atributo **rótulo**.

Adicione o atributo **style=&quot;down&quot;** para forçar o posicionamento vertical dos rótulos de tabulação abaixo do controle. Este atributo é opcional. O valor padrão é **&quot;up&quot;**.

![](assets/do-not-localize/form_exemple7.png)

`<container style="down" type="notebook">  ... </container>`

### Adicionar ícones (caixa de ícones) {#icon-list}

Use este contêiner para exibir uma barra de ícones vertical que permite selecionar as páginas a serem exibidas.

![](assets/do-not-localize/form_exemple8.png)

```
<container type="iconbox">
  <container colcount="2" label="General" img="xtk:properties.png">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
  <container colcount="2" label="Location" img="nms:msgfolder.png">
    ...
  </container>
</container>
```

O container principal é definido pelo atributo **type=&quot;iconbox&quot;**. As páginas associadas aos ícones são declaradas nos contêineres filho. O rótulo dos ícones é preenchido a partir do atributo **label**.

O ícone de uma página é preenchido a partir do atributo `img="<image>"`, onde `<image>` é o nome da imagem correspondente à sua chave composta do nome e do namespace (por exemplo, &quot;xtk:properties.png&quot;).

As imagens estão disponíveis no nó **[!UICONTROL Administration > Configuration > Images]**.

### Ocultar contêineres (visibleGroup) {#visibility-container}

Você pode ocultar um conjunto de controles por meio de uma condição dinâmica.

Este exemplo ilustra a visibilidade dos controles no valor do campo &quot;Gênero&quot;:

```
<container type="visibleGroup" visibleIf="@gender=1">
  ...
</container>
<container type="visibleGroup" visibleIf="@gender=2">
  ...
</container>
```

Um contêiner de visibilidade é definido pelo atributo **type=&quot;visibleGroup&quot;**. O atributo **visibleIf** contém a condição de visibilidade.

Exemplos de sintaxe de condição:

* **visibleIf=&quot;@email=&#39;peter.martinezATneeolane.net&#39;&quot;**: testa a igualdade nos dados do tipo cadeia de caracteres. O valor de comparação deve estar entre aspas.
* **visibleIf=&quot;@gender >= 1 e @gender != 2&quot;**: condição em um valor numérico.
* **visibleIf=&quot;@boolean1=true ou @boolean2=false&quot;**: teste em campos booleanos.

### Exibição condicional (enabledGroup) {#enabling-container}

Esse container permite ativar ou desativar um conjunto de dados de uma condição dinâmica. Desabilitar um controle impede que ele seja editado. O exemplo a seguir ilustra a ativação de controles a partir do valor do campo &quot;Gênero&quot;:

```
<container type="enabledGroup" enabledIf="@gender=1">
  ...
</container>
<container type="enabledGroup" enabledIf="@gender=2">
  ...
</container>
```

Um contêiner de habilitação é definido pelo atributo **type=&quot;enabledGroup&quot;**. O atributo **enabledIf** contém a condição de ativação.

## Editar um link {#editing-a-link}

Lembre-se de que um link é declarado no schema de dados da seguinte maneira:

```
<element label="Company" name="company" target="cus:company" type="link"/>
```

O controle de edição do link em seu formulário de entrada é o seguinte:

![](assets/do-not-localize/form_exemple9.png)

```
<input xpath="company"/>
```

A seleção de público-alvo pode ser acessada por meio do campo de edição. A entrada é assistida pelo tipo antecipado, para que um elemento de destino possa ser facilmente encontrado a partir dos primeiros caracteres inseridos. A pesquisa é baseada na **cadeia de caracteres de cálculo** definida no esquema de destino. Se o schema não existir após a validação no controle, uma mensagem de confirmação da criação do target em tempo real será exibida. A confirmação cria um novo registro na tabela de target e o associa ao link.

Uma lista suspensa é usada para selecionar um elemento target na lista de registros já criados.

O ícone **[!UICONTROL Modify the link]** (pasta) inicia um formulário de seleção com a lista de elementos direcionados e uma zona de filtro.

O ícone **[!UICONTROL Edit link]** (lente de aumento) inicia o formulário de edição do elemento vinculado. O formulário usado é deduzido por padrão na chave do schema direcionado. O atributo **form** permite forçar o nome do formulário de edição (por exemplo, &quot;cus:company2&quot;).

Você pode restringir a opção de elementos target adicionando o elemento **`<sysfilter>`** da definição de link no formulário de entrada:

```
<input xpath="company">
  <sysFilter>
    <condition expr="[location/@city] =  'Newton"/>
  </sysFilter>
</input>
```

Você também pode classificar a lista com o elemento **`<orderby>`**:

```
<input xpath="company">
  <orderBy>
    <node expr="[location/@zipCode]"/>
  </orderBy>
</input>
```

## Propriedades de controle {#control-properties}

* **noAutoComplete**: desabilita a digitação antecipada (com o valor &quot;true&quot;)
* **createMode**: cria o link imediatamente se ele não existir. Os valores possíveis são:

   * **nenhum**: desabilita a criação. Uma mensagem de erro será exibida se o link não existir
   * **inline**: cria o link com o conteúdo no campo de edição
   * **edição**: exibe o formulário de edição no link. Quando o formulário for validado, os dados serão salvos (modo padrão)

* **noZoom**: nenhum formulário de edição no link (com o valor &quot;true&quot;)
* **formulário**: sobrecarrega o formulário de edição do elemento direcionado

## Adicionar uma lista de links (não vinculados) {#list-of-links}

Um link inserido no schema de dados como um elemento de coleção (unbound=&quot;true&quot;) deve passar por uma lista para exibir todos os elementos associados a ele.

O princípio consiste em exibir a lista de elementos vinculados com carregamento de dados otimizado (download por lote de dados, execução da lista somente se estiver visível).

Exemplo de um link de coleção em um esquema:

```
<element label="Events" name="rcpEvent" target="cus:event" type="link" unbound="true">
...
</element>
```

A lista em seu formulário de entrada:

```
 <input xpath="rcpEvent" type="linklist">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

O controle de lista é definido pelo atributo **type=&quot;linklist&quot;**. O caminho da lista deve fazer referência ao link da coleção.

As colunas são declaradas por meio dos elementos **`<input>`** da lista. O atributo **xpath** refere-se ao caminho do campo no esquema de destino.

Uma barra de ferramentas com um rótulo (definido no link no schema) é colocada automaticamente acima da lista.

A lista pode ser filtrada por meio do botão **[!UICONTROL Filters]** e configurada para adicionar e classificar as colunas.

Os botões **[!UICONTROL Add]** e **[!UICONTROL Delete]** permitem adicionar e excluir elementos de coleção no link. Por padrão, adicionar um elemento inicia o formulário de edição do schema de destino.

O botão **[!UICONTROL Detail]** é adicionado automaticamente quando o atributo **zoom=&quot;true&quot;** é concluído na marca **`<input>`** da lista: ele permite iniciar o formulário de edição da linha selecionada.

A filtragem e a classificação podem ser aplicadas quando a lista está sendo carregada:

```
 <input xpath="rcpEvent" type="linklist">
  <input xpath="@label"/>
  <input xpath="@date"/>
  <sysFilter>
    <condition expr="@type = 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@date" sortDesc="true"/>
  </orderBy>
</input>
```

## Definir uma tabela de relacionamento {#relationship-table}

Uma tabela de relação permite vincular duas tabelas com cardinalidade N-N. A tabela de relacionamento contém apenas os links para as duas tabelas.

A adição de um elemento à lista deve, portanto, permitir que você complete uma lista de um dos dois links na tabela de relacionamento.

Exemplo de uma tabela de relação em um esquema:

```
<srcSchema name="subscription" namespace="cus">
  <element name="recipient" type="link" target="cus:recipient" label="Recipient"/>
  <element name="service" type="link" target="cus:service" label="Subscription service"/>
</srcSchema>
```

Para nosso exemplo, começamos com o formulário de entrada do schema &quot;cus:recipient&quot;. A lista deve exibir as associações com assinaturas para serviços e permitir que você adicione uma assinatura selecionando um serviço existente.

![](assets/do-not-localize/form_exemple12.png)

```
<input type="linklist" xpath="subscription" xpathChoiceTarget="service" xpathEditTarget="service" zoom="true">
  <input xpath="recipient"/>
  <input xpath="service"/>
</input>
```

O atributo **xpathChoiceTarget** permite iniciar um formulário de seleção no link inserido. A criação do registro da tabela de relacionamento atualizará automaticamente o link para o recipient atual e o serviço selecionado.

>[!NOTE]
>
>O atributo **xpathEditTarget** permite forçar a edição da linha selecionada no link inserido.

### Propriedades da lista {#list-properties}

* **noToolbar**: oculta a barra de ferramentas (com o valor &quot;true&quot;)
* **toolbarCaption**: sobrecarrega o rótulo da barra de ferramentas
* **toolbarAlign**: modifica a geometria vertical ou horizontal da barra de ferramentas (valores possíveis: &quot;vertical&quot;|&quot;horizontal&quot;)
* **img**: exibe a imagem associada à lista
* **formulário**: sobrecarrega o formulário de edição do elemento direcionado
* **zoom**: adiciona o botão **[!UICONTROL Zoom]** para editar o elemento direcionado
* **xpathEditTarget**: define a edição no link inserido
* **xpathChoiceTarget**: para adição, inicia o formulário de seleção no link inserido

## Adicionar controles de lista de memória {#memory-list-controls}

As listas de memória permitem editar os elementos de coleção usando o pré-carregamento de dados de lista. Esta lista não pode ser filtrada nem configurada.

Essas listas são usadas em elementos de coleção mapeados XML ou em links de baixo volume.

## Adicionar uma lista de colunas {#column-list}

Este controle exibe uma lista de colunas editável com uma barra de ferramentas contendo os botões Adicionar e Excluir.

```
<input xpath="rcpEvent" type="list">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

O controle de lista deve ser preenchido com o atributo **type=&quot;list&quot;** e o caminho da lista deve se referir ao elemento de coleção.

As colunas são declaradas nas marcas filho **`<input>`** da lista. O rótulo e o tamanho da coluna podem ser forçados com os atributos **label** e **colSize**.

>[!NOTE]
>
>As setas de ordem de classificação são adicionadas automaticamente quando o atributo **ordered=&quot;true&quot;** é adicionado ao elemento de coleção no esquema de dados.

Os botões da barra de ferramentas podem ser alinhados horizontalmente:

```
<input nolabel="true" toolbarCaption="List of events" type="list" xpath="rcpEvent" zoom="true">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

O atributo **toolbarCaption** força o alinhamento horizontal da barra de ferramentas e insere o título acima da lista.

### Ativar o zoom em uma lista {#zoom-in-a-list}

A inserção e a edição de dados em uma lista podem ser inseridas em um formulário de edição separado.

```
<input nolabel="true" toolbarCaption="List of events" type="list" xpath="rcpEvent" zoom="true" zoomOnAdd="true">
  <input xpath="@label"/>
  <input xpath="@date"/>

  <form colcount="2" label="Event">
    <input xpath="@label"/>
    <input xpath="@date"/>
  </form>
</input>
```

O formulário de edição é preenchido no elemento `<form>` na definição da lista. Sua estrutura é idêntica à de um formulário de entrada. O botão **[!UICONTROL Detail]** é adicionado automaticamente quando o atributo **zoom=&quot;true&quot;** é concluído na marca **`<input>`** da lista. Este atributo permite iniciar o formulário de edição da linha selecionada.

>[!NOTE]
>
>A adição do atributo **zoomOnAdd=&quot;true&quot;** força o formulário de edição a ser chamado quando um elemento de lista é inserido.

### Propriedades da lista {#list-properties-1}

* **noToolbar**: oculta a barra de ferramentas (com o valor &quot;true&quot;)
* **toolbarCaption**: sobrecarrega o rótulo da barra de ferramentas
* **toolbarAlign**: modifica o posicionamento da barra de ferramentas (valores possíveis: &quot;vertical&quot;|&quot;horizontal&quot;)
* **img**: exibe a imagem associada à lista
* **formulário**: sobrecarrega o formulário de edição do elemento direcionado
* **zoom**: adiciona o botão **[!UICONTROL Zoom]** para editar o elemento direcionado
* **zoomOnAdd**: inicia o formulário de edição na adição
* **xpathChoiceTarget**: para adição, inicia o formulário de seleção no link inserido

## Adicionar campos não editáveis {#non-editable-fields}

Para exibir um campo e evitar que ele seja editado, use a marca **`<value>`** ou preencha o atributo **readOnly=&quot;true&quot;** na marca **`<input>`**.

Exemplo no campo &quot;Sexo&quot;:

![](assets/do-not-localize/form_exemple16.png)

```
<value value="@gender"/>
<input xpath="@gender" readOnly="true"/>
```

## Adicionar botão de opção {#radio-button}

Um botão de opção permite escolher entre várias opções. As marcas **`<input>`** são usadas para listar as opções possíveis, e o atributo **checkedValue** especifica o valor associado à escolha.

Exemplo no campo &quot;Sexo&quot;:

```
<input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```

![](assets/do-not-localize/form_exemple17.png)

## Adicionar uma caixa de seleção {#checkbox}

Uma caixa de seleção reflete um estado booleano (selecionado ou não). Por padrão, esse controle é usado por campos &quot;Booleano&quot; (true/false). Uma variável que assume um valor padrão de 0 ou 1 pode ser associada a esse botão. Este valor pode ser sobrecarregado por meio dos atributos **checkValue**.

```
<input xpath="@boolean1"/>
<input xpath="@field1" type="checkbox" checkedValue="Y"/>
```

![](assets/do-not-localize/form_exemple20.png)

## Editar hierarquia de navegação {#navigation-hierarchy-edit}

Este controle cria uma árvore em um conjunto de campos a serem editados.

Os controles a serem editados estão agrupados em um **`<container>`** inserido na marca **`<input>`** do controle de árvore:

```
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
  </container>
</input>
```

![](assets/do-not-localize/form_exemple18.png)

## Adicionar um campo de expressão {#expression-field}

Um campo de expressão atualiza um campo dinamicamente de uma expressão; a marca **`<input>`** é usada com um atributo **xpath** para inserir o caminho do campo a ser atualizado e um atributo **expr** contendo a expressão de atualização.

```
<!-- Example: updating the boolean1 field from the value contained in the field with path /tmp/@flag -->
<input expr="Iif([/tmp/@flag]=='On', true, false)" type="expr" xpath="@boolean1"/>
<input expr="[/ignored/@action] == 'FCP'" type="expr" xpath="@launchFCP"/>
```

## Contexto de formulários {#context-of-forms}

A execução de um formulário de entrada inicializa um documento XML contendo os dados da entidade que está sendo editada. Este documento representa o contexto do formulário e pode ser usado como um espaço de trabalho.

### Atualizar o contexto {#updating-the-context}

Para modificar o contexto do formulário, use a marca `<set expr="<value>" xpath="<field>"/>`, em que `<field>` é o campo de destino e `<value>` é a expressão ou o valor de atualização.

Exemplos de uso da tag `<set>`:

* **`<set expr="'Test'" xpath="/tmp/@test" />`**: posiciona o valor &#39;Test&#39; no local temporário /tmp/@test1
* **`<set expr="'Test'" xpath="@lastName" />`**: atualiza a entidade no atributo &quot;lastName&quot; com o valor &#39;Test&#39;
* **`<set expr="true" xpath="@boolean1" />`**: define o valor do campo &quot;boolean1&quot; como &quot;true&quot;
* **`<set expr="@lastName" xpath="/tmp/@test" />`**: atualizações com o conteúdo do atributo &quot;lastName&quot;

O contexto do formulário pode ser atualizado ao inicializar e fechar o formulário por meio das marcas **`<enter>`** e **`<leave>`**.

```
<form name="recipient" namespace="cus">
  <enter>
    <set...
  </enter>
  ...
  <leave>
    <set...
  </leave>
</form>
```

>[!NOTE]
>
>Os `<enter>` e `<leave>`   as marcas podem ser usadas no `<container>` de páginas (tipos de &quot;bloco de anotações&quot; e &quot;caixa de ícones&quot;).

### Linguagem de expressão {#expression-language-}

Uma linguagem macro pode ser usada na definição do formulário para executar testes condicionais.

A marca **`<if expr="<expression>" />`** executa as instruções especificadas na marca se a expressão for verificada:

```
<if expr="([/tmp/@test] == 'Test' or @lastName != 'Doe') and @boolean2 == true">
  <set xpath="@boolean1" expr="true"/>
</if>
```

A marca **`<check expr="<condition>" />`** combinada com a marca **`<error>`** impede a validação do formulário e exibe uma mensagem de erro se a condição não for atendida:

```
<leave>
  <check expr="/tmp/@test != ''">
    <error>You must populate the 'Test' field!</error> 
  </check>
</leave>
```

## Assistente (assistente) {#wizards}

Um assistente orienta você sobre um conjunto de etapas de entrada de dados no formato de páginas. Os dados inseridos são salvos quando você valida o formulário.

Para adicionar um assistente, use o seguinte tipo de estrutura:

```
<form type="wizard" name="example" namespace="cus" img="nms:rcpgroup32.png" label="Wizard example" entity-schema="nms:recipient">
  <container title="Title of page 1" desc="Long description of page 1">
    <input xpath="@lastName"/>
    <input xpath="comment"/>
  </container>
  <container title="Title of page 2" desc="Long description of page 2">
    ...
  </container>
  ...
</form>
```

A presença do atributo **type=&quot;wizard&quot;** no elemento `<form>` permite definir o modo de assistente na construção do formulário. As páginas foram concluídas com base nos elementos `<container>`, que são filhos do elemento `<form>`. O elemento `<container>` de uma página é preenchido com os atributos de título do título e desc para exibir a descrição sob o título da página. Os botões **[!UICONTROL Previous]** e **[!UICONTROL Next]** são adicionados automaticamente para permitir a navegação entre páginas.

O botão **[!UICONTROL Finish]** salva os dados inseridos e fecha o formulário.

### Métodos SOAP {#soap-methods}

A execução do método SOAP pode ser iniciada a partir de uma tag **`<leave>`** preenchida no final de uma página.

A marca **`<soapcall>`** contém a chamada para o método com os seguintes parâmetros de entrada:

```
<soapCall name="<name>" service="<schema>">
  <param type="<type>" exprIn="<xpath>"/>  
  ...
</soapCall>
```

O nome do serviço e seu esquema de implementação são inseridos pelos atributos **name** e **service** da marca **`<soapcall>`**.

Os parâmetros de entrada são descritos nos elementos **`<param>`** sob a marca **`<soapcall>`**.

O tipo de parâmetro deve ser especificado por meio do atributo **type**. Os tipos possíveis são os seguintes:

* **cadeia de caracteres**: cadeia de caracteres
* **booleano**: booleano
* **byte**: inteiro de 8 bits
* **short**: inteiro de 16 bits
* **long**: inteiro de 32 bits
* **short**: inteiro de 16 bits
* **double**: número de ponto flutuante de precisão dupla
* **DOMElement**: nó de tipo de elemento

O atributo **exprIn** contém o local dos dados a serem passados como parâmetro.

**Exemplo**:

```
<leave>
  <soapCall name="RegisterGroup" service="nms:recipient">         
    <param type="DOMElement" exprIn="/tmp/entityList"/>         
    <param type="DOMElement" exprIn="/tmp/choiceList"/>         
    <param type="boolean"    exprIn="true"/>       
  </soapCall>
</leave>
```
