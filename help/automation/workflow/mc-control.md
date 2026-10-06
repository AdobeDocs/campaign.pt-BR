---
product: campaign
title: Centro de Mensagens (Controle)
description: Centro de Mensagens (Controle)
feature: Workflows
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
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%
---

# Centro de Mensagens (Controle){#message-center-control}

O fluxo de trabalho detalhado abaixo é agendado para ser executado a cada hora. Ele é instalado por padrão com o módulo do **Centro de Mensagens – Controle**.


<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Message Center &lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;external_account_name&gt;<br /> </td> 
   <td> Esse fluxo de trabalho:<br /> 
    <ul> 
     <li> <p>recupera a lista de eventos processados pela(s) operação(s).</p> </li> 
     <li> <p>sincroniza com a tabela NmsBroadLogMsg para recuperar as qualificações da mensagem de entrega.</p> </li> 
     <li> <p>recupera logs de entrega de eventos assim que a sincronização com a tabela NmsBroadLogMsg for concluída.</p> </li> 
     <li> <p>sincroniza com a tabela NmsTrackingUrl para recuperar o rastreamento para as URLs de entrega.</p> </li> 
     <li> <p>recupera as URLs de rastreamento de eventos assim que a sincronização com a tabela NmsTrackingUrl for concluída.</p> </li> 
     <li> <p>permite recuperar todos os endereços de email colocados em quarentena a cada três horas após o envio de uma entrega.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

