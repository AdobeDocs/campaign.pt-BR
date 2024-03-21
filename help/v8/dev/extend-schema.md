---
title: Estender schemas do Campaign
description: Saiba como estender esquemas do Campaign
feature: Schema Extension, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: e4dcb228-0683-437a-88cd-bd7ed33da921
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Estender um esquema{#extend-schemas}

Como usuário técnico, você pode personalizar o modelo de dados do Campaign para atender às necessidades da sua implementação: adicionar elementos a um esquema existente, modificar um elemento em um esquema ou excluir elementos.

As principais etapas para personalizar o modelo de dados do Campaign são:

1. Criar um esquema de extensão
1. Atualizar banco de dados do Campaign
1. Adaptar o formulário de entrada

>[!CAUTION]
>O esquema incorporado não deve ser modificado diretamente. Se precisar adaptar um esquema incorporado, é necessário estendê-lo.

Para obter uma melhor compreensão das tabelas integradas do Campaign e sua interação, consulte [esta página](datamodel.md). Consulte também recomendações ao criar um novo esquema no [esta página](create-schema.md).

Para estender um schema, siga as etapas abaixo:

1. Navegue até a **[!UICONTROL Administration > Configuration > Data schemas]** no Explorer.
1. Clique em **Novo** e selecione **[!UICONTROL Extend the data in a table using an extension schema]**.

   ![](assets/extend-schema-option.png)

1. Identifique o esquema incorporado que será estendido e selecione-o.

   ![](assets/extend-schema-select.png)

   Por convenção, nomeie o esquema de extensão como o esquema incorporado e use um namespace personalizado.  Observe que alguns namespaces são somente internos. [Saiba mais](schemas.md#reserved-namespaces)

   ![](assets/extend-schema-validate.png)

1. Uma vez no editor de esquema, adicione os elementos necessários usando o menu contextual e salve.

   ![](assets/extend-schema-edit.png)

   No exemplo abaixo, adicionamos a variável **MembershipYear** coloque um limite de comprimento para o sobrenome (esse limite substituirá o padrão) e remova a data de nascimento do esquema incorporado.

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
       <attribute label="Member since" name="MembershipYear" type="long"/>
       <attribute length="50" name="lastName"/>
       <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```

1. Desconecte e reconecte o Campaign para verificar a atualização da estrutura de esquema no **[!UICONTROL Structure]** guia.

   ![](assets/extend-schema-structure.png)

1. Atualize a estrutura do banco de dados para aplicar as alterações. [Saiba mais](update-database-structure.md)

1. Depois que as alterações forem implementadas no banco de dados, você poderá adaptar o formulário de entrada do recipient para tornar suas alterações visíveis. [Saiba mais](forms.md)
