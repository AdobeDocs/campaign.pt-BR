---
product: campaign
title: União
description: Saiba mais sobre a atividade do workflow de união
feature: Workflows, Targeting Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 84%

---

# União{#union}

A **[!UICONTROL Union]** agrupa o resultado de várias atividades de entrada em um único target. O target é criado com todos os resultados recebidos: todas as atividades anteriores devem então ser concluídas para que a união seja executada.

![](assets/s_user_segmentation_union.png)

>[!NOTE]
>
>Para obter mais informações sobre como configurar e usar o **[!UICONTROL Union]** atividade , consulte [esta página](targeting-workflows.md#combining-several-targets--union-).

## Exemplo de união {#union-example}

No exemplo a seguir, os resultados de dois queries foram combinados para atualizar a lista. Os dois queries têm os recipients como alvo. Os resultados são então baseados na mesma tabela.

1. Insira uma atividade do tipo **[!UICONTROL Union]** diretamente após os dois queries e antes de uma atividade do tipo atualização da lista, e depois a abra.
1. Você pode inserir um rótulo.
1. Selecione o método de reconciliação **[!UICONTROL Keys only]**, pois, neste exemplo, o público resultante dos queries contém dados consistentes.
1. Se você tiver inserido dados adicionais para os queries, pode manter apenas os dados compartilhados.
1. Se desejar limitar o tamanho do público final, verifique o **[!UICONTROL Limit size of generated population]** opção.

   Especifique este número final inserindo o número máximo de recipients e selecionando o query cujo público terá prioridade.

1. Aprove o **[!UICONTROL Union]** e configure a variável [Atualizar lista](list-update.md) atividade .
1. Inicie o workflow. O número de resultados é exibido e a lista definida na atividade de atualização da lista é criada ou atualizada. Esta lista contém o conjunto de recipients para queries ou, onde aplicável, o número definido na etapa anterior.

   ![](assets/union_example.png)

## Parâmetros de entrada {#input-parameters}

* tableName
* schema

Cada evento de entrada deve especificar um target definido por esses parâmetros.

## Parâmetros de saída {#output-parameters}

* tableName
* schema
* recCount

Esse conjunto de três valores identifica o target resultante da união. **[!UICONTROL tableName]** é o nome da tabela que registra os identificadores de target, **[!UICONTROL schema]** é o schema do público (normalmente nms:recipient) e **[!UICONTROL recCount]** é o número de elementos na tabela.
