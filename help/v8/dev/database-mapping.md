---
title: Mapeamento do banco de dados do Campaign
description: Mapeamento do banco de dados do Campaign
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '1463'
ht-degree: 0%

---

# Mapeamento de banco de dados{#database-mapping}

O mapeamento SQL do nosso schema de exemplo fornece o seguinte documento XML:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">
  <enumeration basetype="byte" name="gender">    
    <value label="Not specified" name="unknown" value="0"/>    
    <value label="Male" name="male" value="1"/>    
    <value label="Female" name="female" value="2"/> 
  </enumeration>  

  <element name="recipient" sqltable="CusRecipient">    
    <attribute desc="Recipient e-mail address" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
    <attribute default="GetDate()" label="Date of creation" name="created" sqlname="tsCreated" type="datetime"/>    
    <attribute enum="gender" label="Gender" name="gender" sqlname="iGender" type="byte"/>    
    <element label="Location" name="location">      
      <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
    </element>  
  </element>
</schema>
```

## Descrição {#description}

O elemento raiz do schema não é mais **`<srcschema>`**, mas **`<schema>`**.

Isso nos leva a outro tipo de documento, que é gerado automaticamente a partir do schema de origem, simplesmente conhecido como schema. Esse schema será usado pelo aplicativo Adobe Campaign.

Os nomes SQL são determinados automaticamente com base no nome e no tipo do elemento.

As regras de nomenclatura SQL são as seguintes:

* tabela: concatenação do namespace e do nome do schema

   No nosso exemplo, o nome da tabela é inserido por meio do elemento principal do schema no atributo **sqltable**:

   ```
   <element name="recipient" sqltable="CusRecipient">
   ```

* campo : nome do elemento precedido por um prefixo definido de acordo com o tipo (&#39;i&#39; para integer, &#39;d&#39; para double, &#39;s&#39; para string, &#39;ts&#39; para datas, etc.)

   O nome do campo é inserido por meio do atributo **sqlname** para cada **`<attribute>`** digitado e **`<element>`**:

   ```
   <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
   ```

>[!NOTE]
>
>Os nomes SQL podem ser sobrecarregados do schema de origem. Para fazer isso, preencha os atributos &quot;sqltable&quot; ou &quot;sqlname&quot; no elemento relacionado.

O script SQL para criar a tabela gerada do schema estendido é o seguinte:

```
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

As restrições do campo SQL são as seguintes:

* sem valores nulos em campos numéricos e de data,
* campos numéricos são inicializados para 0.

## Campos XML {#xml-fields}

Por padrão, qualquer elemento digitado **`<attribute>`** e **`<element>`** é mapeado em um campo SQL da tabela de schema de dados. No entanto, você pode fazer referência a esse campo em XML em vez de SQL, o que significa que os dados são armazenados em um campo de memorando (&quot;mData&quot;) da tabela que contém os valores de todos os campos XML. O armazenamento desses dados é um documento XML que observa a estrutura do schema.

Para preencher um campo em XML, você deve adicionar o atributo **xml** com o valor &quot;true&quot; ao elemento relacionado.

**Exemplo**: há dois exemplos de uso de campo XML.

* Campo de comentário de várias linhas:

   ```
   <element name="comment" xml="true" type="memo" label="Comment"/>
   ```

* Descrição dos dados no formato HTML:

   ```
   <element name="description" xml="true" type="html" label="Description"/>
   ```

   O tipo &quot;html&quot; permite armazenar o conteúdo do HTML em uma tag CDATA e exibir uma verificação de HTML edit especial na interface do cliente Adobe Campaign.

O uso de campos XML permite adicionar campos sem a necessidade de modificar a estrutura física do banco de dados. Outra vantagem é que você usa menos recursos (tamanho alocado para campos SQL, limite no número de campos por tabela etc.).

## Gerenciamento de chaves {#management-of-keys}

Uma tabela deve ter pelo menos uma chave para identificar um registro na tabela.

Uma chave é declarada do elemento principal do schema de dados.

