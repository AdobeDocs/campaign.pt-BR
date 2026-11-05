---
product: campaign
title: Plataforma Mid-sourcing
description: Plataforma Mid-sourcing
feature: Workflows
role: User
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
source-git-commit: 8a7bf8408d15e0bd9e1c3e72f7846bf9a79c6885
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 41%
---

# Plataforma Mid-sourcing{#mid-sourcing-platform}



Os fluxos de trabalho detalhados abaixo são instalados com o módulo da **plataforma Mid-sourcing** por padrão.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Indicadores de delivery</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryIndicators</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza os indicadores de rastreamento de entrega para uma entrega. Esse fluxo de trabalho é acionado a cada hora por padrão.<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>O período de retenção de log no servidor de mid-sourcing deve ser maior que o período de validade de entrega mais o valor **indicatorsDuration**. Caso contrário, os indicadores de delivery diminuirão quando os logs antigos forem removidos e os valores mais baixos serão sincronizados com a instância de marketing. Por exemplo, com um período de validade de 5 dias e uma **indicatorsDuration** de 30 dias, defina o período de retenção para pelo menos 36 dias.
