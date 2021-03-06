---
title: Formulários de entrada de campanha
description: Saiba como personalizar formulários de entrada
exl-id: 62908bba-9cfa-42b6-b463-b601496d535b
source-git-commit: 5c1ced7972295e79418ac7ff14a6f0888e5ed39a
workflow-type: tm+mt
source-wordcount: '2554'
ht-degree: 3%

---

# Introdução aos formulários de entrada{#gs-ac-forms}

Ao criar ou estender um esquema, é necessário criar ou modificar os formulários de entrada associados para tornar essas alterações visíveis para os usuários finais.

Um formulário de entrada permite editar uma instância associada a um schema de dados no console do cliente do Adobe Campaign. O formulário é identificado por seu nome e namespace.

A chave de identificação de um formulário é uma string composta pelo namespace e pelo nome separados por dois pontos, por exemplo: &quot;cus:contact&quot;.

## Editar formulários de entrada

Crie e configure formulários de entrada a partir do **[!UICONTROL Administration]> [!UICONTROL Configuration] >[!UICONTROL Input forms]** pasta do console do cliente:

![](assets/form_arbo.png)

A zona de edição permite inserir o conteúdo XML do formulário de entrada:

![](assets/form_edit.png)

A visualização gera uma exibição do formulário de entrada:

![](assets/form_preview.png)

## Estrutura do formulário

A descrição de um formulário é um documento XML estruturado que está de acordo com a gramática do schema do formulário **xtk:form**.

O documento XML do formulário de entrada deve conter a variável `<form>` elemento raiz com o  **name** e  **namespace** atributos para preencher o nome e o namespace do formulário.

```
<form name="form_name" namespace="name_space">
...
</form>
```

Por padrão, um formulário é associado ao schema de dados com o mesmo nome e namespace. Para associar um formulário a um nome diferente, defina a variável **entity-schema** do `<form>` elemento para o nome da chave do schema. Para ilustrar a estrutura de um formulário de entrada, vamos descrever uma interface usando o schema de exemplo &quot;cus:recipient&quot;:

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

A descrição dos controles de edição começa do `<form>` elemento raiz. Um controle de edição é inserido em um elemento **`<input>`** com o atributo **xpath** contendo o caminho do campo do schema.

O controle de edição se adapta automaticamente ao tipo de dados correspondente e usa o rótulo definido no schema.

>[!NOTE]
>
>Você pode substituir o rótulo definido em seu schema de dados adicionando a variável **label** para a `<input>` elemento:\
>`<input label="E-mail address" xpath="@name" />`

Por padrão, cada campo é exibido em uma única linha e ocupa todo o espaço disponível, dependendo do tipo de dados.

![](../assets/do-not-localize/book.png) Todos os atributos de formulário estão listados em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/developer/campaign-api/api/control-Button.html){target=&quot;_blank&quot;}.

## Formatação {#formatting}

O layout dos controles se parece com o layout usado em tabelas HTML, com a possibilidade de dividir um controle em várias colunas, entrelaçar elementos ou especificar a ocupação do espaço disponível. Lembre-se, no entanto, que a formatação permite dividir a área para cima por proporções; não é possível especificar dimensões fixas para um objeto.

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

O **`<container>`** com o **colcount** permite forçar a exibição de controles filho em duas colunas.

O **colspan** em um controle estende o controle pelo número de colunas inseridas em seu valor:

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

Ao preencher a variável **type=&quot;frame&quot;** , o contêiner adiciona um quadro ao redor dos controles filhos com o rótulo contido no **label** atributo:

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

A **`<static>`** pode ser usado para formatar o formulário de entrada:

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

O **`<static>`** com a **separador** permite adicionar uma barra separadora com um rótulo contido na variável **label** atributo.

Um texto de ajuda foi adicionado usando o `<static>` com o tipo de ajuda. O conteúdo do texto é inserido no **label** atributo.

## Usar contêineres {#containers}

Use **contêineres** para agrupar um conjunto de controles. Eles são representados pela **`<container>`** elemento. Eles foram usados acima para formatar controles em várias colunas.

O **xpath** em um `<container>` permite simplificar a referência de controles secundários. A referência de controles é então relativa ao pai `<container>` pai.

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

Os contêineres são usados para construir controles complexos usando um conjunto de campos formatados em páginas.