```
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

As chaves obedecem às seguintes regras:

* Uma chave pode fazer referência a um ou mais campos na tabela.
* Uma chave é conhecida como &quot;primária&quot; (ou &quot;prioridade&quot;) quando é a primeira no schema a ser preenchida ou se contém o atributo **internal** com o valor &quot;true&quot;.

**Exemplo**:

* Adicionando uma chave ao endereço de email e à cidade:

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="email">
         <keyfield xpath="@email"/> 
         <keyfield xpath="location/@city"/> 
       </key>
   
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
       <element name="location" label="Location">
         <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
       </element>
     </element>
   </srcSchema>
   ```

   O schema gerado:

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
      <key name="email">      
       <keyfield xpath="@email"/>      
       <keyfield xpath="location/@city"/>    
      </key>    
   
      <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
      <element label="Location" name="location">      
        <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
      </element>  
     </element>
   </schema>
   ```

* Adição de uma chave primária ou interna no campo de nome &quot;id&quot;:

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="id" internal="true">
         <keyfield xpath="@id"/> 
       </key>
   
       <key name="email">
         <keyfield xpath="@email"/> 
       </key>
   
       <attribute name="id" type="long" label="Identifier"/>
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
     </element>
   </srcSchema>
   ```

   O schema gerado:

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
       <key name="email">      
         <keyfield xpath="@email"/>    
       </key>  
   
       <key internal="true" name="id">      
        <keyfield xpath="@id"/>    
       </key>    
   
       <attribute label="Identifier" name="id" sqlname="iRecipientId" type="long"/>    
       <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>  
     </element>
   </schema>
   ```

### Chave primária - Identificador

A chave primária das tabelas do Adobe Campaign é uma **ID universal exclusiva (UUID)** gerada automaticamente pelo mecanismo de banco de dados. O valor da chave é exclusivo em todo o banco de dados. O conteúdo da chave é gerado automaticamente na inserção do registro.

**Exemplo**

Declarando uma chave incremental no schema de origem:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

O schema gerado:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

Além da definição da chave, um campo numérico chamado &quot;id&quot; foi adicionado ao schema estendido para conter a chave primária gerada automaticamente.

>[!CAUTION]
>
>Um registro com uma chave primária definida como 0 é inserido automaticamente na criação da tabela. Esse registro é usado para evitar associações externas, que não são efetivas em tabelas de volume. Por padrão, todas as chaves estrangeiras são inicializadas com o valor 0 para que um resultado possa sempre ser retornado na associação quando o item de dados não for preenchido.

## Links: relação entre tabelas {#links--relation-between-tables}

Um link descreve a associação entre uma tabela e outra.

Os vários tipos de associações (conhecidas como &quot;cardinalidades&quot;) são os seguintes:

* Cardinalidade 1-1: uma ocorrência da tabela de origem pode ter no máximo uma ocorrência correspondente da tabela de destino.
* Cardinalidade 1-N: uma ocorrência da tabela de origem pode ter várias ocorrências correspondentes da tabela de destino, mas uma ocorrência da tabela de destino pode ter no máximo uma ocorrência correspondente da tabela de origem.
* Cardinalidade N-N: uma ocorrência da tabela de origem pode ter várias ocorrências correspondentes da tabela de destino, e vice-versa.

Na interface, você pode distinguir os diferentes tipos de relações facilmente graças aos ícones.

Para relações de associação com uma tabela/banco de dados de campanha:

* ![](assets/do-not-localize/join_with_campaign11.png) : Cardinalidade 1-1. Por exemplo, entre um recipient e um pedido atual. Um recipient pode ser relacionado a apenas uma ocorrência da tabela de pedido atual por vez.
* ![](assets/do-not-localize/externaljoin11.png) : Cardinalidade 1-1, junção externa. Por exemplo, entre um recipient e seu país. Um recipient pode ser relacionado a apenas uma ocorrência do país da tabela. O conteúdo da tabela de países não será salvo.
* ![](assets/do-not-localize/join_with_campaign1n.png) : Cardinalidade 1-N. Por exemplo, entre um recipient e a tabela de assinaturas. Um recipient pode ser relacionado a várias ocorrências na tabela de assinaturas.

Para relações de associação usando o Federated Database Access:

* ![](assets/do-not-localize/join_fda_11.png) : Cardinalidade 1-1
* ![](assets/do-not-localize/join_fda_1m.png) : Cardinalidade 1-N

![](../assets/do-not-localize/glass.png) Para obter mais informações sobre tabelas FDA, consulte  [Federated Data Access](../connect/fda.md).

Um link deve ser declarado no schema que contém a chave externa da tabela vinculada por meio do elemento principal:

```
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

Os links obedecem às seguintes regras:

* A definição de um link é inserida em um link **tipo** com os seguintes atributos:**`<element>`**

   * **name**: nome do link da tabela de origem,
   * **target**: nome do schema do target,
   * **rótulo**: rótulo do link,
   * **revLink**  (opcional): nome do link reverso do schema do target (deduzido automaticamente por padrão),
   * **integridade**  (opcional): integridade referencial da ocorrência da tabela de origem para a ocorrência da tabela de destino. Os valores possíveis são os seguintes:

      * **definir**: é possível excluir a ocorrência de origem se ela não for mais referenciada por uma ocorrência de destino,
      * **normal**: a exclusão da ocorrência de origem inicializa as chaves do link para a ocorrência de destino (modo padrão), esse tipo de integridade inicializa todas as chaves estrangeiras,
      * **Próprio**: a exclusão da ocorrência de origem leva à exclusão da ocorrência de destino,
      * **owncopy**: o mesmo que  **own**  (no caso de exclusão) ou duplica as ocorrências (no caso de duplicação),
      * **neutro**: não faz nada.
   * **revIntegrity**  (opcional): integridade no schema do target (opcional, &quot;normal&quot; por padrão),
   * **revCardinalidade**  (opcional): com o valor &quot;único&quot; preenche a cardinalidade com o tipo 1-1 (1-N por padrão).
   * **externalJoin**  (opcional): força a união externa
   * **revExternalJoin**  (opcional): força a junção externa no link inverso


