---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 814f7c81aa4f154fdf289effc82b8d02bdd9b4c6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Versão mais recente{#latest-release}

Esta página lista novos recursos, melhorias e correções que vêm com a **versão mais recente do Campaign v8**.

## Versão 8.4.4 {#release-8-4-4}

_8 de março de 2023_

**Aprimoramento de segurança**

* Para melhorar a segurança, o Tomcat foi atualizado da versão 8.5.81 para a 8.5.85. (NEO-50530)

**Correções**

* Correção de um problema que impedia a rolagem na guia **Editar** do editor de conteúdo digital (DCE). (NEO-54474)
* Correção de um problema durante a replicação que poderia resultar em uma falha do servidor da web. (NEO-53670)


>[!CAUTION]
>
> A atualização do Console do Cliente é obrigatória. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).


## Versão 8.4.3 {#release-8-4-3}


_27 de janeiro de 2023_

**Aprimoramentos**

* Correção de um problema de sincronização de indicador de entrega entre o servidor de marketing e o servidor mid-sourcing. (NEO-50724) <!--OKKKK-->
* Correção de um problema que poderia causar um erro ao exportar um fluxo de trabalho. (NEO-50555) <!--OKKKK-->
* Correção de um problema ao estender um esquema que foi estendido anteriormente. (NEO-49118) <!--OKKKK-->
* Correção de um problema ao usar duas atividades de enriquecimento com o mesmo identificador na definição do link. (NEO-48851)
* Correção de dois problemas de falha de preparação de entrega. A preparação da entrega pode falhar quando o número de possíveis ofertas que estão sendo manipuladas é muito alto. O segundo problema ocorria quando os URLs de imagem eram definidos como URLs para serem rastreados em uma entrega de formato de texto. (NEO-48807) <!--OKKKK-->
* Correção de um problema que poderia resultar em uma falha de fluxo de trabalho, em que um fluxo de trabalho substituiria o nome do warehouse definido na conta externa para contas não FFDA. (NEO-43209) <!--OKKKK-->
* Segurança aprimorada em aplicativos da Web para evitar ataques de DDoS. (NEO-50757) <!--OKKKK-->
* O gerenciamento de dados de rastreamento consolidados foi aprimorado na Tabela FFDA (nms:trackingStats) do **[!UICONTROL Consolidated tracking]** para evitar duplicatas. (NEO-46409)
* Correção de um problema de operador lógico em consultas de fluxo de trabalho ao usar um `enableIf` em uma condição de operador lógico. A condição lógica anterior foi substituída. (NEO-45815)  <!--OKKKK-->
* A geração de perfis ativos foi otimizada no fluxo de trabalho de faturamento para melhorar o desempenho. (NEO-47658) <!--OKKKK-->
* Corrigido um problema com a importação de arquivos HTML no qual os nós de imagem (img) continham URLs com campos de personalização. (NEO-48396)
* Correção de um problema com o Snowflake (todas as implantações) ao usar o parâmetro de classificação em uma atividade de fluxo de trabalho de **Divisão**. (NEO-45899) <!--OKKKK-->
* Corrigido um problema que resultava em erro quando um usuário com direitos de acesso de leitura para a pasta nmsDeliveryMapping tentava executar uma campanha ou fluxo de trabalho. (NEO-48230)
* Corrigido um problema de desempenho na guia HTML de uma entrega que poderia ocorrer ao usar um código HTML grande. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Correção de um problema que impedia a utilização da opção de fluxo de trabalho **Mesclar linhas selecionadas**. (NEO-48488)
* Correção de um problema no conector Snowflake FDA que fazia com que os registros fossem descartados ao usar a opção “Junção simples de cardinalidade 0 ou 1” durante o enriquecimento. (NEO-48737)
* As referências restantes à biblioteca log4j foram removidas da instalação do Campaign no Windows. (NEO-44851)
* Corrigido um problema que poderia resultar em erro ao adicionar o indicador **Destinatários que abriram** (estimatedRecipientOpen) nos dados adicionais de uma atividade de fluxo de trabalho de **Consulta**. (NEO-46665)
* O gerenciamento de URLs de rastreamento foi aprimorado em workflows com várias entregas para melhorar o desempenho. (NEO-50894) <!--OKKKK-->
* Correção de um problema que poderia causar falha na replicação de esquemas que usam a pasta Xtkfolder. (NEO-46787) <!--OKKKK-->
* Correção de uma causa de problema que poderia fazer com que a coluna personalizada “lastModified” fosse descartada na tabela NmsSubscription. (NEO-48402)


>[!CAUTION]
>
> A atualização do Console do Cliente é obrigatória. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).
