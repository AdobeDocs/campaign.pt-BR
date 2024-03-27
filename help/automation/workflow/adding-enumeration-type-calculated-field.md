---
product: campaign
title: Adicionar um campo calculado do tipo lista discriminada
description: Saiba como adicionar um campo calculado do tipo lista discriminada
feature: Workflows, Data Management
role: User
exl-id: 4fe2ae81-faa6-4777-a332-70c451bca75b
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 100%

---

# Adicionar um campo calculado do tipo lista discriminada {#adding-an-enumeration-type-calculated-field}

Aqui queremos criar uma consulta com um campo calculado do tipo **[!UICONTROL Enumerations]**. Este campo gerará uma coluna adicional na janela de visualização de dados. Essa coluna especificará os valores numéricos retornados como resultado para cada destinatário (0, 1 e 2). Um gênero será atribuído a cada valor na nova coluna: &quot;Male&quot; para &quot;1&quot;, &quot;Female&quot; para &quot;2&quot; ou &quot;Not indicated&quot; se o valor for igual a &quot;0&quot;.

* Qual tabela precisa ser selecionada?

  A tabela de destinatário (nms:recipient)

* Campos a serem selecionados na coluna de saída?

  Last name, First name, Gender

* Critérios que serão usados para filtrar a informação?

  O idioma do destinatário.

Siga as etapas abaixo:

1. Abra o editor de query genérico e selecione a tabela Destinatário (**[!UICONTROL nms:recipient]**).
1. Na janela **[!UICONTROL Data to extract]**, selecione **[!UICONTROL Last name]**, **[!UICONTROL First name]** e **[!UICONTROL Gender]**.

   ![](assets/query_editor_nveau_73.png)

1. Na janela **[!UICONTROL Sorting]**, clique em **[!UICONTROL Next]**: não é necessária nenhuma classificação para este exemplo.
1. Em **[!UICONTROL Data filtering]**, selecione **[!UICONTROL Filtering conditions]**.
1. Na janela **[!UICONTROL Target element]**, defina uma condição de filtro para coletar destinatários que falam inglês.

   ![](assets/query_editor_nveau_74.png)

1. Na janela **[!UICONTROL Data formatting]**, clique em **[!UICONTROL Add a calculated field]**.

   ![](assets/query_editor_nveau_75.png)

1. Vá para a janela **[!UICONTROL Type]** da janela **[!UICONTROL Export calculated field definition]** e selecione **[!UICONTROL Enumerations]**.

   Defina a coluna a qual o novo campo calculado deve se referir. Para fazer isso, selecione a coluna **[!UICONTROL Gender]** no menu suspenso do campo **[!UICONTROL Source column]**: os valores de destino coincidirão com a coluna **[!UICONTROL Gender]**.

   ![](assets/query_editor_nveau_76.png)

   Defina os valores **Source** e **Destination** : o valor de destino facilita a leitura da query. Esta query deve retornar o sexo do destinatário e o resultado será 0, 1 ou 2.

   Para cada linha &quot;source-destination&quot; a ser inserida, clique em **[!UICONTROL Add]** em **[!UICONTROL List of enumeration values]**:

   * Na coluna **[!UICONTROL Source]**, insira o valor de origem de cada gênero (0,1,2) em uma nova linha.
   * Na coluna **[!UICONTROL Destination]**, digite os valores: &quot;Not indicated&quot; para a linha &quot;0&quot;, &quot;Male&quot; para a linha &quot;1&quot; e &quot;Female&quot; para a linha &quot;2&quot;.

   Selecione a função **[!UICONTROL Keep the source value]**.

   Clique em **[!UICONTROL OK]** para aprovar o campo calculado.

   ![](assets/query_editor_nveau_77.png)

1. Na janela **[!UICONTROL Data formatting]**, clique em **[!UICONTROL Next]**.
1. Na janela da pré-visualização, **[!UICONTROL start the preview of the data]**.

   A coluna adicional define o sexo de 0, 1 e 2:

   * 0 para &quot;Não indicado&quot;
   * 1 para &quot;Masculino&quot;
   * 2 para &quot;Feminino&quot;

   ![](assets/query_editor_nveau_78.png)

   Por exemplo, se você não inserir o gênero &quot;2&quot; em **[!UICONTROL List of enumeration values]** e a função **[!UICONTROL Generate a warning and continue]** do campo **[!UICONTROL In other cases]** for selecionada, você receberá um log de aviso. Este log indica que o sexo &quot;2&quot; (Feminino) não foi digitado. Exibido no campo **[!UICONTROL Logs generated during export]** da janela de pré-visualização de dados.

   ![](assets/query_editor_nveau_79.png)

   Vamos tomar outro exemplo e dizer que o valor de enumeração &quot;2&quot; não é inserido. Selecione a função **[!UICONTROL Generate an error and reject the line]**: todos os gêneros &quot;2&quot; dos destinatários criarão anomalias e as outras informações na linha (nome e sobrenome etc.) não serão exportadas. Um log de erros é exibido no campo **[!UICONTROL Logs generated during export]** da janela de pré-visualização de dados. Este log indica que o valor de enumeração &quot;2&quot; não foi inserido.

   ![](assets/query_editor_nveau_80.png)