### Adicionar guias (notebook) {#tab-container}

Use um **notebook** para formatar dados em páginas acessíveis a partir de guias.

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

O contêiner principal é definido pela variável **type=&quot;notebook&quot;** atributo. As guias são declaradas nos containers secundários e o rótulo das guias é preenchido da variável **label** atributo.

Adicione o **style=&quot;down&quot;** para forçar o posicionamento vertical de rótulos de tabulação abaixo do controle. Esse atributo é opcional. O valor padrão é **&quot;up&quot;**.

![](assets/do-not-localize/form_exemple7.png)

`<container style="down" type="notebook">  ... </container>`

### Adicionar ícones (caixa de ícones) {#icon-list}

Use esse contêiner para exibir uma barra de ícones vertical que permite selecionar as páginas a serem exibidas.

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

O contêiner principal é definido pela variável **type=&quot;iconbox&quot;** atributo. As páginas associadas aos ícones são declaradas nos containers secundários. O rótulo dos ícones é preenchido da variável **label** atributo.

O ícone de uma página é preenchido da variável `img="<image>"` , onde `<image>` é o nome da imagem correspondente à sua chave composta pelo nome e namespace (por exemplo, &quot;xtk:properties.png&quot;).

As imagens estão disponíveis no **[!UICONTROL Administration > Configuration > Images]** nó .

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

Um contêiner de visibilidade é definido pelo atributo **type=&quot;visibleGroup&quot;**. O **visibleIf** contém a condição de visibilidade.

Exemplos de sintaxe de condição:

* **visibleIf=&quot;@email=&#39;peter.martinezATneolane.net&#39;&quot;**: testa a igualdade em dados do tipo string. O valor de comparação deve estar entre aspas.
* **visibleIf=&quot;@gender >= 1 e @gender != 2&quot;**: em um valor numérico.
* **visibleIf=&quot;@boolean1=true ou @boolean2=false&quot;**: teste em campos booleanos.

### Exibição condicional (enabledGroup) {#enabling-container}

Esse contêiner permite ativar ou desativar um conjunto de dados de uma condição dinâmica. Desativar um controle impede que ele seja editado. O exemplo a seguir ilustra a ativação de controles do valor do campo &quot;Gênero&quot;:

```
<container type="enabledGroup" enabledIf="@gender=1">
  ...
</container>
<container type="enabledGroup" enabledIf="@gender=2">
  ...
</container>
```

Um contêiner de ativação é definido pela variável **type=&quot;enabledGroup&quot;** atributo. O **enabledIf** contém a condição de ativação.

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

A seleção de destino é acessível por meio do campo de edição. A entrada é assistida por um avanço de tipo para que um elemento de destino possa ser facilmente encontrado a partir dos primeiros caracteres inseridos. A pesquisa é então baseada no **Cálculo de cadeia de caracteres** definido no schema target. Se o schema não existir após a validação no controle, uma mensagem de confirmação da criação do target em tempo real será exibida. A confirmação cria um novo registro na tabela de target e o associa ao link .

Uma lista suspensa é usada para selecionar um elemento de destino da lista de registros já criados.

O **[!UICONTROL Modify the link]** ícone (pasta) inicia um formulário de seleção com a lista de elementos pretendidos e uma zona de filtro.

O **[!UICONTROL Edit link]** Ícone (lente de aumento) inicia o formulário de edição do elemento vinculado. O formulário usado é deduzido por padrão na chave do schema direcionado. O **formulário** permite forçar o nome do formulário de edição (por exemplo, &quot;cus:company2&quot;).

Você pode restringir a escolha de elementos target adicionando a variável **`<sysfilter>`** elemento da definição do link no formulário de entrada:

```
<input xpath="company">
  <sysFilter>
    <condition expr="[location/@city] =  'Newton"/>
  </sysFilter>
</input>
```

Também é possível classificar a lista com a variável **`<orderby>`** elemento:

```
<input xpath="company">
  <orderBy>
    <node expr="[location/@zipCode]"/>
  </orderBy>
</input>
```

## Propriedades do controle {#control-properties}

