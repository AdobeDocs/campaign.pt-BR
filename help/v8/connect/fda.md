---
title: Trabalhar com bancos de dados do Campaign e externos (FDA)
description: Saiba como trabalhar com bancos de dados do Campaign e externos
feature: Federated Data Access
role: Admin
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 36%

---

# Federated Data Access (FDA){#gs-fda}

Use o conector FDA (Federated Data Access) para conectar o Campaign a um ou mais **bancos de dados externos** e processar as informações armazenadas neles sem afetar os dados do banco de dados da nuvem do Campaign. Em seguida, é possível acessar dados externos sem alterar a estrutura dos dados do Adobe Campaign.

>[!NOTE]
>
>* Os bancos de dados compatíveis com o Federated Data Access estão listados na [Matriz de Compatibilidade](../start/compatibility-matrix.md).
>
>* No contexto de uma [implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), uma conta externa específica está disponível para gerenciar a comunicação entre o banco de dados local do Campaign e o banco de dados da nuvem do Snowflake. Esta conta externa foi configurada para você pela Adobe e **não deve** ser modificado.
>
>* Como usuário do Managed Cloud Services, [contate a Adobe](../start/campaign-faq.md#support) para conectar o(s) banco(s) de dados externo(s) com o Campaign.


## Práticas recomendadas e limitações

A opção FDA está sujeita às limitações do sistema de banco de dados de terceiros que você usa.

Além disso, esteja ciente das seguintes limitações e práticas recomendadas:

* A opção FDA é feita para manipular os dados em bancos de dados externos em modo de lote em workflows. Para evitar problemas de desempenho, não é recomendável usar o módulo FDA no contexto de operações unitárias, como: personalização, interação, mensagens em tempo real etc.

* Evite o máximo possível as operações que precisam usar o banco de dados tanto do Adobe Campaign quanto externo. Para fazer isso, é possível:

   * Exportar o banco de dados do Adobe Campaign para o banco de dados externo e executar as operações somente do banco de dados externo antes de importar novamente os resultados para o Adobe Campaign.

   * Coletar os dados do banco de dados externo do Adobe Campaign e executar as operações no local.

  Se você quiser realizar a personalização de entregas usando dados do banco de dados externo, colete os dados para usar em um workflow para torná-lo disponível em uma tabela temporária. Em seguida, use os dados da tabela temporária para personalizar seu delivery. Para fazer isso, pré-processe a personalização da mensagem em um fluxo de trabalho dedicado usando a opção **[!UICONTROL Prepare the personalization data with a workflow]**, disponível na guia **[!UICONTROL Analysis]** das propriedades de entrega. Durante a análise de delivery, essa opção cria e executa automaticamente um workflow que armazena todos os dados vinculados ao target em uma tabela temporária, incluindo dados de tabelas vinculadas em um banco de dados externo.

  >[!CAUTION]
  >
  >Essa opção melhora significativamente o desempenho ao executar a etapa de personalização.


## Usar dados externos em um fluxo de trabalho

O Campaign vem com várias atividades de fluxo de trabalho que você pode usar para interagir com dados de seus bancos de dados externos:

* **Filtrar dados externos** - Use a atividade **[!UICONTROL Query]** para adicionar dados externos e usá-los nas configurações de filtro definidas.

* **Criar subconjuntos** - Use a atividade **[!UICONTROL Split]** para criar subconjuntos. Você pode usar dados externos para definir os critérios de filtragem a serem usados.

* **Carregar banco de dados externo** - Use os dados externos na atividade **[!UICONTROL Data loading (RDBMS)]**.

* **Adicionando informações e links** - Use a atividade **[!UICONTROL Enrichment]** para adicionar dados à tabela de trabalho do fluxo de trabalho e links a uma tabela externa. Nesse contexto, ele pode usar dados de um banco de dados externo.

Você também pode definir diretamente uma conexão com um banco de dados externo de todas as atividades de workflow listadas acima, para um uso temporário. Nesse caso, ele estará em um banco de dados externo local, para ser usado somente no workflow atual.

>[!CAUTION]
>
>Esse tipo de configuração só deve ser usada temporariamente para coletar dados. A configuração da conta externa deve ser preferida para qualquer outro uso.

Por exemplo, na atividade **[!UICONTROL Query]**, é possível definir uma conexão temporária com um banco de dados externo da seguinte maneira:

1. Abra a atividade e clique no link **[!UICONTROL Add data...]**
1. Selecione as opções de **[!UICONTROL External data]**
1. Selecione a opção **[!UICONTROL Locally defining the data source]**
1. Selecione o mecanismo de banco de dados do Target na lista suspensa. Digite o nome do servidor e forneça os parâmetros de autenticação. Especifique também o nome do banco de dados externo.
1. Selecione a tabela onde os dados estão armazenados. Você pode inserir o nome da tabela diretamente no campo correspondente ou clicar no ícone edição para acessar a lista das tabelas do banco de dados.
1. Clique no botão **[!UICONTROL Add]** para definir um ou vários campos de reconciliação entre os dados do banco de dados externo e os do banco de dados do Adobe Campaign. Os ícones **[!UICONTROL Edit expression]** do **[!UICONTROL Remote field]** e **[!UICONTROL Local field]** fornecem acesso à lista de campos de cada uma das tabelas.
1. Se necessário, especifique uma condição de filtragem e o modo de classificação de dados.
1. Selecione os dados adicionais a serem coletados no banco de dados externo. Para fazer isso, clique duas vezes nos campos que deseja adicionar para exibi-los nas **[!UICONTROL Output columns]**.
1. Clique em **[!UICONTROL Finish]** para confirmar essa configuração.
