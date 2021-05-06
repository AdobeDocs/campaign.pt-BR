---
solution: Campaign Classic
product: campaign
title: Estender esquemas do Campaign
description: Saiba como estender schemas do Campaign
translation-type: tm+mt
source-git-commit: 779542ab70f0bf3812358884c698203bab98d1ce
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 6%

---

# Estender um esquema{#extend-schemas}

Este artigo descreve como configurar schemas de extensão para estender o modelo de dados conceituais do banco de dados do Adobe Campaign.

:bulb: Para obter uma melhor compreensão das tabelas integradas do Campaign e sua interação, consulte [esta página](datamodel.md).

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

Determinados namespaces são reservados para descrições das entidades do sistema necessárias para a operação do aplicativo Adobe Campaign:

* **xxl**: sobre schemas do banco de dados do Cloud,
* **xtk**: no que diz respeito aos dados do sistema da plataforma,
* **nl**: sobre a utilização global do pedido,
* **nms**: relativo ao delivery (recipient, delivery, rastreamento etc.),
* **ncm**: em matéria de gestão de conteúdos,
* **temp**: reservado para schemas temporários.

A chave de identificação de um schema é uma cadeia de caracteres criada usando o namespace e o nome separados por dois pontos; por exemplo: **nms:recipient**.
