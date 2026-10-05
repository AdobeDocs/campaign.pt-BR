---
product: campaign
title: Centro de Mensagens (Execução)
description: Centro de Mensagens (Execução)
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 100%
---

# Centro de Mensagens (Execução){#message-center-execution}

Os fluxos de trabalho detalhados abaixo são instalados com o complemento **Centro de Mensagens – Execução** por padrão.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar status do evento</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Esse fluxo de trabalho permite atribuir um status a um evento. Os status do evento são como descritos a seguir:<br /> 
    <ul> 
     <li> <p><strong>Pendente</strong>: o evento está em uma fila. Nenhum modelo de mensagem foi associado a ele.</p> </li> 
     <li> <p><strong>Entrega pendente</strong>: o evento está em uma fila, um modelo de mensagem foi associado a ele e está sendo processado no momento pela entrega.</p> </li> 
     <li> <p><strong>Enviado</strong>: esse status é copiado dos logs de entrega. Significa que a entrega foi enviada.</p> </li> 
     <li> <p><strong>Ignorado pela entrega</strong>: esse status é copiado dos logs de entrega. Significa que a entrega foi ignorada.</p> </li> 
     <li> <p><strong>Erro de entrega</strong>: esse status é copiado dos logs de entrega. Significa que a entrega falhou.</p> </li> 
     <li> <p><strong>Evento não coberto</strong>: o evento falhou ao ser associado a um modelo de mensagem. O evento não será reprocessado.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processamento de eventos em lote</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> Esse fluxo de trabalho permite colocar eventos batch em uma fila antes de associá-los a um modelo de mensagem. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processamento de eventos em tempo real</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> Esse fluxo de trabalho permite colocar eventos em tempo real em uma fila antes de associá-los a um modelo de mensagem. <br /> </td> 
  </tr> 
 </tbody> 
</table>

