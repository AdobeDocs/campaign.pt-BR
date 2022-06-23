---
title: Problemas conhecidos do Campaign v8
description: Problemas conhecidos na versão mais recente do Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 2c9455a09d6b557d525b1af5da9374a1d59201d7
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 3%

---

# Problemas conhecidos{#known-issues}

Esta página lista os problemas conhecidos identificados na variável **Versão mais recente do Campaign v8**. Além disso, as limitações provenientes do Campaign v8 são listadas [nesta página](known-limitations.md).


>[!NOTE]
>
>O Adobe publica essa lista de problemas conhecidos a seu critério. Tem como base o número de relatórios do cliente, a gravidade e a disponibilidade alternativa. Se um problema que você está encontrando não estiver listado, ele pode não ter se encaixado nos critérios para publicação nesta página.

<!--
## Change Data Source activity issue #1 {#issue-1}

### Description{#issue-1-desc}

The **Change Data Source** activity is failing when transfering data from Campaign local database to Snowflake cloud database. When switching directions, the activity can generate issues.

### Reproduction steps{#issue-1-repro}

1. Connect to the client console and create a workflow.
1. Add a **Query** activity and a **Change Data Source** activity.
1. Define a query on the **email**, which is a string.
1. Run the workflow and right-click the transition to view the population: the email records are displayed replaced by `****`.
1. Check the workflow logs: the **Change Data Source** activity interprets these records as numeric values.

### Error message{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Workaround{#issue-1-workaround}

To have the data transfered from Snowflake cloud database to Campaign local database and back to Snowflake, you must use two different **Change Data Source** activities.

### Internal reference{#issue-1-ref}

Reference: NEO-45549 
-->


## Alterar problema de atividade da Fonte de Dados {#issue-2}

### Descrição{#issue-2-desc}

Ao injetar dados no banco de dados da nuvem do Snowflake com uma campanha **Query** e **Alterar fonte de dados** atividade , o processo falha quando um caractere de barra invertida está presente nos dados. A cadeia de caracteres de origem não é removida e os dados não são processados corretamente no Snowflake.

Esse problema só acontece se o caractere de barra invertida estiver no final da string, por exemplo: `Barker\`.


### Etapas de reprodução{#issue-2-repro}

1. Conecte-se ao console do cliente e crie um workflow.
1. Adicione um **Query** e configure-a.
1. Selecione os dados com as características descritas acima.
1. Adicione um **Alterar fonte de dados** e configure-a para selecionar o banco de dados da nuvem do Snowflake.
1. Execute o workflow e verifique os logs do workflow para ver o erro.


### Mensagem de erro{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### Solução alternativa{#issue-2-workaround}

A solução alternativa é excluir dados que contenham um caractere de barra invertida no final da string, ou removê-lo do arquivo de origem.

<!--
As a workaround, export the files with double quotes around the problematic values (like `Barker\`) and include a file format option `FIELD_OPTIONALLY_ENCLOSED_BY = '"'`.
-->

### Referência interna{#issue-2-ref}

Referência: NEO45549


## Falha na atividade de carregamento de dados (arquivo) Upload de arquivo no servidor {#issue-3}

### Descrição{#issue-3-desc}

Ao fazer upload de um arquivo no servidor do Campaign com um **Carregamento de dados (arquivo)** , o processo é interrompido em 100%, mas nunca termina.

### Etapas de reprodução{#issue-3-repro}

1. Conecte-se ao console do cliente e crie um workflow.
1. Adicione um **Carregamento de dados (arquivo)** e configure-a.
1. Selecione o **Fazer upload no servidor** opção.
1. Selecione o arquivo no computador local,
1. Clique em **Upload**


### Mensagem de erro{#issue-3-error}

O processo nunca termina.

### Solução alternativa{#issue-3-workaround}

A solução é usar um console de cliente mais antigo. Você poderá fazer upload do arquivo no servidor.

Como administrador, você pode baixar o console do cliente Campaign v8.3.1 em [Serviço de distribuição de Adobe](https://experience.adobe.com/downloads).

Saiba como acessar o Serviço de distribuição de Adobe [nesta página](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=pt-BR)

Saiba como atualizar seu console do cliente [nesta página](connect.md)

### Referência interna{#issue-3-ref}

Referência: NEO47269