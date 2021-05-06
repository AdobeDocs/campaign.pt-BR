---
solution: Campaign Classic
product: campaign
title: Trabalhar com esquemas do Campaign
description: Introdução a esquemas
translation-type: tm+mt
source-git-commit: f1aed22d04bc0170b533bc088bb1a8e187b44dce
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 7%

---

# Trabalhar com schemas{#gs-ac-schemas}

A estrutura física e lógica dos dados transportados no aplicativo é descrita em XML. Ela obedece a uma gramática específica do Adobe Campaign, chamada de **schema**.

Um schema é um documento XML associado a uma tabela de banco de dados. Ele define a estrutura de dados e descreve a definição SQL da tabela:

* O nome da tabela
* Campos
* Links com outras tabelas

Ele também descreve a estrutura XML usada para armazenar dados:

* Elementos e atributos
* Hierarquia de elementos
* Tipos de elemento e atributo
* Valores padrão
* Rótulos, descrições e outras propriedades.

Os esquemas permitem definir uma entidade no banco de dados. Existe um schema para cada entidade.

A Adobe Campaign emprega os Esquemas de dados para:

* Defina como o objeto de dados no aplicativo é vinculado às tabelas de banco de dados subjacentes.
* Definir links entre os diferentes objetos de dados no aplicativo Campaign.
* Definir e descrever os campos individuais incluídos em cada objeto.

Para obter uma melhor compreensão das tabelas integradas do Campaign e sua interação, consulte [esta seção](datamodel.md).

>[!CAUTION]
>
>Alguns esquemas internos do Campaign têm um schema associado no banco de dados do Cloud. Esses esquemas são identificados pelo namespace **Xxl** e não devem ser modificados.

## Sintaxe de schemas {#syntax-of-schemas}

O elemento raiz do schema é **`<srcschema>`**. Ele contém os subelementos **`<element>`** e **`<attribute>`**.

O primeiro subelemento **`<element>`** coincide com a raiz da entidade.

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
>O elemento raiz da entidade tem o mesmo nome do schema.

![](assets/schema_and_entity.png)

As tags **`<element>`** definem os nomes dos elementos da entidade. **`<attribute>`** as tags do schema definem os nomes dos atributos nas  **`<element>`** tags às quais foram vinculadas.

## Identificação de um schema {#identification-of-a-schema}

Um schema de dados é identificado por seu nome e namespace.

Um namespace permite agrupar um conjunto de schemas por área de interesse. Por exemplo, o namespace **cus** é usado para configuração específica do cliente (**customers**).

>[!CAUTION]
>
>Como padrão, o nome do namespace deve ser conciso e deve conter somente caracteres autorizados de acordo com as regras de nomenclatura XML.
>
>Os identificadores não devem começar com caracteres numéricos.

## Namespaces reservados

Determinados namespaces são reservados para descrições das entidades do sistema necessárias para a operação do aplicativo Adobe Campaign. O namespace a seguir **não deve ser usado** para identificar um novo schema, em qualquer combinação de maiúsculas/minúsculas:

* **xxl**: reservado para esquemas de banco de dados do Cloud,
* **xtk**: reservado aos dados do sistema de plataforma,
* **nl**: reservado à utilização global do pedido,
* **nms**: reservado para deliveries (recipient, delivery, rastreamento etc.),
* **ncm**: reservado para gerenciamento de conteúdo,
* **temp**: reservado para schemas temporários.

A chave de identificação de um schema é uma cadeia de caracteres criada usando o namespace e o nome separados por dois pontos; por exemplo: **nms:recipient**.

## Criar ou estender esquemas do Campaign {#create-or-extend-schemas}

Para adicionar um campo ou outro elemento a um dos esquemas de dados principais no Campaign, como a tabela de recipients (nms:recipient), é necessário estender esse schema.

:bulb: Para obter mais informações, consulte [Estender um schema](extend-schema.md).

Para adicionar um tipo de dados totalmente novo que não existe no Adobe Campaign (uma tabela de contratos, por exemplo), é possível criar um schema personalizado diretamente.

:bulb: Para obter mais informações, consulte [Criar um novo schema](create-schema.md).

![](assets/schemaextension_1.png)


Depois de criar ou estender um schema para funcionar, a prática recomendada é definir seus elementos de conteúdo XML na mesma ordem em que aparecem abaixo.

## Enumerações {#enumerations}

