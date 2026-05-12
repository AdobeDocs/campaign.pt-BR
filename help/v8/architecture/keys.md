---
title: Gerenciamento de chaves no Campaign
description: Introdução ao gerenciamento de chaves
feature: Configuration, FFDA
role: Developer
level: Intermediate
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
TQID: https://experienceleague.adobe.com/DfuZXr3sXnip35yNPRvZBDZ1BVb6dJFWYA2j90vc7RE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 576
ht-degree: 3%

---

# Gerenciamento de chaves e unicidade {#key-management}

No contexto de uma [implantação corporativa (FFDA)](enterprise-deployment.md), a chave primária é um Identificador exclusivo universal (UUID), que é uma cadeia de caracteres. Para criar esta UUID, o elemento principal do esquema deve conter os atributos **autouuid** e **autopk** definidos como **true**.

O Adobe Campaign v8 usa [!DNL Snowflake] como o banco de dados principal. A arquitetura distribuída do banco de dados [!DNL Snowflake] não fornece um mecanismo para garantir a unicidade de uma chave em uma tabela: os usuários finais são responsáveis pela consistência da chave no banco de dados do Adobe Campaign.

Evitar duplicatas em chaves e, especialmente, em chaves primárias é obrigatório para preservar a consistência do banco de dados relacional. Duplicatas em chaves primárias levam a problemas com atividades de fluxo de trabalho de gerenciamento de dados, como **Consulta**, **Reconciliação**, **Atualização de dados** e muito mais. Isso é crítico para definir os critérios de reconciliação adequados ao atualizar as tabelas [!DNL Snowflake].


>[!CAUTION]
>
>Chaves duplicadas não estão restritas aos UUIDs. Isso pode acontecer com IDs, incluindo chaves personalizadas criadas em tabelas personalizadas.


## Unicity Service{#unicity-service}

O Unicity Service é um componente do Cloud Database Manager que ajuda os usuários a preservar e monitorar a integridade das restrições de chaves exclusivas nas tabelas do Cloud Database. Isso permite reduzir o risco de inserir chaves duplicadas.

Como o Cloud Database não impõe restrições de unicidade, o Unicity Service reduz o risco de inserir duplicatas ao gerenciar os dados com o Adobe Campaign.

### Fluxo de trabalho de unicidade{#unicity-wf}

O Unicity Service vem com um fluxo de trabalho interno **[!UICONTROL Unicity alerting]** dedicado, para monitorar restrições de unicidade e alertar quando duplicatas são detectadas.

Esse fluxo de trabalho técnico está disponível no nó **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** do explorador do Campaign. **Não deve ser modificado**.

Este fluxo de trabalho verifica todos os esquemas personalizados e integrados para detectar linhas duplicadas.

![](assets/unicity-alerting-wf.png)

Se o fluxo de trabalho **[!UICONTROL Unicity alerting]** (ffdaUnicity) detectar algumas chaves duplicadas, elas serão adicionadas a uma tabela **Unicidade de auditoria** específica, que inclui o nome do esquema, o tipo de chave, o número de linhas afetadas e a data. Você pode acessar chaves duplicadas do nó **[!UICONTROL Administration > Audit > Key Unicity]**.

![](assets/unicity-table.png)

Como Administrador de Banco de Dados, você pode usar uma atividade SQL para remover as duplicatas ou entrar em contato com o Atendimento ao Cliente da Adobe para obter mais orientação.

### Alertas{#unicity-wf-alerting}

Uma notificação específica é enviada ao grupo de operadores **[!UICONTROL Workflow Supervisors]** quando chaves duplicadas são detectadas. O conteúdo e o público deste alerta podem ser alterados na atividade **Alert** do fluxo de trabalho **[!UICONTROL Unicity alerting]**.

![](assets/wf-alert-activity.png)


## Medidas de proteção adicionais {#duplicates-guardrails}

O Campaign vem com um conjunto de novas medidas de proteção para impedir a inserção de chave duplicada no banco de dados [!DNL Snowflake].

>[!NOTE]
>
>Essas medidas de proteção estão disponíveis a partir do Campaign v8.3. Para verificar sua versão, consulte [esta seção](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### Preparação da entrega {#remove-duplicates-delivery-preparation}

O Adobe Campaign remove automaticamente qualquer UUID duplicado de um público-alvo durante a preparação do delivery. Esse mecanismo impede que qualquer erro ocorra durante a preparação de um delivery. Como usuário final, você pode verificar essas informações nos logs do delivery: alguns recipients podem ser excluídos do público-alvo principal devido à duplicação de chaves. Nesse caso, o seguinte aviso será exibido: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### Atualizar dados em um fluxo de trabalho {#duplicates-update-data}

No contexto de uma [implantação corporativa (FFDA)](enterprise-deployment.md), não é possível selecionar uma chave interna (UUID) como campo para atualizar dados em um fluxo de trabalho.

![](assets/update-data-no-internal-key.png)

### Consultar um esquema com duplicatas {#query-with-duplicates}

Quando um fluxo de trabalho inicia a execução da consulta em um esquema, o Adobe Campaign verifica se há algum registro duplicado relatado na [tabela Unicidade de auditoria](#unicity-wf). Em caso positivo, o workflow registra um aviso como a operação subsequente nos dados duplicados deve afetar potencialmente o resultado do workflow.

![](assets/query-with-duplicates.png)

Essa verificação é executada nas seguintes atividades de workflow:

* Consulta
* Query incremental
* Lista de leitura


>[!NOTE]
>
>Se estiver fazendo a transição de outra versão do Campaign, é fundamental remover duplicatas, solucionar problemas e limpar dados para evitar impacto na transição.