* Um link faz referência a um ou mais campos da tabela de origem para a tabela de destino. Os campos que compõem a associação (elemento `<join>` ) não precisam ser preenchidos porque são automaticamente deduzidos por padrão usando a chave interna do schema de destino.
* Um link consiste em dois links médios, onde o primeiro é declarado do schema de origem e o segundo é criado automaticamente no schema estendido do schema de destino.
* Uma associação pode ser uma associação externa se o atributo **externalJoin** for adicionado, com o valor &quot;true&quot; (compatível no PostgreSQL).

>[!NOTE]
>
>Links são os elementos declarados no final do schema.

### Exemplo 1 {#example-1}

1-N relação com a tabela de schema &quot;cus:company&quot;:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

O schema gerado:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    ...
    <element label="Company" name="company" revLink="recipient" target="cus:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of 'Company' link (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

A definição do link é complementada pelos campos que compõem a associação, ou seja, a chave primária com seu XPath (&quot;@id&quot;) no schema de destino, e a chave estrangeira com seu XPath (&quot;@company-id&quot;) no schema.

A chave externa é adicionada automaticamente em um elemento que usa as mesmas características do campo associado na tabela de destino, com a seguinte convenção de nomenclatura: nome do schema target seguido pelo nome do campo associado (&quot;company-id&quot; em nosso exemplo).

Schema estendido do target (&quot;cus:company&quot;):

```
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany"  autopk="true" autouuid="true"> 
    <key internal="true" name="id">      
      <keyfield xpath="@id"/>    
    </key>
    ...
    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iCompanyId" type="long"/>
    ...
    <element belongsTo="cus:recipient" integrity="define" label="Contact" name="recipient" revLink="company" target="nms:recipient" type="link" unbound="true">      
      <join xpath-dst="@company-id" xpath-src="@id"/>    
    </element>
  </element>
</schema>
```

Um link reverso para a tabela &quot;cus:recipient&quot; foi adicionado com os seguintes parâmetros:

* **name**: deduz automaticamente do nome do schema de origem (pode ser forçado com o atributo &quot;revLink&quot; na definição do link no schema de origem)
* **revLink**: nome do link reverso
* **target**: chave do schema vinculado (schema &quot;cus:recipient&quot;)
* **unbound**: o link é declarado como um elemento de coleção para uma cardinalidade 1-N (por padrão)
* **integridade**: &quot;definir&quot; por padrão (pode ser forçado com o atributo &quot;revIntegrity&quot; na definição do link no schema de origem).

### Exemplo 2 {#example-2}

Neste exemplo, declararemos um link para a tabela de schema &quot;nms:address&quot;. A associação é uma associação externa e é preenchida explicitamente com o endereço de email do recipient e o campo &quot;@address&quot; da tabela vinculada (&quot;nms:address&quot;).

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"> 
    ...
    <element integrity="neutral" label="Info about email" name="emailInfo" revIntegrity="neutral" revLink="recipient" target="nms:address" type="link" externalJoin="true">      
      <join xpath-dst="@address" xpath-src="@email"/>
    </element>
  </element>
</srcSchema>
```

### Exemplo 3 {#example-3}

1-1 relação com a tabela de schema &quot;cus:extension&quot;:

```
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

### Exemplo 4 {#example-4}

Link para uma pasta (schema &quot;xtk:folder&quot;):

```
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

O valor padrão retorna o identificador do primeiro arquivo de tipo de parâmetro elegível inserido na função &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot;.

### Exemplo 5 {#example-5}

Neste exemplo, queremos criar uma chave em um link (&quot;empresa&quot; para &quot;cus:empresa&quot; schema) com o atributo **xlink** e um campo da tabela (&quot;email&quot;):

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <key name="companyEmail"> 
      <keyfield xpath="@email"/>
      <keyfield xlink="company"/>
    </key>
    
    <attribute name="email" type="string" length="80" label="Email" desc="Recipient email"/>
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

O schema gerado:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <key name="companyEmail">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </key>

    <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>
    <element label="Company" name="company" revLink="recipient" target="sfa:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of link 'Company' (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

A definição da chave do nome &quot;companyEmail&quot; foi estendida com a chave externa do link &quot;company&quot;.
