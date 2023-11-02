---
title: Trabalhar com bancos de dados do Campaign e externos (FDA)
description: Saiba como trabalhar com bancos de dados do Campaign e externos
feature: Federated Data Access
role: Admin
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 40%

---

# Federated Data Access (FDA){#gs-fda}

Use o conector FDA (Federated Data Access) para conectar o Campaign a um ou mais **bancos de dados externos** e processar as informações armazenadas neles sem afetar os dados do banco de dados da nuvem do Campaign. Em seguida, é possível acessar dados externos sem alterar a estrutura dos dados do Adobe Campaign.

![](../assets/do-not-localize/speech.png) Como usuário do Managed Cloud Service, [Adobe de contato](../start/campaign-faq.md#support) para conectar seu(s) banco(s) de dados externo(s) ao Campaign.


>[!NOTE]
>
>* Os bancos de dados compatíveis com o Federated Data Access estão listados na [Matriz de compatibilidade](../start/compatibility-matrix.md).
>
>* No contexto de um [Implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), uma conta externa específica está disponível para gerenciar a comunicação entre o banco de dados local do Campaign e o banco de dados da nuvem do Snowflake. Essa conta externa é configurada para você pelo Adobe e **não deve** ser modificadas.
>


## Práticas recomendadas e limitações

A opção FDA está sujeita às limitações do sistema de banco de dados de terceiros que você usa.

Além disso, esteja ciente das seguintes limitações e práticas recomendadas:

* A opção FDA é feita para manipular os dados em bancos de dados externos em modo de lote em workflows. Para evitar problemas de desempenho, não é recomendável usar o módulo FDA no contexto de operações unitárias, como: personalização, interação, mensagens em tempo real etc.

* Evite o máximo possível as operações que precisam usar o banco de dados tanto do Adobe Campaign quanto externo. Para fazer isso, é possível:

   * Exportar o banco de dados do Adobe Campaign para o banco de dados externo e executar as operações somente do banco de dados externo antes de importar novamente os resultados para o Adobe Campaign.

   * Coletar os dados do banco de dados externo do Adobe Campaign e executar as operações no local.

  Se você quiser realizar a personalização de entregas usando dados do banco de dados externo, colete os dados para usar em um workflow para torná-lo disponível em uma tabela temporária. Em seguida, use os dados da tabela temporária para personalizar sua entrega. Para fazer isso, pré-processe a personalização da mensagem em um fluxo de trabalho dedicado usando o **[!UICONTROL Prepare the personalization data with a workflow]** opção, disponível na **[!UICONTROL Analysis]** das propriedades de delivery. Durante a análise de delivery, essa opção cria e executa automaticamente um workflow que armazena todos os dados vinculados ao target em uma tabela temporária, incluindo dados de tabelas vinculadas em um banco de dados externo.

  >[!CAUTION]
  >
  >Essa opção melhora significativamente o desempenho ao executar a etapa de personalização.


## Usar dados externos em um fluxo de trabalho

O Campaign vem com várias atividades de fluxo de trabalho que você pode usar para interagir com dados de seus bancos de dados externos:

* **Filtrar dados externos** - Use o **[!UICONTROL Query]** atividade para adicionar dados externos e usá-los nas configurações de filtro definidas.

* **Criar subconjuntos** - Use o **[!UICONTROL Split]** atividade para criar subconjuntos. Você pode usar dados externos para definir os critérios de filtragem a serem usados.

* **Carregar banco de dados externo** - Use os dados externos no **[!UICONTROL Data loading (RDBMS)]** atividade.

* **Adição de informações e links** - Use o **[!UICONTROL Enrichment]** atividade para adicionar dados à tabela de trabalho do workflow e links para uma tabela externa. Nesse contexto, ele pode usar dados de um banco de dados externo.

Você também pode definir diretamente uma conexão com um banco de dados externo de todas as atividades de workflow listadas acima, para um uso temporário. Nesse caso, ele estará em um banco de dados externo local, para ser usado somente no workflow atual.

>[!CAUTION]
>
>Esse tipo de configuração só deve ser usada temporariamente para coletar dados. A configuração da conta externa deve ser preferida para qualquer outro uso.

Por exemplo, na variável **[!UICONTROL Query]** você pode definir uma conexão temporária com um banco de dados externo da seguinte maneira:

1. Abra a atividade e clique no link **[!UICONTROL Add data...]**
1. Selecione o **[!UICONTROL External data]** opções
1. Selecione o **[!UICONTROL Locally defining the data source]** opção
1. Selecione o mecanismo de banco de dados do Target na lista suspensa. Digite o nome do servidor e forneça os parâmetros de autenticação. Especifique também o nome do banco de dados externo.
1. Selecione a tabela onde os dados estão armazenados. Você pode inserir o nome da tabela diretamente no campo correspondente ou clicar no ícone edição para acessar a lista das tabelas do banco de dados.
1. Clique no botão **[!UICONTROL Add]** para definir um ou vários campos de reconciliação entre os dados do banco de dados externo e os do banco de dados do Adobe Campaign. Os ícones **[!UICONTROL Edit expression]** do **[!UICONTROL Remote field]** e **[!UICONTROL Local field]** fornecem acesso à lista de campos de cada uma das tabelas.
1. Se necessário, especifique uma condição de filtragem e o modo de classificação de dados.
1. Selecione os dados adicionais a serem coletados no banco de dados externo. Para fazer isso, clique duas vezes nos campos que deseja adicionar para exibi-los nas **[!UICONTROL Output columns]**.
1. Clique em **[!UICONTROL Finish]** para confirmar essa configuração.
