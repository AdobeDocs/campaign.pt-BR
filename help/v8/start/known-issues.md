---
title: Problemas conhecidos do Campaign v8
description: Problemas conhecidos na versão mais recente do Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 9ae93ce4e2b0424bb3b3862b2c7d016309bd630e
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 4%

---

# Problemas conhecidos{#known-issues}

Esta página lista os problemas conhecidos identificados na variável **Versões mais recentes do Campaign v8**. Além disso, as limitações provenientes do Campaign v8 são listadas [nesta página](ac-guardrails.md).


>[!NOTE]
>
>O Adobe publica essa lista de problemas conhecidos a seu critério. Tem como base o número de relatórios do cliente, a gravidade e a disponibilidade alternativa. Se um problema que você está encontrando não estiver listado, ele pode não ter se encaixado nos critérios para publicação nesta página.

## Campaign v8.3.8{#8.3-issues}

### Alterar problema de atividade da Fonte de Dados {#issue-2}

#### Descrição{#issue-2-desc}

Ao injetar dados no banco de dados da nuvem do Snowflake com uma campanha **Query** e **Alterar fonte de dados** atividade , o processo falha quando um caractere de barra invertida está presente nos dados. A cadeia de caracteres de origem não é removida e os dados não são processados corretamente no Snowflake.

Esse problema só acontece se o caractere de barra invertida estiver no final da string, por exemplo: `Barker\`.


#### Etapas de reprodução{#issue-2-repro}

1. Conecte-se ao console do cliente e crie um workflow.
1. Adicione um **Query** e configure-a.
1. Selecione os dados com as características descritas acima.
1. Adicione um **Alterar fonte de dados** e configure-a para selecionar o banco de dados da nuvem do Snowflake.
1. Execute o workflow e verifique os logs do workflow para ver o erro.


#### Mensagem de erro{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Solução alternativa{#issue-2-workaround}

A solução alternativa é excluir dados que contenham um caractere de barra invertida no final da string, ou removê-lo do arquivo de origem.


#### Referência interna{#issue-2-ref}

Referência: NEO45549


### Falha na atividade de carregamento de dados (arquivo) Upload de arquivo no servidor {#issue-3}

#### Descrição{#issue-3-desc}

Ao fazer upload de um arquivo no servidor do Campaign com um **Carregamento de dados (arquivo)** , o processo é interrompido em 100%, mas nunca termina.

#### Etapas de reprodução{#issue-3-repro}

1. Conecte-se ao console do cliente e crie um workflow.
1. Adicione um **Carregamento de dados (arquivo)** e configure-a.
1. Selecione o **Fazer upload no servidor** opção.
1. Selecione o arquivo no computador local,
1. Clique em **Upload**


#### Mensagem de erro{#issue-3-error}

O processo nunca termina.

#### Solução alternativa{#issue-3-workaround}

A solução é usar um console de cliente mais antigo. Você poderá fazer upload do arquivo no servidor.

Como administrador do Campaign, você pode baixar o console do cliente Campaign v8.3.1 em [Distribuição de software Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc layout=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;}.

Saiba como acessar a Distribuição de software do Adobe [nesta página](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=pt-BR){target=&quot;_blank&quot;}.

Saiba como atualizar seu console do cliente [nesta página](connect.md)

#### Referência interna{#issue-3-ref}

Referência: NEO47269

