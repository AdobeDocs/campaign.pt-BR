---
product: campaign
title: Fluxos de trabalho de regulamento de proteção de dados de privacidade
description: Saiba mais sobre os fluxos de trabalho do Regulamento de proteção de dados de privacidade
role: User
version: Campaign v8, Campaign Classic v7
feature: Workflows, Privacy
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: a7760dfc-5c44-4d77-bb68-c50b1e265c93
    internal-label: Security and privacy
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ac9c0a9c-8a76-4419-bd64-9c34c5782666
    internal-label: Privacy
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%
---

# Regulamento de proteção de dados de privacidade{#general-data-protection-regulation-gdpr}


Os fluxos de trabalho detalhados abaixo são instalados com o módulo de **Regulamento de proteção de dados de privacidade** por padrão. Para obter mais informações sobre esse módulo, consulte esta [seção](https://helpx.adobe.com/br/campaign/kb/acc-privacy.html).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Collect privacy requests</span> <br /> </td> 
   <td> <span class="uicontrol">collectPrivacyRequests</span> <br /> </td> 
   <td> Esse fluxo de trabalho gera os dados do destinatário armazenados no Adobe Campaign e o disponibiliza para download na tela da solicitação de privacidade.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Delete privacy requests data</span> <br /> </td> 
   <td> <span class="uicontrol">deletePrivacyRequestsData</span> <br /> </td> 
   <td> Esse fluxo de trabalho exclui os dados do destinatário armazenados no Adobe Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Privacy request cleanup</span> <br /> </td> 
   <td> <span class="uicontrol">cleanupPrivacyRequests</span> <br /> </td> 
   <td> Esse fluxo de trabalho apaga os arquivos de solicitação de acesso criados há mais de 90 dias.<br /> </td> 
  </tr> 
 </tbody> 
</table>

