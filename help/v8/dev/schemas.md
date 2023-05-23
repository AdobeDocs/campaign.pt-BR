---
title: Trabalhar com esquemas do Campaign
description: Introdução a esquemas
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '1262'
ht-degree: 8%

---

# Trabalhar com esquemas{#gs-ac-schemas}

A estrutura física e lógica dos dados transportados no aplicativo é descrita em XML. Ela obedece a uma gramática específica do Adobe Campaign, chamada de **schema**.

Um esquema é um documento XML associado a uma tabela de banco de dados. Ele define a estrutura de dados e descreve a definição SQL da tabela:

* O nome da tabela
* Campos
* Links com outras tabelas

Também descreve a estrutura XML usada para armazenar dados:

* Elementos e atributos
* Hierarquia de elementos
* Tipos de elemento e atributo
* Valores padrão
* Rótulos, descrições e outras propriedades.

Os esquemas permitem definir uma entidade no banco de dados. Há um esquema para cada entidade.

A Adobe Campaign emprega esquemas de dados para:

* Defina como os objetos de dados no aplicativo são vinculados às tabelas de banco de dados subjacentes.
* Definir links entre os diferentes objetos de dados no aplicativo Campaign.
* Definir e descrever os campos individuais incluídos em cada objeto.

Para obter uma melhor compreensão das tabelas integradas do Campaign e sua interação, consulte [nesta seção](datamodel.md).

>[!CAUTION]
>
>Alguns esquemas integrados do Campaign têm um esquema associado no banco de dados da nuvem. Esses esquemas são identificados pela variável **Xxl** e não devem ser modificados ou estendidos.

## Sintaxe de schemas {#syntax-of-schemas}

O elemento raiz do esquema é **`<srcschema>`**. Contém a **`<element>`** e **`<attribute>`** subelementos.

O primeiro **`<element>`** o subelemento coincide com a raiz da entidade.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>O elemento raiz da entidade tem o mesmo nome que o schema.

![](assets/schema_and_entity.png)

A variável **`<element>`** as tags definem os nomes dos elementos da entidade. **`<attribute>`** As tags do esquema definem os nomes dos atributos na variável **`<element>`** tags às quais elas foram vinculadas.

## Identificação de um esquema {#identification-of-a-schema}

Um schema de dados é identificado por seu nome e seu namespace.

Um namespace permite agrupar um conjunto de esquemas por área de interesse. Por exemplo, a variável **cus** O namespace é usado para configuração específica do cliente (**clientes**).

>[!CAUTION]
>
>Como padrão, o nome do namespace deve ser conciso e conter apenas caracteres autorizados, de acordo com as regras de nomenclatura XML.
>
>Os identificadores não devem começar com caracteres numéricos.

## Namespaces reservados {#reserved-namespaces}

Determinados namespaces são reservados para descrições das entidades do sistema necessárias para a operação do aplicativo do Adobe Campaign. O namespace a seguir **não deve ser usado** para identificar um novo schema, em qualquer combinação de maiúsculas/minúsculas:

* **xxl**: reservado para schemas de banco de dados na nuvem
* **xtk**: reservado para dados do sistema da plataforma
* **nl**: reservado para o uso geral do aplicativo
* **nms**: reservado para deliveries (recipient, delivery, rastreamento etc.)
* **ncm**: reservado para gerenciamento de conteúdo
* **temp**: reservado para schemas temporários
* **crm**: reservado para integração dos conectores CRM

A chave de identificação de um esquema é uma cadeia de caracteres criada usando o namespace e o nome separados por dois pontos, por exemplo: **nms:recipient**.

## Criar ou estender esquemas do Campaign {#create-or-extend-schemas}

Para adicionar um campo ou outro elemento a um dos esquemas de dados principais no Campaign, como a tabela de recipients (nms:recipient), é necessário estender esse esquema.

![](../assets/do-not-localize/glass.png) Para obter mais informações, consulte [Estender um esquema](extend-schema.md).

Para adicionar um tipo de dados totalmente novo que não existe no Adobe Campaign (uma tabela de contratos, por exemplo), você pode criar um esquema personalizado diretamente.

![](../assets/do-not-localize/glass.png) Para obter mais informações, consulte [Criar um novo esquema](create-schema.md).

![](assets/schemaextension_1.png)


Depois de criar ou estender um esquema para trabalhar, a prática recomendada é definir seus elementos de conteúdo XML na mesma ordem em que aparecem abaixo.

## Enumerações {#enumerations}

As enumerações são definidas primeiro, antes do elemento principal do esquema. Eles permitem exibir valores em uma lista para restringir as opções que o usuário tem para um determinado campo.

Exemplo:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

Ao definir campos, é possível usar essa enumeração da seguinte maneira:

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>Você também pode empregar enumerações gerenciadas pelo usuário (geralmente em **[!UICONTROL Administration]** > **[!UICONTROL Platform]** ) para especificar os valores de um determinado campo. Elas são enumerações globais efetivamente e uma opção melhor se sua enumeração puder ser usada fora do esquema específico em que você está trabalhando.

<!--
## Index {#index} 

In the context of a [FDA Snowflake deployment](../architecture/fda-deployment.md), you need to declare indexes. Indexes are the first elements declared in the main element of the schema. 