* **noAutoComplete**: desativa o tipo forward (com o valor &quot;true&quot;)
* **createMode**: cria o link dinamicamente, se ele não existir. Os valores possíveis são:

   * **nenhum**: desativa a criação. Uma mensagem de erro será exibida se o link não existir
   * **inline**: cria o link com o conteúdo no campo de edição
   * **edição**: exibe o formulário de edição no link . Quando o formulário é validado, os dados são salvos (modo padrão)

* **noZoom**: nenhum formulário de edição no link (com o valor &quot;true&quot;)
* **formulário**: sobrecarrega o formulário de edição do elemento direcionado

## Adicionar uma lista de links (não vinculado) {#list-of-links}

Um link inserido no schema de dados como um elemento de coleção (unbound=&quot;true&quot;) deve passar por uma lista para exibir todos os elementos associados a ele.

O princípio consiste em exibir a lista de elementos vinculados com carregamento de dados otimizado (download por lote de dados, execução da lista somente se estiver visível).

Exemplo de um link de coleção em um schema:

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

O controle de lista é definido pela variável **type=&quot;linklist&quot;** atributo. O caminho da lista deve se referir ao link de coleção.

As colunas são declaradas por meio do **`<input>`** elementos da lista. O **xpath** attribute se refere ao caminho do campo no schema target.

Uma barra de ferramentas com um rótulo (definido no link no schema) é colocada automaticamente acima da lista.

A lista pode ser filtrada por meio do **[!UICONTROL Filters]** e configuradas para adicionar e classificar as colunas.

O **[!UICONTROL Add]** e **[!UICONTROL Delete]** botões permitem adicionar e excluir elementos de coleção no link. Por padrão, a adição de um elemento inicia o formulário de edição do schema de destino.

O **[!UICONTROL Detail]** é adicionado automaticamente quando a função **zoom=&quot;true&quot;** é concluído na **`<input>`** da lista: ele permite iniciar o formulário de edição da linha selecionada.

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

Uma tabela de relacionamento permite vincular duas tabelas com uma cardinalidade N-N. A tabela de relacionamento contém apenas os links para as duas tabelas.

A adição de um elemento à lista deve, portanto, permitir que você complete uma lista de um dos dois links na tabela do relacionamento.

Exemplo de uma tabela de relacionamento em um schema:

```
<srcSchema name="subscription" namespace="cus">
  <element name="recipient" type="link" target="cus:recipient" label="Recipient"/>
  <element name="service" type="link" target="cus:service" label="Subscription service"/>
</srcSchema>
```

Para nosso exemplo, começamos com o formulário de entrada do schema &quot;cus:recipient&quot;. A lista deve exibir as associações com assinaturas de serviços e deve permitir adicionar uma assinatura selecionando um serviço existente.

![](assets/do-not-localize/form_exemple12.png)

```
<input type="linklist" xpath="subscription" xpathChoiceTarget="service" xpathEditTarget="service" zoom="true">
  <input xpath="recipient"/>
  <input xpath="service"/>
</input>
```

O **xpathChoiceTarget** permite iniciar um formulário de seleção no link inserido. A criação do registro da tabela de relacionamento atualizará automaticamente o link para o recipient atual e o serviço selecionado.

>[!NOTE]
>
>O **xpathEditTarget** permite forçar a edição da linha selecionada no link inserido.

### Propriedades da lista {#list-properties}

* **noToolbar**: oculta a barra de ferramentas (com o valor &quot;true&quot;)
* **toolbarCaption**: sobrecarrega o rótulo da barra de ferramentas
* **toolbarAlign**: modifica a geometria vertical ou horizontal da barra de ferramentas (valores possíveis: &quot;vertical&quot;|&quot;horizontal&quot;)
* **img**: exibe a imagem associada à lista
* **formulário**: sobrecarrega o formulário de edição do elemento direcionado
* **zoom**: adiciona o **[!UICONTROL Zoom]** botão para editar o elemento direcionado
* **xpathEditTarget**: conjuntos de edição no link inserido
* **xpathChoiceTarget**: para além disso, inicia o formulário de seleção no link inserido

## Adicionar controles de lista de memória {#memory-list-controls}

As listas de memória permitem editar os elementos de coleção usando o pré-carregamento de dados da lista. Esta lista não pode ser filtrada ou configurada.

Essas listas são usadas em elementos de coleção XML mapeados ou em links de baixo volume.

## Adicionar uma lista de colunas {#column-list}

