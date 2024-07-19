---
title: Gerenciamento de chaves no banco de dados do Campaign
description: Entender o gerenciamento de chaves em esquemas do Adobe Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: cf1f5cfc-172f-44ec-ac97-804d15f9d628
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Gerenciamento de chaves {#management-of-keys}

Cada tabela associada a um schema de dados deve ter pelo menos uma chave para identificar um registro em uma tabela.

Uma chave é declarada pelo elemento principal do schema de dados.

```sql
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Uma chave é conhecida como &quot;chave primária&quot; quando é a primeira no esquema a ser preenchida, ou se contém o atributo `internal` definido como &quot;true&quot;.

Uma chave pode fazer referência a um ou mais campos na tabela.

**Exemplo**:

* Adicionando uma chave ao endereço de e-mail e à cidade:

  ```sql
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

  ```sql
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

* Adicionar uma chave primária ou interna no campo de nome &quot;id&quot;:

  ```sql
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

  ```sql
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

## Chave primária - Identificador{#primary-key}

No contexto de uma [implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), a chave primária das tabelas do Adobe Campaign é uma **ID exclusiva universal (UUID)** gerada automaticamente pelo mecanismo de banco de dados. O valor da chave é exclusivo em todo o banco de dados. O conteúdo da chave é gerado automaticamente ao inserir o registro.

**Exemplo**

No exemplo abaixo, declaramos uma chave incremental no schema de origem:

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

O schema gerado:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

Além da definição da chave, um campo numérico chamado &quot;id&quot; foi adicionado ao esquema estendido para conter a chave primária gerada automaticamente.

>[!CAUTION]
>
>Um registro com uma chave primária definida como 0 é inserido automaticamente ao criar a tabela. Esse registro é usado para evitar associações externas, que não são eficazes em tabelas de volume. Por padrão, todas as chaves estrangeiras são inicializadas com o valor 0 para que um resultado sempre possa ser retornado na associação quando o item de dados não for preenchido.
