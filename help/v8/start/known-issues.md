---
title: Problemas conhecidos do Campaign v8
description: Problemas conhecidos na versão mais recente do Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: e82ae1158926fb6335380626158089c6394377a1
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 3%

---

# Problemas conhecidos{#known-issues}

Esta página lista os problemas conhecidos identificados na variável **Versão mais recente do Campaign v8**. Além disso, as limitações provenientes do Campaign v8 são listadas [nesta página](known-limitations.md).


>[!NOTE]
>
>O Adobe publica essa lista de problemas conhecidos a seu critério. Tem como base o número de relatórios do cliente, a gravidade e a disponibilidade alternativa. Se um problema que você está encontrando não estiver listado, ele pode não ter se encaixado nos critérios para publicação nesta página.

## Alterar problema de atividade da Fonte de Dados {#issue-1}

### Descrição{#issue-1-desc}

O **Alterar fonte de dados** A atividade está falhando ao transferir dados do banco de dados local do Campaign para o banco de dados da nuvem do Snowflake. Ao alternar direções, a atividade pode gerar problemas.

### Etapas de reprodução{#issue-1-repro}

1. Conecte-se ao console do cliente e crie um workflow.
1. Adicione um **Query** e uma **Alterar fonte de dados** atividade .
1. Defina uma query na **email**, que é uma string.
1. Execute o workflow e clique com o botão direito do mouse na transição para visualizar o público: os registros de email são exibidos e substituídos por `****`.
1. Verifique os logs do workflow: o **Alterar fonte de dados** A atividade interpreta esses registros como valores numéricos.

### Mensagem de erro{#issue-1-error}

```
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Solução alternativa{#issue-1-workaround}

Para que os dados sejam transferidos do banco de dados da nuvem do Snowflake para o banco de dados local do Campaign e de volta para o Snowflake, você deve usar dois **Alterar fonte de dados** atividades.

### Referência interna{#issue-1-ref}

Referência: NEO45549



## Falha na atividade de carregamento de dados (arquivo) devido a uma barra invertida {#issue-2}

### Descrição{#issue-2-desc}

Ao inserir dados no banco de dados da nuvem do Snowflake com uma atividade de carregamento do Campaign, o processo pode falhar devido a um caractere de barra invertida estar presente no arquivo de origem. A sequência de caracteres não é removida e os dados não são processados corretamente no Snowflake.

Esse problema só acontece se a barra invertida estiver no final da string, por exemplo: &quot;Barker\&quot;.


### Etapas de reprodução{#issue-2-repro}

1. Conecte-se ao console do cliente e crie um workflow.
1. Adicione um **Carregamento de dados (arquivo)** e configure-a.
1. Selecione um arquivo local com as características descritas acima.
1. Execute o workflow e verifique os logs do workflow para ver o erro.


### Mensagem de erro{#issue-2-error}

```
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### Solução alternativa{#issue-2-workaround}

Como solução alternativa, exporte os arquivos com aspas duplas em torno dos valores como &quot;Barker\&quot; e inclua uma opção de formato de arquivo FIELD_OPTIONALLY_ENCLOSED_BY = &#39;&quot;&#39;

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

nenhuma

### Referência interna{#issue-3-ref}

Referência: NEO47269