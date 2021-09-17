---
title: Mecanismo de preparo da API do Campaign
description: Mecanismo de preparo da API do Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---

# Mecanismo de preparo da API do Campaign

Com o banco de dados do Campaign Cloud, chamadas unitárias de explosão não são recomendadas em relação a desempenhos (latência e simultaneidade). A operação de lote é sempre preferida. Para melhorar o desempenho, as APIs de assimilação são redirecionadas para o banco de dados local.

O recurso de preparo da campanha é ativado por padrão em alguns schemas incorporados. Também podemos ativá-lo em qualquer schema personalizado. Mecanismo de armazenamento temporário em poucas palavras:

* A estrutura do schema de dados é duplicada na tabela de preparo local
* Novas APIs dedicadas à assimilação de dados fluem diretamente na tabela de preparo local. [Saiba mais](new-apis.md)
* Um workflow agendado dispara a cada hora e sincroniza dados de volta ao banco de dados da nuvem. [Saiba mais](../config/replication.md)

Alguns esquemas internos são Preparados por padrão, como nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

As APIs do Campaign Classic v7 ainda estão disponíveis, mas não podem se beneficiar desse novo mecanismo de preparo: As chamadas de API fluem diretamente para o banco de dados do Cloud. O Adobe recomenda usar o novo mecanismo de preparo o máximo possível para reduzir a pressão e a latência gerais no banco de dados do Campaign Cloud.

>[!CAUTION]
>
>* Com esse novo mecanismo, a sincronização de dados para exclusão de canal, assinaturas, unsubscriptions ou registro móvel agora é **assíncrona**.
>
>* O armazenamento temporário só se aplica a esquemas armazenados no banco de dados da nuvem. Não ative o armazenamento temporário em schemas replicados. Não ative o armazenamento temporário em esquemas locais. Não ativar Preparo em um esquema Preparado
>


## Etapas de implementação{#implement-staging}

Para implementar o mecanismo de preparo do Campaign em uma tabela específica, siga as etapas abaixo:

1. Crie uma amostra de esquema personalizado no banco de dados da Campaign Cloud. Nenhuma preparação habilitada nesta etapa.

   ```
   <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

   ?? Saiba mais sobre a criação de esquema personalizado em [this page](create-schema.md).

1. Salve e atualize a estrutura do banco de dados.  [Saiba mais](update-database-structure.md)

1. Ative o mecanismo de preparo na definição do schema adicionando o parâmetro **autoStg=&quot;true&quot;**.

   ```
   <srcSchema _cs="Sample Table (dem)" "YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autoStg="true" autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

1. Salve a modificação. Um novo schema de preparo está disponível, que é uma cópia local do schema inicial.

   ![](assets/staging-mechanism.png)

1. Atualize a estrutura do banco de dados. A tabela de preparo será criada no banco de dados local do Campaign.
