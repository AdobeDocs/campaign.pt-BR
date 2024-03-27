---
product: campaign
title: Atualizar lista
description: Atualizar lista
feature: Workflows, Targeting Activity
role: User
exl-id: abb7f777-0b4a-4bf2-bcb6-32264f340a58
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 98%

---

# Atualizar lista{#list-update}



Uma atividade **List update** armazena a população especificada na transição em uma lista de destinatários.

![](assets/s_user_segmentation_update_group.png)

A lista pode ser selecionada na lista de grupos existentes.

Ele também pode ser criado por meio das opções **[!UICONTROL Create the list if necessary (Computed name)]** e **[!UICONTROL Create the list if necessary (Computed Folder and Name)]**. Essas opções permitem selecionar o rótulo de sua escolha para criar uma lista e, posteriormente, a pasta na qual ela será salva. O rótulo também pode ser gerado automaticamente inserindo campos dinâmicos ou um script. Os diferentes campos dinâmicos estão disponíveis no menu pop-up à direita do rótulo.

![](assets/s_user_segmentation_update_list_calc.png)

Se a lista já existe, os destinatários são adicionados ao conteúdo existente, a menos que a opção **[!UICONTROL Purge the list if it exists (otherwise add to the list)]** esteja habilitada. Nesse caso, o conteúdo da lista é excluído antes da atualização.

Se desejar que a lista criada ou atualizada use uma tabela diferente da tabela destinatário, marque a opção **[!UICONTROL Create or use a list with its own table]**.

Para usar a opção, as tabelas específicas devem ter sido configuradas em sua instância do Adobe Campaign.

Geralmente, salvar um target em uma lista marca o final de um workflow. Por padrão, a atividade **[!UICONTROL List update]** não tem uma transição de saída. Marque a opção **[!UICONTROL Generate an outbound transition]** para adicionar uma.

![](assets/do-not-localize/how-to-video.png) [Descubra como criar uma lista de recipients pelo Explorer em vídeo](#video)

## Exemplo: atualização de lista {#example--list-update}

No exemplo a seguir, a atividade de atualização da lista segue uma query direcionada a homens com mais de 30 anos vivendo na França. A lista será inicialmente criada a partir dos resultados da query. Ela será atualizada sempre que for iniciada a partir do workflow. Ela pode, por exemplo, ser usada regularmente para ofertas promocionais direcionadas em campanhas.

1. Adicione um **[!UICONTROL list update activity]** diretamente após uma consulta, depois abra-a para editá-la.

   Para obter mais informações sobre como criar uma consulta em um workflow, consulte [Query](query.md).

1. É possível selecionar um rótulo para a atividade.
1. Selecione a opção **[!UICONTROL Create the list if necessary (Calculated name)]** para mostrar que a lista é criada quando o primeiro workflow é executado e, em seguida, atualizada com as execuções seguintes.
1. Selecione a pasta na qual deseja salvar a lista.
1. Insira um rótulo para a lista. É possível inserir campos dinâmicos para gerar automaticamente o nome a partir da lista. Neste exemplo, a lista tem o mesmo nome que a query para identificar facilmente seu conteúdo.
1. Deixe a opção **[!UICONTROL Purge the list if it exists (otherwise add to the list)]** marcada para excluir os destinatários que não correspondem aos critérios de direcionamento e para inserir os novos na lista.
1. Deixe a opção **[!UICONTROL Create or use a list with its own table]** também marcada.
1. Deixe a opção **[!UICONTROL Generate an outbound transition]** desmarcada.
1. Clique em **[!UICONTROL Ok]** e inicie o workflow.

   ![](assets/s_user_segmentation_update_list_calc_example.png)

   A lista de destinatários correspondentes é então criada ou atualizada.

## Parâmetros de entrada {#input-parameters}

* tableName
* schema

Identifica a população a ser salva no grupo.

## Parâmetros de saída {#output-parameters}

* groupId: Identificador de grupo.

## Tutorial em vídeo {#video}

Este vídeo mostra como criar uma lista de destinatários pelo Explorer.

>[!VIDEO](https://video.tv.adobe.com/v/25602/quality=12)

Vídeos extras explicativos do Campaign estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.