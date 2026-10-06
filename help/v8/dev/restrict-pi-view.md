---
title: Restringir visualização de IP
description: Saiba como restringir a visualização de IP
feature: PI, Privacy, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: 1b833745-71d7-430d-ac7d-c830c78ea232
TQID: 'https://experienceleague.adobe.com/MRPX97V84a4r1eVIIyrU2Z7ZwiNkn-RHMZGQG3YV9ec'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
    internal-label: Schemas
  - id: a7760dfc-5c44-4d77-bb68-c50b1e265c93
    internal-label: Security and privacy
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
    internal-label: PI
  - id: ac9c0a9c-8a76-4419-bd64-9c34c5782666
    internal-label: Privacy
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%
---
# Restringir visualização de IP{#restricting-pii-view}

## Visão geral {#overview}

Se você precisar que os usuários de marketing acessem registros de dados, mas não quiser que eles vejam as Informações pessoais (PI) do recipient, como nome, sobrenome ou endereço de email, aplique as diretrizes abaixo para proteger a privacidade e impedir que os dados sejam usados indevidamente pelos operadores de campanha comuns.

## Implementação {#implementation}

Um atributo específico que pode ser aplicado a qualquer elemento ou atributo foi adicionado aos esquemas, ele complementa o atributo existente **[!UICONTROL visibleIf]**. Este atributo é: **[!UICONTROL accessibleIf]**. Ao conter uma expressão XTK relacionada ao contexto de usuário atual, ela pode aproveitar **[!UICONTROL HasNamedRight]** ou **[!UICONTROL $(login)]**, por exemplo.

Você pode encontrar abaixo um exemplo de extensão de schema de recipient que mostra esse uso:

```
<srcSchema desc="Recipient table (profiles" entitySchema="xtk:srcSchema" extendedSchema="xxl:nmsRecipientXl"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Recipient table (profiles" img="xxl:recipient.png" label="Recipients"
           labelSingular="Recipient" name="recipient">
    <attribute name="firstName" accessibleIf="$(login)=='admin'"/>
    <attribute name="lastName" visibleIf="$(login)=='admin'"/>
    <attribute name="email" accessibleIf="$(login)=='admin'"/>
  </element>
</srcSchema>
```

As principais propriedades são:

* **[!UICONTROL visibleIf]**: oculta os campos dos metadados, portanto, eles não podem ser acessados em uma exibição de esquema, seleção de coluna ou um [Construtor de expressões](../../v8/start/filter-conditions.md#list-of-functions). Mas isso não oculta dados. Se o nome do campo for inserido manualmente em uma expressão, o valor será exibido.
* **[!UICONTROL accessibleIf]**: oculta os dados (substituindo-os por valores vazios) da consulta resultante. Se visibleIf estiver vazio, ele terá a mesma expressão que **[!UICONTROL accessibleIf]**.

Estas são as consequências do uso desse atributo no Campaign:

* Os dados não serão exibidos usando o editor de query genérico no console,
* Os dados não estarão visíveis nas listas de visão geral e de registros (console).
* Os dados se tornarão somente leitura na exibição detalhada.
* Os dados só serão utilizáveis dentro de filtros (o que significa que, usando algumas estratégias de dicotomia, ainda é possível adivinhar valores).
* Qualquer expressão criada usando um campo restrito se torna restrita a: lower(@email) se torna tão acessível quanto @email.
* Em um workflow, é possível adicionar a coluna restrita à população direcionada como uma coluna extra da transição, mas ela ainda estará inacessível aos usuários do Adobe Campaign.
* Ao armazenar a população direcionada em um grupo (lista), as características dos campos armazenados são as mesmas da fonte de dados.
* Os dados não estão acessíveis ao código JS por padrão.

>[!IMPORTANT]
>
>O uso do atributo **accessibleIf** em parâmetros críticos (como aqueles em chaves compostas) pode resultar em erros para usuários que não têm permissão para ler os dados devido a dados ocultos. Isso pode levar a falhas de consulta ou comportamento inesperado. Garantir que os parâmetros essenciais estejam acessíveis para evitar interrupções.

## Recomendações {#recommendations}

Em cada delivery, endereços de email são copiados nas tabelas **[!UICONTROL broadLog]** e **[!UICONTROL forecastLog]**: como consequência, esses campos também precisam ser protegidos.

Abaixo está uma amostra da extensão da tabela de log para implementar isso:

```
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:broadLogRcp" img="nms:broadLog.png"
           label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:broadLog.png" label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema desc="Delivery messages being prepared." entitySchema="xtk:srcSchema"
           extendedSchema="nms:tmpBroadcast" img="" label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Delivery messages being prepared." label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:excludeLogRcp" img="nms:excludeLog.png"
           label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:excludeLog.png" label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
```

>[!CAUTION]
>
>Essa restrição se aplica somente a usuários não técnicos e não isola dados: um usuário técnico, com permissões relacionadas, pode recuperar dados.
