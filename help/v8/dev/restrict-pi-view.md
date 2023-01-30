---
title: Restringir visualização de IP
description: Saiba como restringir a exibição de PI
feature: PI, Privacy
role: Developer
level: Intermediate, Experienced
exl-id: 1b833745-71d7-430d-ac7d-c830c78ea232
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# Restringir visualização de IP{#restricting-pii-view}

## Visão geral {#overview}

Se você precisar que os usuários de marketing acessem registros de dados, mas não quiser que eles vejam informações pessoais do destinatário (PI), como nome, sobrenome ou endereço de email, aplique as diretrizes abaixo para proteger a privacidade e impedir que os dados sejam utilizados incorretamente por operadores de campanha regulares.

## Implementação {#implementation}

Um atributo específico que pode ser aplicado a qualquer elemento ou atributo foi adicionado aos esquemas, complementa o atributo existente **[!UICONTROL visibleIf]**. Este atributo é: **[!UICONTROL accessibleIf]**. Ao conter uma expressão XTK relacionada ao contexto do usuário atual, ela pode aproveitar **[!UICONTROL HasNamedRight]** ou **[!UICONTROL $(login)]**, por exemplo.

Você pode encontrar uma amostra de uma extensão de schema de recipient que mostra este uso abaixo:

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

* **[!UICONTROL visibleIf]** : oculta os campos dos metadados, portanto, eles não podem ser acessados em uma visualização de esquema, ou seleção de coluna, ou em um construtor de expressões. Mas isso não oculta dados. Se o nome do campo for inserido manualmente em uma expressão, o valor será exibido.
* **[!UICONTROL accessibleIf]** : oculta os dados (substituindo-os por valores vazios) da consulta resultante. Se visibleIf estiver vazio, ele terá a mesma expressão que **[!UICONTROL accessibleIf]**.

Estas são as consequências do uso desse atributo no Campaign:

* Os dados não serão mostrados usando o editor de query genérico no console,
* Os dados não estarão visíveis nas listas de visão geral e de registro (console).
* Os dados se tornarão somente leitura na exibição detalhada.
* Os dados só serão utilizáveis em filtros (o que significa que, usando algumas estratégias de dicotomia, você ainda pode adivinhar valores).
* Qualquer expressão que é criada usando um campo restrito é restrita a: lower(@email) torna-se acessível como @email.
* Em um workflow, é possível adicionar a coluna restrita ao público alvo como uma coluna extra da transição, mas ela ainda fica inacessível aos usuários do Adobe Campaign.
* Ao armazenar a população direcionada em um grupo (lista), as características dos campos armazenados são as mesmas da fonte de dados.
* Por padrão, os dados não são acessíveis ao código JS.

## Recomendações {#recommendations}

Em cada delivery, os endereços de email são copiados para o **[!UICONTROL broadLog]** e **[!UICONTROL forecastLog]** tabelas: consequentemente, esses campos também precisam ser protegidos.

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
