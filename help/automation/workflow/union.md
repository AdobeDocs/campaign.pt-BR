---
product: campaign
title: União
description: Saiba mais sobre a atividade do workflow de união
feature: Workflows, Targeting Activity
version: Campaign v8, Campaign Classic v7
exl-id: 4109e198-bf9d-4dd2-92a1-16bbadbe30e8
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 84%

---

# União{#union}

Um **[!UICONTROL Union]** agrupa o resultado de várias atividades de entrada em um único público-alvo. O target é criado com todos os resultados recebidos: todas as atividades anteriores devem então ser concluídas para que a união seja executada.

![](assets/s_user_segmentation_union.png)

>[!NOTE]
>
>Para obter mais informações sobre como configurar e usar a atividade **[!UICONTROL Union]**, consulte [esta página](targeting-workflows.md#combining-several-targets--union-).

## Exemplo de união {#union-example}

No exemplo a seguir, os resultados de dois queries foram combinados para atualizar a lista. Os dois queries têm os destinatários como alvo. Os resultados são então baseados na mesma tabela.

1. Insira uma atividade do tipo **[!UICONTROL Union]** diretamente após os dois queries e antes de uma atividade do tipo atualização da lista, e depois a abra.
1. Você pode inserir um rótulo.
1. Selecione o método de reconciliação **[!UICONTROL Keys only]**, pois, neste exemplo, a população resultante dos queries contém dados consistentes.
1. Se você tiver inserido dados adicionais para os queries, pode manter apenas os dados compartilhados.
1. Se quiser limitar o tamanho da população final, marque a opção **[!UICONTROL Limit size of generated population]**.

   Especifique este número final inserindo o número máximo de destinatários e selecionando o query cuja população terá prioridade.

1. Aprove a atividade **[!UICONTROL Union]** e configure a atividade [List update](list-update.md).
1. Inicie o workflow. O número de resultados é exibido e a lista definida na atividade de atualização da lista é criada ou atualizada. Esta lista contém o conjunto de destinatários para queries ou, onde aplicável, o número definido na etapa anterior.

   ![](assets/union_example.png)

## Parâmetros de entrada {#input-parameters}

* tableName
* schema

Cada evento de entrada deve especificar um target definido por esses parâmetros.

## Parâmetros de saída {#output-parameters}

* tableName
* schema
* recCount

Esse conjunto de três valores identifica o target resultante da união. **[!UICONTROL tableName]** é o nome da tabela que registra os identificadores de target, **[!UICONTROL schema]** é o schema do população (normalmente nms:recipient) e **[!UICONTROL recCount]** é o número de elementos na tabela.
