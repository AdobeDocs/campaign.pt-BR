---
title: Criar um novo schema no Campaign
description: Saiba como criar um novo schema no Campaign
exl-id: 796af848-b537-4b8d-a601-fe0628a1fc83
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# Criar um novo schema{#create-new-schema}

Para editar, criar e configurar os esquemas, clique no botão **[!UICONTROL Administration > Configuration > Data schemas]** do console do cliente do Adobe Campaign.

>[!NOTE]
>
>Os esquemas de dados incorporados só podem ser excluídos por um administrador do console do Adobe Campaign.

![](assets/schema_navtree.png)

O **[!UICONTROL Edit]** mostra o conteúdo XML de um schema:

![](assets/schema_edition.png)

>[!NOTE]
>
>O controle de edição &quot;Name&quot; permite a inserção da chave do schema formada pelo nome e pelo namespace. Os atributos &quot;name&quot; e &quot;namespace&quot; do elemento raiz do schema são atualizados automaticamente na zona de edição XML do schema. Observe que alguns namespaces são somente internos. [Saiba mais](schemas.md#reserved-namespaces)

O **[!UICONTROL Preview]** A guia gera automaticamente o schema estendido:

![](assets/schema_edition2.png)

>[!NOTE]
>
>Quando o schema de origem é salvo, a geração do schema estendido é iniciada automaticamente.

Se você precisar verificar a estrutura completa de um schema, poderá usar a variável **[!UICONTROL Preview]** guia . Se o schema tiver sido estendido, você poderá visualizar todas as suas extensões. Como complemento, a variável **[!UICONTROL Documentation]** exibe todos os atributos e elementos do esquema e suas propriedades (Campo SQL, tipo/comprimento, rótulo, descrição). O **[!UICONTROL Documentation]** Essa guia se aplica somente aos schemas gerados.

## Caso de uso: criar uma tabela de contrato {#example--creating-a-contract-table}

No exemplo a seguir, você cria uma nova tabela para **contratos** no banco de dados. Essa tabela permite armazenar nomes e sobrenomes e endereços de email de titulares e cotitulares, para cada contrato.

Para fazer isso, é necessário criar o schema da tabela e atualizar a estrutura do banco de dados para gerar a tabela correspondente. As etapas detalhadas estão listadas abaixo.

1. Edite o **[!UICONTROL Administration > Configuration > Data schemas]** nó da árvore do Adobe Campaign e clique em **[!UICONTROL New]**.
1. Escolha a **[!UICONTROL Create a new table in the data template]** e clique em **[!UICONTROL Next]** .

   ![](assets/create_new_schema.png)

1. Especifique um nome para a tabela e um namespace.

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >Por padrão, os esquemas criados pelos usuários são armazenados no namespace &#39;cus&#39;. Para obter mais informações, consulte [Identificação de um schema](extend-schema.md#identification-of-a-schema).

1. Crie o conteúdo da tabela. Recomendamos o uso do assistente dedicado para garantir que nenhuma configuração esteja ausente. Para fazer isso, clique no botão **[!UICONTROL Insert]** e escolha o tipo de configuração a ser adicionada.

   ![](assets/create_new_content.png)

1. Defina as configurações da tabela de contrato.

   Como prática recomendada, crie a tabela no banco de dados do Cloud adicionando a variável `dataSource="nms:extAccount:ffda"` atributo. Esse atributo é adicionado por padrão ao criar uma nova tabela.

   ```
   <srcSchema created="YYYY-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" lastModified="YYYY-MM-DD HH:MM:SS.TZ"
           mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

   Adicione o tipo de enumeração de contrato.

   ```
   <srcSchema created="AA-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png" label="Contracts" labelSingular="Contract" AA-MM-DD HH:MM:SS.TZ"mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <enumeration basetype="byte" name="typeContract">
         <value label="Home" name="home" value="0"/>
         <value label="Car" name="car" value="1"/>
         <value label="Health" name="health" value="2"/>
         <value label="Pension fund" name="pension fund" value="2"/>
      </enumeration>
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

1. Salve o esquema e clique no botão **[!UICONTROL Structure]** para gerar a estrutura:

   ![](assets/configuration_structure.png)

1. Atualize a estrutura do banco de dados para criar a tabela à qual o schema será vinculado. Para obter mais informações, consulte [esta seção](update-database-structure.md).
