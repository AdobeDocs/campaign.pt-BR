---
title: Importar perfis no Campaign
description: Saiba como importar contatos no Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
TQID: https://experienceleague.adobe.com/qoVtBCkTTk2DKaR605exVaJvjQ7kjKRoRg-9fJqdoo4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 287
ht-degree: 42%

---

# Importar perfis de um arquivo{#create-profiles}

Para preencher o banco de dados do Campaign, você pode [adicionar perfis manualmente](create-profiles.md) ou importar perfis conforme detalhado abaixo. Você também pode usar arquivos importados para atualizar dados de contato.

## Importar perfis com um fluxo de trabalho {#import-profiles-with-a-wf}

Os fluxos de trabalho podem ser uma maneira útil de automatizar alguns dos processos de importação. Se você importa dados de um arquivo local ou de um SFTP, você pode usar fluxos de trabalho para padronizar os procedimentos de gerenciamento de dados.

### Usar dados de uma lista: Lista de leitura {#data-from-read-list}

Prepare e estruture seus dados em um arquivo para importá-lo com um fluxo de trabalho. [Saiba mais](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html?lang=pt-BR){target="_blank"}.

### Carregar dados de um arquivo {#data-from-a-file}

Os dados processados em um workflow podem ser extraídos de um arquivo estruturado para serem importados para o Adobe Campaign. [Saiba mais](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html?lang=pt-BR){target="_blank"}.

Depois que os dados forem coletados, você poderá usá-los em seus fluxos de trabalho, por exemplo, para enriquecer uma entrega ou atualizar o banco de dados. Para obter mais informações, consulte [esta seção](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html?lang=pt-BR){target="_blank"}.

## Importações únicas{#import-jobs}

O Adobe Campaign fornece a capacidade de importação genérica que permite, por exemplo, extrair uma lista de clientes ou prospetos que se tornarão parte de uma população de destino ou fornecer dados de arquivos externos ao seu banco de dados.

As importações genéricas são gerenciadas no menu **[!UICONTROL Profiles and Targets > Jobs]** da página inicial do Adobe Campaign.

![](assets/new-import-job.png)

As etapas para executar uma importação genérica estão detalhadas na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=pt-BR){target="_blank"}.
