---
product: campaign
title: Interação
description: Interação
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 73%
---

# Interação{#interaction}

Os fluxos de trabalho detalhados abaixo são instalados com o complemento **Mecanismo de oferta (Interação)** por padrão.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Full aggregate calculation (propositionrcp cube)</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> Esse fluxo de trabalho atualiza o agregado <strong>completo</strong> do cubo da <strong>Apresentação da oferta. </strong> É acionado todos os dias às 6:00 AM por padrão. Este agregado abrange as seguintes dimensões: Canal, Entrega, Oferta de marketing e Data.<br /> O cubo <strong>Apresentação de oferta</strong> é usado para gerar relatórios com base em ofertas.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter full aggregate calculation</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Esse fluxo de trabalho atualiza o agregado <strong>completo</strong> para o cubo do <strong>centro de mensagem</strong>. É acionado todos os dias às 3:00 AM por padrão. Este agregado abrange as seguintes dimensões: Canal, Data, Status e Tipo de evento.<br /> O cubo <strong>Centro de mensagens</strong> é usado para gerar relatórios com base em eventos. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Saiba mais sobre cubos e agregações em [esta seção](../../v8/reporting/gs-cubes.md).

