---
product: campaign
title: Campanha
description: Campanha
feature: Workflows
role: User, Admin
topic-tags: technical-workflows
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 100%

---


# Campanha{#campaign}

Os workflows detalhados abaixo são instalados com o módulo **Campaign** por padrão.

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
   <td> Esse workflow inicia o cálculo das linhas de despesas e custos nos orçamentos, planos, programas, campanhas, deliveries e tarefas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Stock: Orders and alerts</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span><br /> </td> 
   <td> Este workflow inicia o cálculo de estoque nas linhas de pedido e gerencia os limites de aviso.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Empregos em deliveries em campanhas</span><br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span><br /> </td> 
   <td> Esse workflow aciona os deliveries aprovados e inicia o pós-processamento no provedor de serviços para um delivery externo. Também envia notificações e lembretes de aprovação.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Campaign jobs</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span><br /> </td> 
   <td> Esse workflow gerencia as tarefas para campanhas de marketing (inicia o target, extrai arquivos etc.). Ele também cria workflows relacionados a campanhas recorrentes e periódicas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Empregos em prestadores de serviços</span> <br /> </td> 
   <td> <span class="uicontrol">vendorMgt</span><br /> </td> 
   <td> Esse workflow inicia processos do provedor de serviços (email para o roteador e o pós-processamento) após a aprovação de deliveries. <br /> </td> 
  </tr> 
 </tbody> 
</table>

