---
product: campaign
title: Canal LINE
description: Canal LINE
feature: Workflows, Line App
role: User
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: d9d413df-4e9e-4906-bbbc-28c06c2ccf59
    internal-label: LINE App
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 90%
---

# Canal LINE{#line-channel}

Os fluxos de trabalho detalhados abaixo são instalados com o módulo do **canal LINE** por padrão. Para obter mais informações sobre este módulo, consulte [esta página](../../v8/send/line/line.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualização do token de acesso LINE V2</span> <br /> </td> 
   <td> <span class="uicontrol">updateLineV2AccessToken</span> <br /> </td> 
   <td> Este fluxo de trabalho atualiza o token de acesso para LINE V2.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Excluir usuários bloqueados do LINE</span> <br /> </td> 
   <td> <span class="uicontrol">deleteBlockedLineUsersV2</span> <br /> </td> 
   <td> Esse fluxo de trabalho garante que os dados dos usuários LINE V2 sejam excluídos após bloquearem a conta oficial LINE por 180 dias.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Migração do MID para LineUserID</span> <br /> </td> 
   <td> <span class="uicontrol">MIDToUserIDMigration</span> <br /> </td> 
   <td> Esse fluxo de trabalho gera a ID de usuários LINE V2 para migração de LINE V1 para LINE V2.<br /> </td> 
  </tr> 
 </tbody> 
</table>