Este controle exibe uma lista de colunas editável com uma barra de ferramentas contendo os botões Adicionar e Excluir.

```
<input xpath="rcpEvent" type="list">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

O controle de lista deve ser preenchido com o atributo **type=&quot;list&quot;** e o caminho da lista deve se referir ao elemento de coleção.

As colunas são declaradas no filho **`<input>`** tags da lista. O rótulo e o tamanho da coluna podem ser forçados com o **label** e **colSize** atributos.

>[!NOTE]
>
>As setas de ordem de classificação são adicionadas automaticamente quando a variável **ordered=&quot;true&quot;** é adicionado ao elemento de coleção no schema de dados.

Os botões da barra de ferramentas podem ser alinhados horizontalmente:

```
<input nolabel="true" toolbarCaption="List of events" type="list" xpath="rcpEvent" zoom="true">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

O **toolbarCaption** força o alinhamento horizontal da barra de ferramentas e insere o título acima da lista.

### Ativar zoom em uma lista {#zoom-in-a-list}

A inserção e a edição dos dados em uma lista podem ser inseridas em um formulário de edição separado.

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

O formulário de edição é preenchido no `<form>`  sob definição de lista. Sua estrutura é idêntica à de um formulário de entrada. O **[!UICONTROL Detail]** é adicionado automaticamente quando a função **zoom=&quot;true&quot;** é concluído na **`<input>`** da lista. Esse atributo permite iniciar o formulário de edição da linha selecionada.

>[!NOTE]
>
>Adicionar a **zoomOnAdd=&quot;true&quot;** força o formulário de edição a ser chamado quando um elemento de lista é inserido.

### Propriedades da lista {#list-properties-1}

* **noToolbar**: oculta a barra de ferramentas (com o valor &quot;true&quot;)
* **toolbarCaption**: sobrecarrega o rótulo da barra de ferramentas
* **toolbarAlign**: modifica o posicionamento da barra de ferramentas (valores possíveis: &quot;vertical&quot;|&quot;horizontal&quot;)
* **img**: exibe a imagem associada à lista
* **formulário**: sobrecarrega o formulário de edição do elemento direcionado
* **zoom**: adiciona o **[!UICONTROL Zoom]** botão para editar o elemento direcionado
* **zoomOnAdd**: inicia o formulário de edição na adição
* **xpathChoiceTarget**: para além disso, inicia o formulário de seleção no link inserido

## Adicionar campos não editáveis {#non-editable-fields}

Para exibir um campo e evitar sua edição, use o **`<value>`** ou preencha a **readOnly=&quot;true&quot;** no **`<input>`** .

Exemplo no campo &quot;Gênero&quot;:

![](assets/do-not-localize/form_exemple16.png)

```
<value value="@gender"/>
<input xpath="@gender" readOnly="true"/>
```

## Botão Adicionar rádio {#radio-button}

Um botão de opção permite escolher entre várias opções. O **`<input>`** as tags são usadas para listar as opções possíveis e a variável **checkedValue** especifica o valor associado à escolha.

Exemplo no campo &quot;Gênero&quot;:

```
<input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```

![](assets/do-not-localize/form_exemple17.png)

## Adicionar uma caixa de seleção {#checkbox}

Uma caixa de seleção reflete um estado booleano (selecionado ou não). Por padrão, esse controle é usado por campos &quot;Boolean&quot; (true/false). Uma variável com um valor padrão de 0 ou 1 pode ser associada a esse botão. Esse valor pode ser sobrecarregado por meio da variável **checkValue** atributos.

```
<input xpath="@boolean1"/>
<input xpath="@field1" type="checkbox" checkedValue="Y"/>
```

![](assets/do-not-localize/form_exemple20.png)

## Editar hierarquia de navegação {#navigation-hierarchy-edit}

Esse controle cria uma árvore em um conjunto de campos a serem editados.

Os controles a serem editados são agrupados em um **`<container>`** inseridos no **`<input>`** tag do controle de árvore:

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

Um campo de expressão atualiza um campo dinamicamente de uma expressão; o **`<input>`** é usada com uma **xpath** para inserir o caminho do campo a ser atualizado e uma **expr** que contém a expressão de atualização.

