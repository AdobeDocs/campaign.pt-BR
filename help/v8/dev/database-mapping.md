---
title: Mapeamento do banco de dados do Campaign
description: Mapeamento do banco de dados do Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# Mapeamento de banco de dados{#database-mapping}

O mapeamento SQL do nosso schema de exemplo fornece o seguinte documento XML:

```sql
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

O elemento raiz do esquema não é mais **`<srcschema>`**, mas **`<schema>`**.

Isso nos leva a outro tipo de documento, que é gerado automaticamente a partir do schema de origem, chamado simplesmente de schema. Este esquema será usado pelo aplicativo do Adobe Campaign.

Os nomes SQL são determinados automaticamente com base no nome e no tipo do elemento.

As regras de nomenclatura SQL são as seguintes:

* tabela: concatenação do namespace e do nome do schema

  No nosso exemplo, o nome da tabela é inserido por meio do elemento principal do schema na **sqltable** atributo:

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* field: nome do elemento precedido por um prefixo definido de acordo com o tipo (&#39;i&#39; para inteiro, &#39;d&#39; para duplo, &#39;s&#39; para string, &#39;ts&#39; para datas etc.)

  O nome do campo é inserido por meio da variável **sqlname** atributo para cada tipo **`<attribute>`** e **`<element>`**:

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>Os nomes SQL podem ser sobrecarregados do esquema de origem. Para fazer isso, preencha os atributos &quot;sqltable&quot; ou &quot;sqlname&quot; no elemento relacionado.

O script SQL para criar a tabela gerada a partir do schema estendido é o seguinte:

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

As restrições do campo SQL são as seguintes:

* nenhum valor nulo em campos numéricos e de data
* campos numéricos são inicializados como 0

## Campos XML {#xml-fields}

Por padrão, qualquer tipo **`<attribute>`** e **`<element>`** O elemento é mapeado em um campo SQL da tabela de esquema de dados. No entanto, você pode fazer referência a esse campo em XML, em vez de SQL, o que significa que os dados são armazenados em um campo de memorando (&quot;mData&quot;) da tabela que contém os valores de todos os campos XML. O armazenamento desses dados é um documento XML que observa a estrutura do schema.

Para preencher um campo em XML, é necessário adicionar o **xml** com o valor &quot;true&quot; ao elemento em questão.

**Exemplos**

* Campo de comentário multilinha:

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* Descrição dos dados em formato HTML:

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  O tipo &quot;html&quot; permite armazenar o conteúdo do HTML em uma tag CDATA e exibir uma verificação de edição de HTML especial na interface do cliente do Adobe Campaign.

O uso de campos XML permite adicionar campos sem a necessidade de modificar a estrutura física do banco de dados. Outra vantagem é que você usa menos recursos (tamanho alocado para campos SQL, limite do número de campos por tabela etc.).
