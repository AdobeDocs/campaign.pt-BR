---
product: campaign
title: Gerenciar permissões de fluxo de trabalho
description: Saiba como gerenciar permissões de fluxo de trabalho
feature: Workflows, Permissions
role: Admin
version: Campaign v8, Campaign Classic v7
exl-id: 3cb8aeec-e758-4b71-adef-67942cf9ded7
TQID: 'https://experienceleague.adobe.com/xZwqhzyDbDM309Q-WNpYoD-BvWiJmaTVHsmf50ywAJk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 96%
---
# Gerenciar permissões de fluxo de trabalho{#managing-rights}



Se não forem Administradores, os operadores do Adobe Campaign precisam de direitos de acesso para criar, executar ou modificar fluxos de trabalho.

Em geral, os operadores que atuam com fluxos de trabalho precisam acessar os arquivos que contêm os dados usados durante as várias atividades (destinatários, lista de destinatários, subscrições, entregas, etc.) e possivelmente seus arquivos secundários.

Eles também devem ser mapeados com os direitos nomeados que coincidam com as ações executadas pelos fluxos de trabalho que eles afetarão (importação do destinatário, acesso à arquivos, fusão, execução de script SQL, etc.).

Para obter mais informações sobre gerenciamento de operadores e permissões, consulte [esta seção](../../v8/start/gs-permissions.md).

## Grupos de operadores {#operator-groups-wf}

Os seguintes grupos de operadores estão associados ao fluxo de trabalho:

* O grupo **[!UICONTROL Workflow execution]** permite controlar a execução e a aprovação de fluxo de trabalho de segmentação: o direito nomeado WORKFLOW é mapeado para os operadores deste grupo. É necessário para todas as ações em fluxos de trabalho, além de direitos de acesso aos arquivos de dados. Por padrão, o grupo **[!UICONTROL Workflow execution]** tem acesso somente leitura de arquivos padrão de fluxos de trabalho para construção de target e modelos de fluxo de trabalho. Os operadores neste grupo também têm acesso de leitura e gravação para o arquivo de aprovação pendente.
* O grupo **[!UICONTROL Workflow supervisors]** permite que os operadores gerenciem aprovações de fluxo de trabalho.
* O grupo **[!UICONTROL Operation Managers]** permite acessar fluxos de trabalho da campanha.

## Direitos nomeados {#named-rights}

Somente o direito nomeado WORKFLOW é específico para fluxos de trabalho: permite criar, iniciar e parar fluxos de trabalho. Os direitos de leitura no arquivo de fluxo de trabalho são necessários para que o direito nomeado seja aplicável. Para fluxos de trabalho de segmentação, é necessário a leitura no arquivo **[!UICONTROL Profiles and Targets]**.

## Conta de execução de fluxo de trabalho {#workflow-execution-account}

Você pode configurar a conta de execução a ser usada no nível de modelo de fluxo de trabalho. A conta de execução permite mapear autorizações para o fluxo de trabalho diretamente, independentemente do operador do Adobe Campaign iniciando a execução. Por padrão, cada fluxo de trabalho é executado com os direitos do operador que o iniciou.

Para mapear uma conta de execução a um fluxo de trabalho, vá para a lista de modelos de fluxo de trabalho e clique com o botão direito do mouse no modelo vinculado ao fluxo de trabalho. Escolha **[!UICONTROL Action > Change execution account...]** e depois selecione a conta que será usada.