As enumerações são definidas primeiro, antes do elemento principal do schema. Eles permitem exibir valores em uma lista para restringir as opções que o usuário tem para um determinado campo.

Exemplo:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

Ao definir campos, você pode usar essa enumeração da seguinte maneira:

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>Você também pode empregar enumerações gerenciadas pelo usuário (normalmente em **[!UICONTROL Administration]** > **[!UICONTROL Platform]** ) para especificar os valores para um determinado campo. Essas são enumerações globais efetivamente e uma melhor opção se a enumeração puder ser usada fora do schema específico em que você está trabalhando.

## Teclas {#keys}

Cada tabela deve ter pelo menos uma chave, e geralmente é automaticamente estabelecida no elemento principal do schema usando o atributo **@autouuid=true** definido como &quot;true&quot;.

A chave primária também pode ser definida usando o atributo **internal** .

Exemplo:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

Neste exemplo, em vez de permitir que o atributo **@autouuid** crie uma chave primária padrão chamada &quot;id&quot;, estamos especificando nossa própria chave primária &quot;householdId&quot;.

>[!CAUTION]
>
>Ao criar um novo schema ou durante uma extensão de schema, você precisa manter o mesmo valor de sequência da chave primária (@pkSequence) para todo o schema.

:bulb: Saiba mais sobre as chaves em [nesta seção](database-mapping.md#management-of-keys).

## Atributos (Campos) {#attributes--fields-}

Os atributos permitem definir os campos que compõem o objeto de dados. Você pode usar o botão **[!UICONTROL Insert]** na barra de ferramentas da edição do schema para soltar modelos de atributos vazios em seu XML, onde o cursor está. Saiba mais [nesta seção](create-schema.md).

![](assets/schemaextension_2.png)

A lista completa de atributos está disponível na seção `<attribute>` element na seção [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model). Estes são alguns dos atributos mais usados: **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label a13/>,**@length **,**@name **,**@notNull **,**@required **,**@ref 23/>, **@xml**, **@type**.****

:seta_upper_right: Para obter mais informações sobre cada atributo, consulte a Descrição do atributo em [documentação do Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

### Exemplos {#examples}

Exemplo de definição de um valor padrão:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Exemplo de uso de um atributo comum como modelo para um campo também marcado como obrigatório:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

Exemplo de um campo calculado que está oculto usando o atributo **@advanced**:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

Exemplo de um campo XML também armazenado em um campo SQL e que tem um atributo **@dataPolicy**.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>Embora a maioria dos atributos seja vinculada de acordo com uma cardinalidade 1-1 a um campo físico do banco de dados, esse não é o caso dos campos XML ou dos campos calculados.\
>Um campo XML é armazenado em um campo de memorando (&quot;mData&quot;) da tabela.\
>No entanto, um campo calculado é criado dinamicamente cada vez que um query é iniciado, portanto, ele só existe na camada do aplicativo.

## Links {#links}

Os links são alguns dos últimos elementos no elemento principal do schema. Eles definem como todos os diferentes esquemas em sua instância estão relacionados uns com os outros.

Os links são declarados no schema que contém a **chave estrangeira** da tabela à qual estão vinculados.

Existem três tipos de cardinalidade: 1-1, 1-N e N-N. É o tipo 1-N usado por padrão.

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

Aqui, &quot;xpath-dst&quot; corresponde à chave primária no schema de destino e &quot;xpath-src&quot; corresponde à chave estrangeira no schema de origem.

## Trilha de auditoria {#audit-trail}

Um elemento útil que pode ser incluído na parte inferior do esquema é um elemento de rastreamento (Trilha de auditoria).

Use o exemplo abaixo para incluir campos relacionados à data de criação, ao usuário que criou os dados, à data e ao autor da última modificação para todos os dados na tabela:

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## Atualização da estrutura do banco de dados {#updating-the-database-structure}

Depois que as alterações forem concluídas e salvas, todas as alterações que possam afetar a estrutura do SQL precisarão ser aplicadas ao banco de dados. Para fazer isso, use o assistente de atualização do banco de dados.

![](assets/schemaextension_3.png)

Para obter mais informações, consulte [esta seção](update-database-structure.md).

>[!NOTE]
>
>Quando as modificações não afetam a estrutura do banco de dados, basta gerar os schemas novamente. Para fazer isso, selecione os esquemas a serem atualizados, clique com o botão direito do mouse e escolha **[!UICONTROL Actions > Regenerate selected schemas...]** .

