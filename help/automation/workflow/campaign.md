---
product: campaign
title: Campanha
description: Campanha
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 92%

---


# Campanha{#campaign}

Os fluxos de trabalho detalhados abaixo são instalados com o módulo **Campanha** por padrão.

>[!CAUTION]
>
>Esses workflows DEVEM ser iniciados para que os processos de campanha sejam executados em um nível de campanha.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Cost calculation</span> <br /> </td> 
   <td> <span class="uicontrol">budgetMgt</span><br /> </td> 
   <td> Esse workflow inicia o cálculo das linhas de despesas e custos nos orçamentos, planos, programas, campanhas, entregas e tarefas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Stock: Orders and alerts</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span><br /> </td> 
   <td> Este workflow inicia o cálculo de estoque nas linhas de pedido e gerencia os limites de aviso.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Empregos em deliveries em campanhas</span><br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span><br /> </td> 
   <td> Esse fluxo de trabalho aciona as entregas aprovadas e inicia o pós-processamento no provedor de serviços para uma entrega externa. Também envia notificações e lembretes de aprovação.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Campaign jobs</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span><br /> </td> 
   <td> Esse workflow gerencia as tarefas para campanhas de marketing (inicia o target, extrai arquivos etc.). Ele também cria workflows relacionados a campanhas recorrentes e periódicas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Empregos em prestadores de serviços</span> <br /> </td> 
   <td> <span class="uicontrol">vendorMgt</span><br /> </td> 
   <td> Esse workflow inicia processos do provedor de serviços (email para o roteador e o pós-processamento) após a aprovação de entregas. <br /> </td> 
  </tr> 
 </tbody> 
</table>

