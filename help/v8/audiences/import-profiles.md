---
title: Importar perfis no Campaign
description: Saiba como importar contatos no Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 45%

---

# Importar perfis de um arquivo{#create-profiles}

Para preencher o banco de dados do Campaign, é possível [adicionar perfis manualmente](create-profiles.md) ou importe perfis conforme detalhado abaixo. Também é possível usar arquivos importados para atualizar dados de contato.

## Importar perfis com um fluxo de trabalho {#import-profiles-with-a-wf}

Os workflows podem ser uma maneira útil de automatizar alguns dos processos de importação. Se você importa dados de um arquivo local ou de um SFTP, você pode usar workflows para padronizar os procedimentos de gerenciamento de dados.

### Usar dados de uma lista: Lista de leitura {#data-from-read-list}

Prepare e estruture seus dados em um arquivo para importá-los com um fluxo de trabalho. [Saiba mais](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html).

### Carregar dados de um arquivo {#data-from-a-file}

Os dados processados em um workflow podem ser extraídos de um arquivo estruturado para serem importados para o Adobe Campaign. [Saiba mais](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html).

Depois que os dados forem coletados, você poderá usá-los em seus workflows, por exemplo, para enriquecer uma entrega ou atualizar o banco de dados. Para obter mais informações, consulte [esta seção](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html).

## Importações únicas{#import-jobs}

O Adobe Campaign fornece um recurso de importação genérico que permite, por exemplo, extrair uma lista de clientes ou prospetos que farão parte de um público-alvo ou fornecer ao banco de dados dados dados de arquivos externos.

As importações genéricas são gerenciadas a partir do **[!UICONTROL Profiles and Targets > Jobs]** na página inicial do Adobe Campaign.

![](assets/new-import-job.png)

As etapas para executar uma importação genérica estão detalhadas em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=pt-BR){target=&quot;_blank&quot;}.
