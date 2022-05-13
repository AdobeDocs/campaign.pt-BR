---
title: Gerenciamento de chaves no Campaign
description: Introdução ao gerenciamento de chaves
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: d3137e75bfc4986e1d6badf32f21fda4c4353c8b
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 3%

---

# Gerenciamento de chaves e unicidade {#key-management}

No contexto de um [Implantação empresarial (FDA)](enterprise-deployment.md), a chave primária é um UUID (Universally Unique IDentifier), que é uma string em caracteres. Para criar esse UUID, o elemento principal do schema deve conter a variável **autouuid** e **autopk** atributos definidos como **true**.

O Adobe Campaign v8 usa [!DNL Snowflake] como o banco de dados principal. A arquitetura distribuída da [!DNL Snowflake] O banco de dados não fornece mecanismo para garantir a unicidade de uma chave dentro de uma tabela: os usuários finais são responsáveis pela consistência das chaves no banco de dados do Adobe Campaign.

Evitar duplicatas em chaves e, especialmente, em chaves primárias, é obrigatório para preservar a consistência do banco de dados relacional. Duplicidades em chaves primárias levam a problemas com atividades de fluxo de trabalho de gerenciamento de dados, como **Query**, **Reconciliação**, **Atualizar dados** e muito mais. Isso é essencial para definir os critérios de reconciliação adequados ao atualizar [!DNL Snowflake] tabelas.


>[!CAUTION]
>
>Chaves duplicadas não são restritas a UUIDs. Isso pode ocorrer no com IDs, incluindo chaves personalizadas criadas em tabelas personalizadas.


## Unicity Service{#unicity-service}

O Unicity Service é um componente do Cloud Database Manager que ajuda os usuários a preservar e monitorar a integridade de restrições de chave exclusivas nas tabelas do Cloud Database. Isso permite reduzir o risco de inserir chaves duplicadas.

Como o Banco de Dados da Nuvem não impõe restrições de unicidade, o Unicity Service reduz o risco de inserir duplicatas ao gerenciar os dados com o Adobe Campaign.

### Fluxo de trabalho de Unicidade{#unicity-wf}

O Unicity Service vem com um **[!UICONTROL Unicity alerting]** fluxo de trabalho integrado, para monitorar as restrições de unicidade e alertar quando duplicatas são detectadas.

Esse workflow técnico está disponível no **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** nó do explorador do Campaign. **Ele não deve ser modificado**.

Esse workflow verifica todos os esquemas personalizados e incorporados para detectar linhas duplicadas.

![](assets/unicity-alerting-wf.png)

Se a variável **[!UICONTROL Unicity alerting]** O workflow (ffdaUnicity) detecta algumas chaves duplicadas, elas são adicionadas a um **Unicidade de auditoria** tabela, que inclui o nome do schema, o tipo de chave, o número de linhas afetadas e a data. Você pode acessar chaves duplicadas da variável **[!UICONTROL Administration > Audit > Key Unicity]** nó .

![](assets/unicity-table.png)

Como Administrador de Banco de Dados, você pode usar uma atividade SQL para remover as duplicatas ou entrar em contato com o Atendimento ao Cliente do Adobe para obter mais orientações.

### Alerta{#unicity-wf-alerting}

Uma notificação específica é enviada ao **[!UICONTROL Workflow Supervisors]** grupo de operadores quando chaves duplicadas forem detectadas. O conteúdo e o público-alvo desse alerta podem ser alterados no **Alerta** da **[!UICONTROL Unicity alerting]** fluxo de trabalho.

![](assets/wf-alert-activity.png)


## Medidas de proteção adicionais{#duplicates-guardrails}

O Campaign vem com um conjunto de novas grades de proteção para evitar a inserção de chave duplicada em [!DNL Snowflake] banco de dados.

>[!NOTE]
>
>Essas grades de proteção estão disponíveis a partir do Campaign v8.3. Para verificar sua versão, consulte [esta seção](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### Preparação do delivery{#remove-duplicates-delivery-preparation}

O Adobe Campaign remove automaticamente qualquer UUID duplicada de um público-alvo durante a preparação do delivery. Esse mecanismo impede que qualquer erro ocorra ao preparar um delivery. Como usuário final, você pode verificar essas informações nos logs do delivery: alguns recipients podem ser excluídos do target principal devido à chave duplicada. Nesse caso, o seguinte aviso é exibido: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### Atualizar dados em um fluxo de trabalho{#duplicates-update-data}

No contexto de um [Implantação empresarial (FDA)](enterprise-deployment.md), não é possível selecionar uma chave interna (UUID) como campo para atualizar dados em um fluxo de trabalho.

![](assets/update-data-no-internal-key.png)

Ao usar a chave de reconciliação explícita, a variável **Atualizar dados** A atividade garante automaticamente a unicidade do schema de destino com base nessa chave ao:

1. Desduplicação de dados de entrada (da transição)
1. Desduplicação de dados com tabela de destino (mesclagem)


![](assets/update-data-deduplicate.png)

>[!CAUTION]
>
>Essa garantia só se aplica com a opção **[!UICONTROL Using reconciliation keys]**.


### Consultar um schema com duplicatas{#query-with-duplicates}

Quando um workflow inicia a execução da query em um schema, o Adobe Campaign verifica se qualquer registro duplicado é relatado na variável [Tabela de Unicidade de auditoria](#unicity-wf). Nesse caso, o workflow registra um aviso, pois a operação subsequente nos dados duplicados deve afetar potencialmente o resultado do workflow.

![](assets/query-with-duplicates.png)

Essa verificação é realizada nas seguintes atividades de workflow:

* Consulta
* Query incremental
* Lista de leitura