---
title: Filtrar esquemas de campanha
description: Saiba como filtrar esquemas do Campaign
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 2%

---

# Esquemas de filtro{#filter-schemas}

## Filtros do sistema {#system-filters}

Você pode filtrar o acesso ao esquema para usuários específicos, dependendo de suas permissões. Os filtros de sistema permitem gerenciar as permissões de leitura e gravação de entidades detalhadas em esquemas, usando os parâmetros **readAccess** e **writeAccess**.

>[!NOTE]
>
>Essa restrição se aplica somente a usuários não técnicos: um usuário técnico, com permissões relacionadas ou usando um fluxo de trabalho, poderá recuperar e atualizar dados.

* **readAccess**: fornece acesso somente leitura a dados de esquema.

  **Aviso** - Todas as tabelas vinculadas devem ser definidas com a mesma restrição. Essa configuração pode afetar o desempenho.

* **writeAccess**: fornece acesso de gravação a dados de esquema.

Esses filtros são inseridos no nível **element** principal dos esquemas e, como mostrado nos exemplos a seguir, podem ser formados para restringir o acesso.

* Restringir permissões de GRAVAÇÃO

  Aqui, o filtro é usado para não permitir permissões WRITE no schema para operadores sem a permissão ADMINISTRATION. Isso significa que somente administradores terão permissões de gravação nas entidades descritas por esse esquema.

  ```
  <sysFilter name="writeAccess">      
   <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
  </sysFilter>
  ```

* Restringir permissões de LEITURA e GRAVAÇÃO:

  Aqui, o filtro é usado para não permitir permissões de LEITURA e GRAVAÇÃO no esquema para todos os operadores. Somente a conta **interna**, representada pela expressão &quot;$(loginId)!=0&quot;, tem essas permissões.

  ```
  <sysFilter name="readAccess"> 
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  
  <sysFilter name="writeAccess">  
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  ```

  Possíveis valores de atributo **expr** usados para definir a condição são TRUE ou FALSE.

>[!NOTE]
>
>Se nenhum filtro for especificado, todos os operadores terão permissões de leitura e gravação no esquema.

## Esquemas integrados do Protect

Por padrão, os esquemas integrados só podem ser acessados com permissões WRITE para operadores com direitos ADMINISTRATION:

* ncm:publicação
* nl:monitoring
* nms:calendar
* xtk:builder
* xtk:conexões
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusion
* xtk:image
* xtk:javascript
* xtk:jssp
* xtk:jst
* xtk:navtree
* xtk:operatorGroup
* xtk:package
* xtk:queryDef
* xtk:resourceMenu
* xtk:rights
* xtk:schema
* xtk:scriptContext
* xtk:specFile
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk:strings
* xtk:xslt

>[!CAUTION]
>
>As permissões de LEITURA e GRAVAÇÃO para o esquema **xtk:sessionInfo** só podem ser acessadas pela conta interna de uma instância do Adobe Campaign.

## Modificar filtros de sistema de esquemas internos

Os esquemas integrados estão protegidos para evitar problemas de compatibilidade com versões mais antigas. O Adobe recomenda que você não modifique os parâmetros de esquema padrão para garantir a segurança ideal.

No entanto, em contextos específicos, talvez seja necessário modificar os filtros de sistema dos esquemas integrados. Para fazer isso, siga as etapas abaixo:

1. Crie uma extensão para o esquema incorporado ou abra uma extensão existente.
1. Adicione um elemento filho **`<sysfilter name="<filter name>" _operation="delete"/>`** no elemento principal para ignorar o filtro no mesmo esquema interno.
1. Você pode adicionar um novo filtro, conforme detalhado na seção [Filtros de sistema](#system-filters).
