---
title: Mecanismo de preparo da API do Campaign
description: Mecanismo de preparo da API do Campaign
feature: Configuration, API, FFDA
role: Developer
level: Intermediate
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
TQID: https://experienceleague.adobe.com/7lzQJvwlZtyuL-QAgSB1WGmiQhhQEZ66XRyiVFNqiZQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 2%

---

# Mecanismo de preparo da API do Campaign

No contexto de uma [implantação corporativa (FFDA)](enterprise-deployment.md), a geração de chamadas unitárias não é recomendada em relação a desempenhos (latência e simultaneidade). A menos que você esteja enviando um volume extremamente baixo, a operação em lote **deve** ser usada. Para melhorar o desempenho, as APIs de assimilação são redirecionadas para o banco de dados local.

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
