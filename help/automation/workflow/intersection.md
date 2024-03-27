---
product: campaign
title: Interseção
description: Interseção
feature: Workflows, Targeting Activity
role: User
exl-id: 12777107-5ccc-4f19-9dcd-8f6cade3ee98
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 100%

---

# Interseção{#intersection}



Uma atividade do tipo **intersecção** cria um público alvo a partir da intersecção dos targets recebidos.

Uma intersecção permite extrair somente o público que é comum a todos os resultados da atividade de entrada. O target é criado com todos os resultados recebidos: todas as atividades anteriores devem então ser concluídas antes que a intersecção possa ser executada. Para configurar essa atividade, você precisa inserir um rótulo para ela, bem como as opções referentes ao resultado.

![](assets/s_user_segmentation_inter.png)

Para obter mais informações sobre como configurar e usar a atividade de intersecção, consulte [Extraindo dados conjuntos (Intersecção)](targeting-workflows.md#extracting-joint-data--intersection-).

Marque a opção **[!UICONTROL Generate complement]** se desejar processar o público restante. O complemento conterá a união dos resultados de todas as atividades de entrada menos a intersecção. Uma transição de saída adicional será adicionada à atividade, da seguinte maneira:

![](assets/s_user_segmentation_inter_compl.png)

## Exemplo de intersecção {#intersection-example}

No exemplo a seguir, o objetivo da intersecção é calcular os destinatários comuns em três consultas simples para criar uma lista.

1. Após três queries simples, insira uma atividade do tipo **[!UICONTROL Intersection]**.

   Neste exemplo, os queries direcionam os destinatários homens, que moram em Paris e com idade entre 18 e 30 anos, respectivamente.

1. Configure a intersecção. Para fazer isso, selecione o método de reconciliação **[!UICONTROL Keys only]** desde que as populações resultantes dos queries contenham dados consistentes.
1. Se você tiver fornecido dados adicionais para os queries, poderá optar por manter apenas aqueles compartilhados por destinatários marcando a caixa relevante.
1. Se quiser usar o restante dos dados (em relação aos queries, mas não sua intersecção), marque a caixa **[!UICONTROL Generate complement]**.
1. Adicione uma atividade de atualização da lista após o resultado da intersecção. Você também pode adicionar uma atualização da lista ao complemento que deseja usar.
1. Execute o workflow Aqui, dois destinatários se aplicam a todos os três queries fornecidos ao mesmo tempo. O complemento é composto de cinco destinatários que se aplicam apenas a um ou dois queries.

   O resultado da intersecção é enviado para a atualização da primeira lista. Se você optou usar o complemento, ele também será enviado para a segunda atualização da lista.

   ![](assets/intersection_example.png)

## Parâmetros de entrada {#input-parameters}

* tableName
* schema

Cada evento de entrada deve especificar um target definido por esses parâmetros.

## Parâmetros de saída {#output-parameters}

* tableName
* schema
* recCount

Esse conjunto de três valores identifica o target resultante da intersecção. **[!UICONTROL tableName]** é o nome da tabela que registra os identificadores de target, **[!UICONTROL schema]** é o schema do público (normalmente **[!UICONTROL nms:recipient]**) e **[!UICONTROL recCount]** é o número de elementos na tabela.