```
<!-- Example: updating the boolean1 field from the value contained in the field with path /tmp/@flag -->
<input expr="Iif([/tmp/@flag]=='On', true, false)" type="expr" xpath="@boolean1"/>
<input expr="[/ignored/@action] == 'FCP'" type="expr" xpath="@launchFCP"/>
```

## Contexto dos formulários {#context-of-forms}

A execução de um formulário de entrada inicializa um documento XML contendo os dados da entidade que está sendo editada. Este documento representa o contexto do formulário e pode ser usado como um espaço de trabalho.

### Atualizar o contexto {#updating-the-context}

Para modificar o contexto do formulário, use o `<set expr="<value>" xpath="<field>"/>` tag, onde `<field>` é o campo de destino e `<value>` é a expressão ou valor de atualização.

Exemplos de utilização da variável `<set>` tag:

* **`<set expr="'Test'" xpath="/tmp/@test" />`**: posiciona o valor &quot;Test&quot; no local temporário /tmp/@test1
* **`<set expr="'Test'" xpath="@lastName" />`**: atualiza a entidade no atributo &quot;lastName&quot; com o valor &quot;Test&quot;
* **`<set expr="true" xpath="@boolean1" />`**: define o valor do campo &quot;boolean1&quot; como &quot;true&quot;
* **`<set expr="@lastName" xpath="/tmp/@test" />`**: atualizações com o conteúdo do atributo &quot;lastName&quot;

O contexto do formulário pode ser atualizado ao inicializar e fechar o formulário por meio do **`<enter>`** e **`<leave>`** tags.

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
>O `<enter>`  e  `<leave>`   as tags podem ser usadas na `<container>` de páginas (tipos &quot;bloco de anotações&quot; e &quot;caixa de ícones&quot;).

### Idioma da expressão {#expression-language-}

Um idioma macro pode ser usado na definição do formulário para executar testes condicionais.

O **`<if expr="<expression>" />`** A tag executa as instruções especificadas na tag se a expressão for verificada:

```
<if expr="([/tmp/@test] == 'Test' or @lastName != 'Doe') and @boolean2 == true">
  <set xpath="@boolean1" expr="true"/>
</if>
```

O **`<check expr="<condition>" />`** combinada com a **`<error>`** impede a validação do formulário e exibe uma mensagem de erro se a condição não for atendida:

```
<leave>
  <check expr="/tmp/@test != ''">
    <error>You must populate the 'Test' field!</error> 
  </check>
</leave>
```

## Assistente (assistente) {#wizards}

Um assistente o orienta por um conjunto de etapas de entrada de dados no formulário de páginas. Os dados inseridos são salvos ao validar o formulário.

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

A presença do **type=&quot;wizard&quot;** no `<form>` permite definir o modo de assistente na construção do formulário. As páginas são concluídas de `<container>` elementos, que são filhos do `<form>` elemento. O `<container>` O elemento de uma página é preenchido com os atributos de título do título e desc para exibir a descrição sob o título da página. O **[!UICONTROL Previous]** e **[!UICONTROL Next]** botões são adicionados automaticamente para permitir a navegação entre páginas.

O **[!UICONTROL Finish]** salva os dados inseridos e fecha o formulário.

### Métodos SOAP {#soap-methods}

A execução do método SOAP pode ser iniciada a partir de um método preenchido **`<leave>`** no final de uma página.

O **`<soapcall>`** contém a chamada para o método com os seguintes parâmetros de entrada:

```
<soapCall name="<name>" service="<schema>">
  <param type="<type>" exprIn="<xpath>"/>  
  ...
</soapCall>
```

O nome do serviço e seu schema de implementação são inseridos por meio do **name** e **service** atributos do **`<soapcall>`** .

Os parâmetros de entrada são descritos na seção **`<param>`** elementos sob **`<soapcall>`** .

O tipo de parâmetro deve ser especificado por meio da variável **type** atributo. Os tipos possíveis são os seguintes:

* **string**: sequência de caracteres
* **booleano**: Booleano
* **byte**: Número inteiro de 8 bits
* **short**: Número inteiro de 16 bits
* **long**: Número inteiro de 32 bits
* **short**: Número inteiro de 16 bits
* **double**: número de ponto flutuante de precisão dupla
* **DOMElement**: nó do tipo elemento

O **exprIn** contém o local dos dados a serem transmitidos como parâmetro.

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
