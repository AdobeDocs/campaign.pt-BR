---
title: Notas de versão anteriores do Campaign v8
description: Lançamento antecipado do Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 100%

---

# Notas de versão anteriores {#e-new-release}

Esta página descreve as melhorias e correções incluídas no próximo lançamento do Campaign v8. Esse conteúdo está sujeito a alterações sem aviso prévio até a data de lançamento. As notas de versão oficiais estão disponíveis nesta [página](../start/release-notes.md).

## Versão 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> A atualização do Console do Cliente é obrigatória. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#download-ac-console).

_7 de outubro de 2022_

**Aprimoramentos**

* Correção de um problema que afetava as atualizações de status do log de entrega na instância MID quando a opção FeatureFlag_GZIP_Compression era habilitada. (NEO-49183)
* O fluxo de trabalho técnico de **Limpeza do banco de dados** agora também lida com esquemas de preparo personalizados. (NEO-48974)
* Correção de um problema que poderia fazer com que as entregas ficassem no status **Pendente** mesmo que a data de contato tivesse sido alcançada. (NEO-48079, NEO-48251)
* Estabilidade aprimorada ao manipular strings XML inválidas durante chamadas SOAP. (NEO-48027)
* Correção de um problema que poderia retardar a análise de entrega, durante a etapa de exclusão de incluir na lista de bloqueios de recipients, ao direcionar grandes volumes de recipients. (NEO-48019)
* Para evitar a lentidão ao enviar provas para os seed addresses, todas as replicações consecutivas de membros de seed agora são agrupadas em uma solicitação de replicação. (NEO-44844)
* Correção de um problema que resultava em problemas de personalização ao enviar mensagens SMS usando um modo de entrega externo. (NEO-46415)
* Correção de um problema que exibia um erro ao tentar visualizar uma entrega em qualquer evento arquivado do Centro de mensagens. (NEO-43620)
* Correção de um problema em fluxos de trabalho que poderia impedir a atualização de arquivos no servidor ao usar a atividade **Carregamento de dados (arquivo)**. O processo parou em 100%, mas nunca terminou. (NEO-47269)
* Correção de um problema que resultava na criação de DeliveryParts desnecessárias quando a entrega usava os modos de calendário e divisão. (NEO-48634)
* Correção de um problema de desempenho ao usar ondas baseadas em calendário. (NEO-48451)
* Correção de um problema que poderia resultar em uma mensagem de erro na tela da lista de entrega após criar um novo target mapping em um esquema personalizado. (NEO-49237)
* Correção de um problema que poderia ocorrer se uma entrega atingisse um tamanho específico durante o processo de MTA. (NEO-46097)
* Correção de um problema que impedia que os logs de rastreamento retornassem dados relacionados ao navegador do destinatário. (NEO-46612)
* Correção de um problema durante a pós-atualização em ambientes japoneses. (NEO-46640)
* Correção de um problema ao usar a atividade de **Consulta** e filtrar uma tabela. Quando um nome de coluna continha a palavra “Atualizar”, ocorria um erro de compilação com um identificador inválido e a seguinte mensagem: “número de linhas atualizado”. (NEO-46485)
* Correção de um problema que impedia que o fluxo de trabalho técnico do **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) fosse interrompido mesmo quando um erro ocorresse durante sua execução. (NEO-46280)
* Correção de um problema que poderia causar perda de dados se o fluxo de trabalho de preparo estivesse com erro e o período de retenção fosse totalmente passado. (NEO-48975)
* Correção de um problema ao inserir dados no banco de dados de nuvem do Snowflake com uma atividade de **Consulta** do Campaign e uma atividade **Alterar fonte de dados**: o processo falhava quando um caractere de barra invertida estava presente nos dados. A cadeia de caracteres de origem não tinha escape e os dados não eram processados corretamente no Snowflake. (NEO-45549)
