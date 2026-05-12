---
product: campaign
title: Extração de dados (arquivo)
description: Saiba mais sobre a atividade de fluxo de trabalho de extração de dados (arquivo)
feature: Workflows, Data Management Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8510e879-2862-491f-bc52-ca8f56105932
TQID: https://experienceleague.adobe.com/ZTuore2mgh5eLsp9YNJJ2Gzh2Np3KAPz57E-LEMGZU4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 315
ht-degree: 100%

---

# Extração de dados (arquivo){#extraction-file}

Você pode extrair dados de uma tabela de fluxo de trabalho em um arquivo externo usando a atividade **[!UICONTROL Data extraction (file)]**.

>[!CAUTION]
>
>Essa atividade sempre deve ter uma transição de entrada que contenha os dados a serem extraídos.

Para configurar a extração de dados, siga as seguintes etapas:

1. Especifique o nome do arquivo de output: esse nome pode conter variáveis, inseridas por meio do botão de personalização à direita do campo.
1. Clique em **[!UICONTROL Edit the file format...]** para selecionar os dados que serão extraídos.

   ![](assets/s_advuser_extract_file_param.png)

   A opção **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** adiciona uma etapa extra para filtrar o resultado final do agregado, por exemplo, em um determinado tipo de pedido, clientes que fizeram mais de 10 pedidos, etc.

1. Se necessário, você pode adicionar novas colunas ao arquivo de output, como, por exemplo, computar ou processar resultados. Para fazer isso, clique no ícone **[!UICONTROL Add]**.

   ![](assets/s_advuser_extract_file_add_col.png)

   Na linha adicional, clique no ícone **[!UICONTROL Edit expression]** para definir o conteúdo da nova coluna.

   ![](assets/s_advuser_extract_file_add_exp.png)

   Você então acessará a janela de seleção. Clique em **[!UICONTROL Advanced selection]** para escolher o processo a ser aplicado aos dados.

   ![](assets/s_advuser_extract_file_advanced_selection.png)

   Escolha a fórmula desejada na lista.

   ![](assets/s_advuser_extract_file_agregate_values.png)

Você pode definir um pós-processo que será executado durante a extração de dados, permitindo a compactação ou criptografia dos arquivos. Para fazer isso, o comando desejado deve ser adicionado na guia da atividade **[!UICONTROL Script]**.

![](assets/postprocessing_dataextraction.png)

## Lista de funções agregadas {#list-of-aggregate-functions}

Veja a seguir uma lista de funções agregadas disponíveis:

* **[!UICONTROL Count]** para contar todos os valores não nulos do campo a ser agregado, incluindo valores duplicados (do campo de agregação),

  **[!UICONTROL Distinct]** para contar o número total de valores diferentes e não nulos do campo a ser agregado (valores duplicados são excluídos antes do cálculo),

* **[!UICONTROL Sum]** para calcular a soma dos valores de um campo numérico,
* **[!UICONTROL Minimum value]** para calcular os valores mínimos de um campo (numérico ou não),
* **[!UICONTROL Maximum value]** para calcular os valores máximos de um campo (numérico ou não),
* **[!UICONTROL Average]** para calcular a média dos valores de um campo numérico.
