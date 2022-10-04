---
title: Notas de versão do Campaign v8 antecipadamente
description: Lançamento do Campaign v8 antecipado
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---

# Notas de versão anteriores {#e-new-release}

Esta página descreve aprimoramentos e correções incluídos na próxima versão do Campaign v8. Esse conteúdo está sujeito a alterações sem aviso prévio até a data de lançamento. As notas de versão oficiais estão disponíveis neste [página](../start/release-notes.md).

## Versão 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> A atualização do Console do Cliente é obrigatória. Saiba como atualizar seu console do cliente neste [página](../start/connect.md#download-ac-console).

_7 de outubro de 2022_

**Aprimoramentos**

* Correção de um problema que afetava as atualizações de status do log de delivery na instância MID, quando a opção FeatureFlag_GZIP_Compression era habilitada. (NEO-49183)
* O **Limpeza do banco de dados** o fluxo de trabalho técnico agora também lida com esquemas de preparo personalizados. (NEO-48974)
* Correção de um problema que poderia resultar na permanência dos deliveries em **Pending** mesmo que a data de contato tenha sido alcançada. (NEO-48079, NEO-48251)
* Estabilidade aprimorada ao manipular strings XML inválidas durante chamadas SOAP. (NEO-48027)
* Correção de um problema que poderia retardar a análise de delivery, durante a etapa de exclusão de incluir na lista de bloqueios recipients, ao direcionar grandes volumes de recipients. (NEO-48019)
* Para evitar a lentidão ao enviar prova para seed addresses, todas as replicações consecutivas de membros seed agora são agrupadas em uma solicitação de replicação. (NEO-44844)
* Correção de um problema que resultava em problemas de personalização ao enviar mensagens SMS usando um modo de delivery externo. (NEO-46415)
* Correção de um problema que exibia um erro ao tentar visualizar um delivery em qualquer evento arquivado do Centro de mensagens. (NEO-43620)
* Correção de um problema em workflows que poderia impedir a atualização de arquivos no servidor ao usar o **Carregamento de dados (arquivo)** atividade . O processo parou em 100%, mas nunca terminou. (NEO-47269)
* Correção de um problema que resultava na criação de DeliveryParts desnecessárias quando o delivery usava os modos de calendário e divisão. (NEO-48634)
* Correção de um problema de desempenho ao usar ondas baseadas em calendário. (NEO-48451)
* Correção de um problema que poderia resultar em uma mensagem de erro na tela da lista de delivery após criar um novo target mapping em um schema personalizado. (NEO-49237)
* Correção de um problema que poderia ocorrer se um delivery atingisse um tamanho específico durante o processo MTA. (NEO-46097)
* Correção de um problema que impedia o rastreamento de logs de retornar dados relacionados ao navegador do recipient. (NEO-46612)
* Correção de um problema durante o pós-atualização em ambientes japoneses. (NEO-46640)
* Correção de um problema ao usar o **Query** atividade e filtragem de uma tabela. Quando um nome de coluna continha a palavra &quot;Atualizar&quot;, ocorria um erro de compilação com um identificador inválido e a seguinte mensagem: &quot;número de linhas atualizadas&quot;. (NEO-46485)
* Correção de um problema que impedia o **[!UICONTROL Replicate Staging data]** O workflow técnico (ffdaReplicateStagingData) não é interrompido mesmo quando um erro ocorreu durante sua execução. (NEO-46280)
* Correção de um problema que poderia causar perda de dados se o workflow de preparo estivesse com erro e o período de retenção fosse totalmente passado. (NEO-48975)
* Correção de um problema ao injetar dados no banco de dados da nuvem do Snowflake com uma Campanha **Query** e uma **Alterar fonte de dados** atividade : o processo falhava quando um caractere de barra invertida estava presente nos dados. A cadeia de caracteres de origem não foi removida e os dados não foram processados corretamente no Snowflake. (NEO-45549)
