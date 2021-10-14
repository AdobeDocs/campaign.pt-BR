---
title: Filtrar esquemas de campanha
description: Saiba como filtrar esquemas do Campaign
source-git-commit: e0faeda87d5b84309524a72d9f021c381ac4619e
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Schemas de filtro{#filter-schemas}

## Filtros do sistema {#system-filters}

Você pode filtrar o acesso ao esquema para usuários específicos, dependendo de suas permissões. Os filtros do sistema permitem gerenciar as permissões de leitura e gravação de entidades detalhadas em schemas, usando os parâmetros **readAccess** e **writeAccess** .

>[!NOTE]
>
>Esta restrição aplica-se apenas a utilizadores não técnicos: um usuário técnico, com permissões relacionadas ou usando um workflow, poderá recuperar e atualizar dados.

* **readAccess**: fornece acesso somente leitura aos dados do esquema.

   **Aviso**  - Todas as tabelas vinculadas devem ser definidas com a mesma restrição. Essa configuração pode afetar o desempenho.

* **writeAccess**: fornece acesso de gravação aos dados do esquema.

Esses filtros são inseridos no nível principal **element** dos schemas e, como mostrado nos exemplos a seguir, podem ser formados para restringir o acesso.

* Restringir permissões de GRAVAÇÃO

   Aqui, o filtro é usado para não permitir permissões de GRAVAÇÃO no schema para operadores sem a permissão ADMINISTRATION. Isso significa que somente os administradores terão permissões de gravação em entidades descritas por esse esquema.

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* Restringir permissões de LEITURA e GRAVAÇÃO:

   Aqui, o filtro é usado para não permitir permissões de LEITURA e GRAVAÇÃO no schema para todos os operadores. Somente a conta **interna**, representada pela expressão &quot;$(loginId)!=0&quot;, tem essas permissões.

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   Os possíveis valores de atributo **expr** usados para definir a condição são TRUE ou FALSE.

>[!NOTE]
>
>Se nenhum filtro for especificado, todos os operadores terão permissões de leitura e gravação no schema.

## Schemas integrados do Protect

Por padrão, os esquemas internos só podem ser acessados com permissões de GRAVAÇÃO para operadores com direitos de ADMINISTRATION:

* ncm:publicação
* nl:monitoramento
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
>As permissões READ e WRITE para o schema **xtk:sessionInfo** só podem ser acessadas pela conta interna de uma instância do Adobe Campaign.

## Modificar filtros do sistema de esquemas internos

Os esquemas internos são protegidos para evitar problemas de compatibilidade com versões mais antigas. O Adobe recomenda não modificar os parâmetros de esquema padrão para garantir a segurança ideal.

No entanto, em contextos específicos, pode ser necessário modificar os filtros do sistema dos schemas incorporados. Para fazer isso, siga as etapas abaixo:

1. Crie uma extensão para o schema incorporado ou abra uma extensão existente.
1. Adicione um elemento filho **`<sysfilter name="<filter name>" _operation="delete"/>`** no elemento principal para ignorar o filtro sob o mesmo no schema incorporado.
1. Você pode adicionar um novo filtro, conforme detalhado na seção [Filtros do sistema](#system-filters).
