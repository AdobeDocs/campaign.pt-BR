---
product: campaign
title: Ciclo de vida do fluxo de trabalho
description: Saiba mais sobre o ciclo de vida de um fluxo de trabalho
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 4356b90c-9d7c-49ef-88cd-716b2ccdb7f0
TQID: https://experienceleague.adobe.com/lrXuOzmsLhy3AfYLPzKfLd1-IVfB5r9xZZqoMdihYus
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 93%

---

# Ciclo de vida do fluxo de trabalho {#workflow-life-cycle}



O ciclo do fluxo de trabalho tem três etapas principais.

* **Em edição**

  Esta é a fase inicial de design: quando o novo fluxo de trabalho é criado, seu status é &quot;Being edited&quot;. O fluxo de trabalho ainda não foi processado pelo servidor e pode ser modificado sem risco.

* **Iniciado**

  Quando a fase inicial de design for concluída, o fluxo de trabalho poderá ser iniciado. Nesta fase, a instância é tratada pelo servidor e as tarefas individuais são executadas. O fluxo de trabalho ainda pode ser modificado com determinadas precauções.

* **Concluído**

  Um fluxo de trabalho é &#39;Concluído&#39; quando não há mais nenhuma tarefa em andamento ou quando um operador tiver interrompido explicitamente a instância.

Por exemplo, as atividades **Start** e **Delivery** são destacadas enquanto a atividade **Aprovação** pisca no fluxo de trabalho abaixo.

![](assets/new-workflow-6.png)

Isso significa que as duas primeiras atividades foram executadas com êxito e que a aprovação está em andamento, ou seja, foi criada, mas ainda não foi concluída.

Os caracteres **574 -Ok** exibidos acima da transição após a atividade de **Delivery** significam que a preparação da entrega teve 574 destinatários como alvo e que a operação foi concluída com êxito. Essas informações, que são adicionadas às transições quando são executadas, são calculadas pelas atividades que processam dados.

O fluxo de trabalho é iniciado e aguarda um operador pertencente ao grupo especificado na atividade de **Aprovação** para tomar uma decisão. Os operadores pertencentes ao grupo e que têm um endereço de email ou número de celular são notificados.

Para obter mais informações sobre como monitorar o fluxo de trabalho, consulte [esta seção](monitor-workflow-execution.md).
