---
product: campaign
title: Centro de Mensagens (Execução)
description: Centro de Mensagens (Execução)
feature: Workflows
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 100%

---


# Centro de Mensagens (Execução){#message-center-execution}

Os workflows detalhados abaixo são instalados com o complemento **Centro de Mensagens – Execução** por padrão.

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
   <td> Esse workflow permite atribuir um status a um evento. Os status do evento são como descritos a seguir:<br /> 
    <ul> 
     <li> <p><strong>Pendente</strong>: o evento está em uma fila. Nenhum template de mensagem foi associado a ele.</p> </li> 
     <li> <p><strong>Delivery pendente</strong>: o evento está em uma fila, um template de mensagem foi associado a ele e está sendo processado no momento pelo delivery.</p> </li> 
     <li> <p><strong>Enviado</strong>: esse status é copiado dos logs de delivery. Significa que o delivery foi enviado.</p> </li> 
     <li> <p><strong>Ignorado pelo delivery</strong>: esse status é copiado dos logs de delivery. Significa que o delivery foi ignorado.</p> </li> 
     <li> <p><strong>Erro de delivery</strong>: esse status é copiado dos logs de delivery. Significa que o delivery falhou.</p> </li> 
     <li> <p><strong>Evento não coberto</strong>: o evento falhou ao ser associado a um template de mensagem. O evento não será reprocessado.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processamento de eventos em lote</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> Esse workflow permite colocar eventos batch em uma fila antes de associá-los a um template de mensagem. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processamento de eventos em tempo real</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> Esse workflow permite colocar eventos em tempo real em uma fila antes de associá-los a um template de mensagem. <br /> </td> 
  </tr> 
 </tbody> 
</table>