They can be unique or not, and reference one or more fields.

Examples:

```
<dbindex name="email" unique="true">
  <keyfield xpath="@email"/>
</dbindex>
```

```
<dbindex name="lastNameAndZip">
  <keyfield xpath="@lastName"/>
  <keyfield xpath="location/@zipCode"/>
</dbindex>
```

The **xpath** attribute points to the field in your schema that you wish to index.

>[!IMPORTANT]
>
>It is important to remember that the SQL query read performance gains provided by indexes also come with a performance hit on writing records. The indexes should therefore be used with precaution.

For more on indexes, refer to the [Indexed fields](database-mapping.md#indexed-fields) section.

-->

## Chaves {#keys}

Cada tabela deve ter pelo menos uma chave e, com frequência, é estabelecida automaticamente no elemento principal do esquema usando o **autopk** atributo definido como **true**.

Além disso, no contexto de uma [Implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), use o **@autouuid** e defina-o como **true**.

A chave primária também pode ser definida usando o **interno** atributo.

Exemplo:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

Neste exemplo, em vez de permitir que **@autopk** ou o **@autouuid** atributo criar uma chave primária padrão chamada &quot;id&quot; estamos especificando nossa própria chave primária &quot;householdId&quot;.

>[!CAUTION]
>
>Ao criar um novo schema ou durante uma extensão de schema, você precisa manter o mesmo valor de sequência da chave primária (@pkSequence) para todo o schema.

![](../assets/do-not-localize/glass.png) Saiba mais sobre chaves em [nesta seção](database-mapping.md#management-of-keys).

## Atributos (Campos) {#attributes--fields-}

Os atributos permitem definir os campos que compõem seu objeto de dados. Você pode usar o **[!UICONTROL Insert]** botão na barra de ferramentas da edição do esquema para soltar modelos de atributos vazios no XML onde o cursor está. Saiba mais [nesta seção](create-schema.md).

![](assets/schemaextension_2.png)

A lista completa de atributos está disponível no `<attribute>` seção de elemento em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html#content-model). Estes são alguns dos atributos usados com mais frequência: **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label**, **@length**, **@name**, **@notNull**, **@required**, **@ref**, **@xml**, **@type**.

![](../assets/do-not-localize/book.png) Para obter mais informações sobre cada atributo, consulte a Descrição do atributo em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html#configuring-campaign-classic).

### Exemplos {#examples}

Exemplo de definição de um valor padrão:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Exemplo de uso de um atributo comum como modelo para um campo também marcado como obrigatório:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

Exemplo de um campo calculado que está oculto usando o **@advanced** atributo:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

Exemplo de um campo XML também armazenado em um campo SQL e que tem um **@dataPolicy** atributo.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>Embora a maioria dos atributos seja vinculada de acordo com uma cardinalidade 1-1 a um campo físico do banco de dados, esse não é o caso para os campos XML ou os campos calculados.\
>Um campo XML é armazenado em um campo de memorando (&quot;mData&quot;) da tabela.\
>No entanto, um campo calculado é criado dinamicamente sempre que uma consulta é iniciada, portanto, ele só existe na camada do aplicativo.

## Links {#links}

Os links são alguns dos últimos elementos no elemento principal do esquema. Elas definem como todos os diferentes esquemas na sua instância se relacionam entre si.

Os links são declarados no esquema que contém a variável **chave estrangeira** da tabela à qual está vinculado.

Há três tipos de cardinalidade: 1-1, 1-N e N-N. É o tipo 1-N usado por padrão.

### Exemplos {#examples-1}

Um exemplo de um link 1-N entre a tabela do recipient (schema pronto para uso) e uma tabela de transações personalizadas:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

Um exemplo de um link 1-1 entre um schema personalizado &quot;Car&quot; (no namespace &quot;cus&quot;) e a tabela de recipients:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

Exemplo de uma associação externa entre a tabela de recipients e uma tabela de endereços com base no endereço de email e não em uma chave primária:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

Aqui, &quot;xpath-dst&quot; corresponde à chave primária no esquema de destino e &quot;xpath-src&quot; corresponde à chave externa no esquema de origem.

## Trilha de auditoria {#audit-trail}

Um elemento útil que você pode querer incluir na parte inferior do esquema é um elemento de rastreamento (Trilha de auditoria).

Use o exemplo abaixo para incluir campos relacionados à data de criação, ao usuário que criou os dados, à data e ao autor da última modificação para todos os dados na tabela:

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## Atualização da estrutura do banco de dados {#updating-the-database-structure}

Depois que as alterações forem concluídas e salvas, qualquer alteração que possa afetar a estrutura SQL precisará ser aplicada ao banco de dados. Para fazer isso, use o assistente de atualização de banco de dados.

![](assets/schemaextension_3.png)

Para obter mais informações, consulte [esta seção](update-database-structure.md).

>[!NOTE]
>
>Quando as modificações não afetam a estrutura do banco de dados, você só precisa gerar novamente os esquemas. Para fazer isso, selecione os esquemas a serem atualizados, clique com o botão direito do mouse e escolha **[!UICONTROL Actions > Regenerate selected schemas...]**.
