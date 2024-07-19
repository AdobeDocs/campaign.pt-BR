---
title: Mecanismo de preparo da API do Campaign
description: Mecanismo de preparo da API do Campaign
feature: Configuration, API, FFDA
role: Developer
level: Intermediate
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Mecanismo de preparo da API do Campaign

No contexto de uma [implantação corporativa (FFDA)](enterprise-deployment.md), a geração de chamadas unitárias não é recomendada em relação a desempenhos (latência e simultaneidade). A operação em lote é sempre preferível. Para melhorar o desempenho, as APIs de assimilação são redirecionadas para o banco de dados local.

O recurso de preparo do Campaign está habilitado por padrão em alguns esquemas integrados. Também podemos ativá-la em qualquer esquema personalizado. Mecanismo de preparo em poucas palavras:

* A estrutura do esquema de dados é duplicada na tabela de preparo local
* Novas APIs dedicadas para assimilação de dados fluem diretamente para a tabela de preparo local. [Saiba mais](new-apis.md)
* Um fluxo de trabalho agendado é acionado a cada hora e sincroniza os dados de volta ao banco de dados da nuvem. [Saiba mais](replication.md)

Alguns esquemas internos são Preparados por padrão, como nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

As APIs do Campaign Classic v7 ainda estão disponíveis, mas não podem se beneficiar desse novo mecanismo de preparo: as chamadas de API fluem para diretamente para o banco de dados da nuvem. A Adobe recomenda usar o novo mecanismo de preparo o máximo possível para reduzir a pressão e a latência gerais no banco de dados da nuvem do Campaign.

>[!CAUTION]
>
>* Com esse novo mecanismo, a sincronização de dados para recusa de canal, assinaturas, cancelamento de assinatura ou registro móvel agora é **assíncrona**.
>
>* O preparo se aplica somente a esquemas armazenados no banco de dados da nuvem. Não ative o preparo em esquemas replicados. Não ative a Preparação em esquemas locais. Não ativar a Preparação em um esquema em etapas
>

## Etapas de implementação {#implement-staging}

Para implementar o mecanismo de preparo do Campaign em uma tabela específica, siga as etapas abaixo:

1. Crie um exemplo de esquema personalizado no banco de dados da Campaign Cloud. Nenhum preparo ativado nesta etapa.

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

   Saiba mais sobre a criação de esquema personalizado em [esta página](../dev/create-schema.md).

1. Salvar e atualizar a estrutura do banco de dados.  [Saiba mais](../dev/update-database-structure.md)

1. Habilite o mecanismo de preparo na definição do esquema adicionando o parâmetro **autoStg=&quot;true&quot;**.

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

1. Salve a modificação. Um novo esquema de preparo está disponível, que é uma cópia local do esquema inicial.

   ![](assets/staging-mechanism.png)

1. Atualize a estrutura do banco de dados. A tabela de preparo será criada no banco de dados local do Campaign.
