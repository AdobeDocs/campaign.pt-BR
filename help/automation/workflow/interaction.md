---
product: campaign
title: Interação
description: Interação
feature: Workflows, Interaction
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 93%

---


# Interação{#interaction}

Os workflows detalhados abaixo são instalados com o complemento **Mecanismo de oferta (Interação)** por padrão.

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
   <td> Esse workflow atualiza o agregado <strong>completo</strong> do cubo da <strong>Apresentação da oferta. </strong> É acionado todos os dias às 6:00 AM por padrão. Esse agregado captura as seguintes dimensões: canal, delivery, oferta de marketing e data.<br /><strong> O cubo de apresentação da oferta é usado para gerar relatórios com base em ofertas.</strong><br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter full aggregate calculation</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Esse workflow atualiza o agregado <strong>completo</strong> para o cubo do <strong>centro de mensagem</strong>. É acionado todos os dias às 3:00 AM por padrão. Esse agregado captura as seguintes dimensões: canal, data, status e tipo de evento.<br /> O cubo do <strong>centro de mensagem</strong> é usado para gerar relatórios com base em eventos. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Saiba mais sobre cubos e agregados em [esta seção](../../v8/reporting/gs-cubes.md).

