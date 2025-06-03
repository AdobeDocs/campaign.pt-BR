---
title: Problemas conhecidos do Campaign v8
description: Problemas conhecidos na versão mais recente do Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 41e39e046ec77de8b5e657ba76645898ff1cd2d7
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---

# Problemas conhecidos{#known-issues}

Esta página lista problemas conhecidos identificados nas **versões mais recentes do Campaign v8**. Além disso, as limitações que acompanham o Campaign v8 estão listadas [nesta página](ac-guardrails.md).


>[!NOTE]
>
>A Adobe publica essa lista de problemas conhecidos a seu critério. Tem como base o número de relatórios de clientes, a gravidade e a disponibilidade temporária. Se um problema encontrado não estiver listado, talvez ele não tenha os critérios de publicação nesta página.

## Campaign v8.3.8{#8.3-issues}

### Alterar problema de atividade do Data Source {#issue-2}

#### Descrição{#issue-2-desc}

Ao inserir dados no banco de dados de nuvem do Snowflake com uma atividade Campaign **Query** e uma **Change Data Source**, o processo falhará quando um caractere de barra invertida estiver presente nos dados. A cadeia de caracteres de origem não tem escape e os dados não são processados corretamente no Snowflake.

Esse problema ocorre somente se o caractere de barra invertida estiver no final da cadeia de caracteres, por exemplo: `Barker\`.


#### Etapas de reprodução{#issue-2-repro}

1. Conecte-se ao Console do cliente e crie um workflow.
1. Adicione uma atividade **Query** e configure-a.
1. Selecione dados com as características descritas acima.
1. Adicione uma atividade **Change Data Source** e configure-a para selecionar o banco de dados na nuvem do Snowflake.
1. Execute o workflow e verifique os logs de workflow para ver o erro.


#### Mensagem de erro{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Solução alternativa{#issue-2-workaround}

A solução alternativa é excluir dados que contenham o caractere de barra invertida no final da string ou removê-los do arquivo de origem.


#### Referência interna{#issue-2-ref}

Referência: NEO-45549


### A atividade de carregamento de dados (arquivo) falhou ao fazer upload do arquivo no servidor {#issue-3}

#### Descrição{#issue-3-desc}

Ao carregar um arquivo no servidor do Campaign com uma atividade **Data loading (file)**, o processo para em 100%, mas nunca termina.

#### Etapas de reprodução{#issue-3-repro}

1. Conecte-se ao Console do cliente e crie um workflow.
1. Adicione uma atividade **Data loading (file)** e configure-a.
1. Selecione a opção **Carregar no servidor**.
1. Selecione o arquivo no computador local,
1. Clique em **Carregar**


#### Mensagem de erro{#issue-3-error}

O processo nunca termina.

#### Solução alternativa{#issue-3-workaround}

A solução alternativa é usar um Console do cliente mais antigo. Você poderá fazer upload do arquivo no servidor.

Como administrador do Campaign, você pode baixar o Console do Cliente do Campaign v8.3.1 na [Distribuição de software da Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target="_blank"}.

Saiba como acessar a Distribuição de Software da Adobe [nesta página](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=pt-BR){target="_blank"}.

Saiba como atualizar o Console do Cliente [nesta página](connect.md)

#### Referência interna{#issue-3-ref}

Referência: NEO-47269

