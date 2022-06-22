---
title: Problemas conhecidos do Campaign v8
description: Problemas conhecidos na versão mais recente do Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 099d14ace04df1b98e03be283a6436f49f535958
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 1%

---

# Problemas conhecidos{#known-issues}

Esta página lista os problemas conhecidos identificados na variável **Versão mais recente do Campaign v8**. Além disso, as limitações provenientes do Campaign v8 são listadas [nesta página](known-limitations.md).


>[!NOTE]
>
>O Adobe publica essa lista de problemas conhecidos a seu critério. Tem como base o número de relatórios do cliente, a gravidade e a disponibilidade alternativa. Se um problema que você está encontrando não estiver listado, ele pode não ter se encaixado nos critérios para publicação nesta página.

## Alterar problema de atividade da Fonte de Dados {#issue-1}

### Descrição

O **Alterar fonte de dados** A atividade está falhando ao transferir dados do banco de dados local do Campaign para o banco de dados da nuvem do Snowflake. Ao alternar direções, a atividade pode gerar problemas.

### Etapas de reprodução

1. Conecte-se ao console do cliente e crie um workflow.
1. Adicione um **Query** e uma **Alterar fonte de dados** atividade .
1. Defina uma query na **email**, que é uma string.
1. Execute o workflow e clique com o botão direito do mouse na transição para visualizar o público: os registros de email são exibidos e substituídos por `****`.
1. Verifique os logs do workflow: o **Alterar fonte de dados** A atividade interpreta esses registros como valores numéricos.

### Solução alternativa

Para que os dados sejam transferidos do banco de dados da nuvem do Snowflake para o banco de dados local do Campaign e de volta para o Snowflake, você deve usar dois **Alterar fonte de dados** atividades.

### Referência interna

Referência: NEO45549


## Falha na atividade de carregamento de dados (arquivo) Upload de arquivo no servidor {#issue-2}

### Descrição

O upload de arquivo no servidor do Campaign é interrompido em 100% de progresso, mas nunca termina.

### Etapas de reprodução

1. Conecte-se ao console do cliente e crie um workflow.
1. Adicione um **Carregamento de dados (arquivo)** e configure-a.
1. Selecione o **Fazer upload no servidor** opção.
1. Selecione o arquivo no computador local,
1. Clique em **Upload**

### Solução alternativa

nenhuma

### Referência interna

Referência: NEO47269