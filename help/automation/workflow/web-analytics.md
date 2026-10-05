---
product: campaign
title: Análise da web
description: Saiba mais sobre o pacote do Web Analytics
feature: Workflows, Analytics Integration
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
  - id: cbcf4d90-26be-46e2-b16a-aebc529dc41e
    internal-label: Analytics integration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 89%
---

# Análise da web{#web-analytics}



Os fluxos de trabalho detalhados abaixo são instalados com o módulo dos **conectores Web Analytics** por padrão.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Envio de indicadores e atributos de campanha</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsSendMetrics</span> <br /> </td> 
   <td> Esse fluxo de trabalho permite enviar indicadores de campanha de email do Adobe Campaign para o Adobe Experience Cloud Suite por meio do conector do Adobe® Analytics. Os indicadores relacionados são: <strong>Sent</strong> (iSent), <strong>Total count of opens</strong> (iTotalRecipientOpen), <strong>Total number of recipients who clicked</strong> (iTotalRecipientClick), <strong>Errors</strong> (iError), <strong>Opt-Out</strong> (opt-out) (iOptOut).<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Identificação de contatos convertidos</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsFindConverted</span> <br /> </td> 
   <td> Este fluxo de trabalho indexa os visitantes do site que concluíram sua compra após uma campanha de re-marketing. Os dados recuperados por este fluxo de trabalho podem ser acessados no <span class="uicontrol">Relatório de eficiência de remarketing</span> (Consulte esta seção ). <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpeza de eventos</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsPurgeWebEvents</span> <br /> </td> 
   <td> Esse fluxo de trabalho permite excluir todos os eventos do campo de banco de dados de acordo com o período configurado no campo <span class="uicontrol">Lifespan</span>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Recuperação de eventos da Web</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsGetWebEvents</span> <br /> </td> 
   <td> A cada hora, este fluxo de trabalho baixa segmentos do comportamento do usuário na Internet em um determinado site, os coloca no banco de dados do Adobe Campaign e inicia o fluxo de trabalho de re-marketing. <br /> </td> 
  </tr> 
 </tbody> 
</table>

