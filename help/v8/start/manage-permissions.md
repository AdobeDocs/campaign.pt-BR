---
title: Conceder permissões ao Campaign v8
description: Saiba como conceder permissões a usuários do Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
source-git-commit: b63dc1616bc7ce1387a7bd0590c289b59f11b33f
workflow-type: tm+mt
source-wordcount: '1640'
ht-degree: 40%

---

# Gerenciar permissões do usuário{#manage-permissions}

## Adicionar usuários {#add-users}

Como administrador de produtos, você pode adicionar usuários e conceder acesso ao Campaign.

Para adicionar um usuário, siga as etapas abaixo:

1. No [Admin Console](https://adminconsole.adobe.com/enterprise){target=&quot;_blank&quot;} página inicial, selecione **Adicionar usuários**.

   ![](assets/add-a-user.png)

1. Insira o endereço de email do usuário.
1. Use o sinal de &quot;+&quot; para selecionar os perfis de produto ou grupos de usuários a serem atribuídos ao usuário.

   ![](assets/add-a-product-profile.png)

   Os perfis de produto integrados do Campaign são listados em [esta seção](#ootb-productprofiles).

   Saiba como criar grupos de usuários no [esta seção](#user-groups)

1. Clique em **Save**. O usuário é adicionado e exibido na lista Usuários. Se você atribuir uma função de administrador ou um Perfil de produto aos usuários, eles receberão uma notificação por email. Os usuários devem seguir o link para concluir o perfil.

Saiba mais sobre a criação de usuários no Admin Console [esta página](https://helpx.adobe.com/ie/enterprise/using/manage-users-individually.html){target=&quot;_blank&quot;}.

Quando novos usuários [fazer logon no Campaign](connect.md) com a Adobe ID, eles são adicionados à lista Operadores do Campaign no console do cliente. Os operadores de campanha são armazenados no **[!UICONTROL Administration > Access management > Operators]** pasta do explorador do Campaign.

## Trabalhar com perfis de produto{#product-profiles}

Use perfis de produto para dar aos usuários os recursos incluídos no produto.

* Para cada produto no Admin Console, é possível criar um ou mais perfis de produto.
* Em cada perfil de produto, você atribui usuários e grupos de usuários (na organização).
* Quando um usuário faz logon com as credenciais especificadas no perfil do produto, ele recebe acesso aos aplicativos e serviços do produto no qual o perfil do produto é baseado.

Esses perfis de produto correspondem aos grupos de operadores que são armazenados no **[!UICONTROL Administration > Access management > Operator groups]** pasta do explorador do Campaign.

No Admin Console, os perfis de produtos usam a seguinte sintaxe:

campaign - `<your instance>` - nome interno do grupo de operadores

Por exemplo, para a variável **Operador Delivery** na instância &#39;test&#39;, o perfil de produto no Admin Console é:

campaign - test - delivery

Você pode usar perfis de produto padrão ou criar novos.

### Criar um perfil de produto{#create-product-profile}

Para adicionar um novo perfil de produto ao Adobe, primeiro você deve criá-lo no console do cliente do Campaign e depois adicioná-lo no Admin Console.

Por exemplo, para criar um perfil de produto &quot;revisores&quot;, siga as etapas abaixo.

#### Criar o grupo de operadores no Campaign{#create-op-group}

1. Conecte-se ao Campaign, abra o Explorer e navegue até **[!UICONTROL Administration > Access management > Operator groups]**.
1. Clique em **[!UICONTROL New]**e defina o nome do grupo de operadores e defina seu nome interno (&#39;revisores&#39;).
   ![](assets/new-op-group.png)
1. Defina as permissões associadas selecionando direitos nomeados. Os direitos nomeados são detalhados em [esta seção](#use-named-rights)
1. Salve o novo grupo de operadores.

#### Crie o perfil de produto no Admin Console{#create-profile-in-admin-console}

1. Conecte-se ao [Admin Console](https://adminconsole.adobe.com/enterprise){target=&quot;_blank&quot;}.
1. No **Produtos e serviços** da página inicial, abra o Campaign product.
1. Clique em **Novo perfil** e insira o nome do perfil de produto a ser criado, com a sintaxe exata correta, como explicado [here](#product-profiles). Para nosso exemplo, inserimos: campaign - `<your-instance-name>` - revisores

   ![](assets/new-product-profile-ui.png)

1. Salve as alterações.

Agora você pode adicionar usuários a esse novo perfil de produto, como explicado em [esta seção](#add-users).

A prática recomendada é atribuir perfis de produtos a grupos de usuários. O gerenciamento de permissões por usuário não é um modelo sustentável.


### Perfis de produto e grupos de operadores padrão {#ootb-productprofiles}

O Adobe Campaign vem com **perfis de produto** que são definidas quando o Adobe ativa seu ambiente.

![](assets/ootb-product-profiles.png)

Esses perfis de produto correspondem ao Campaign **grupos de operadores**. Os grupos de operadores padrão e seus [direitos nomeados](#use-named-rights) estão listados abaixo:

1. **[!UICONTROL Administrator]** (administrador)

   Os operadores neste grupo têm acesso total à instância. Os administradores são usuários que podem acessar as partes mais técnicas da interface do usuário.

   Esse grupo contém os seguintes direitos nomeados:

   * **[!UICONTROL ADMINISTRATION]**: direito a executar/criar/editar/excluir qualquer objeto, como workflow, delivery, scripts, etc.

1. **[!UICONTROL Delivery operators]** (entrega)

   Os operadores nesse grupo são responsáveis pelo gerenciamento de deliveries: eles permitem o acesso aos principais recursos necessários para a criação e preparação de deliveries (tipologias de campanha, mapeamentos de delivery, templates padrão, blocos de personalização, etc.).

   Esse grupo contém os seguintes direitos nomeados:

   * **[!UICONTROL PREPARE DELIVERIES]**: Direito de criar, editar e iniciar a análise de delivery,
   * **[!UICONTROL START DELIVERIES]**: Direito de aprovar deliveries anteriormente analisados.

1. **[!UICONTROL Campaign managers]** (operação)

   Os operadores nesse grupo podem gerenciar campanhas de marketing: permite acessar os objetos vinculados às campanhas (planos, programas, workflows, orçamentos, etc.) no âmbito da estrutura de **[!UICONTROL Campaign]** (módulo opcional do Adobe Campaign).

   Esse grupo contém os seguintes direitos nomeados:

   * **[!UICONTROL INSERT FOLDERS]**: direito de inserir pastas à árvore do Adobe Campaign (se você tiver o direito de editar ramificações),
   * **[!UICONTROL WORKFLOW]**: direito de usar workflows.

   >[!NOTE]
   >
   >Esse grupo não permite que os operadores iniciem deliveries.

1. **[!UICONTROL Content contributors]** (conteúdo)

   Os usuários desse grupo podem acessar as pastas Conteúdo, no contexto da variável **[!UICONTROL Content management]** complemento. Este grupo não concede permissões adicionais.

1. **[!UICONTROL Access to reports]** (relatório)

   Esse grupo é reservado para operadores externos, para acessar os relatórios do delivery por meio de um [Acesso à Web](../start/campaign-ui.md#web-browser).

1. **[!UICONTROL Workflow execution]** (workflow)

   O grupo **[!UICONTROL Workflow execution]** permite controlar a execução e a aprovação de workflows para construção de target: o direito nomeado WORKFLOW é mapeado para os operadores deste grupo. É necessário para todas as ações em workflows, além de direitos de acesso aos arquivos de dados. Por padrão, o grupo **[!UICONTROL Workflow execution]** tem acesso somente leitura de arquivos padrão de workflows para construção de target e templates de workflow. Os operadores neste grupo também têm acesso de leitura e gravação para o arquivo de aprovação pendente.

1. **[!UICONTROL Workflow supervisors]** (workflowSupervisor)

   Os usuários desse grupo gerenciam aprovações de workflow e recebem uma notificação por email no caso de alertas relativos aos workflows da campanha.

1. **Gerenciamento local / central** (central/local)

   Os usuários deste grupo podem usar **[!UICONTROL Distributed marketing]** complemento.

1. **[!UICONTROL Offer managers]** (oferta)

   Os operadores nesse grupo podem criar e manter ofertas ao usar o complemento Interaction. [Saiba mais](../interaction/interaction-operators.md).

   Esse grupo contém os seguintes direitos nomeados:

   * **[!UICONTROL INSERT FOLDERS]**: direito de inserir pastas à árvore do Adobe Campaign (se você tiver o direito de editar ramificações),
   * **[!UICONTROL EDIT FOLDERS]**: direito de alterar as propriedades da pasta, como nome interno, rótulo, imagem associada, pedido de subpastas etc.

   As permissões atribuídas aos gerentes de oferta permitem que eles executem as seguintes tarefas:

   * Modificar ambientes **[!UICONTROL Design]**.
   * Visualizar ambientes **[!UICONTROL Live]**.
   * Configurar funções de administração (espaços e filtros predefinidos).
   * Criar e atualizar categorias.
   * Criar ofertas.
   * Configurar a qualificação para a oferta.
   * Aprovar ofertas.

   >[!NOTE]
   >
   >**Gerentes de oferta** só pode aprovar uma oferta se nenhum revisor for especificado, ou se tiverem sido definidos como revisores no template de oferta.

   A matriz de permissões do gerente de ofertas por ambiente está disponível em [esta página](../interaction/interaction-operators.md#recap-of-rights-according-to-operator).

## Trabalhar com grupos de usuários{#user-groups}

Você pode usar o Admin Console para criar grupos de usuários e atribuir usuários a eles.

Um grupo de usuários é uma coleção de usuários diferentes que precisam receber um conjunto compartilhado de permissões. Saiba como criar grupos de usuários no [esta seção](https://helpx.adobe.com/ie/enterprise/using/user-groups.html){target=&quot;_blank&quot;}.

Você pode atribuir perfis de produtos a grupos de usuários. Assim, todos os usuários desse grupo receberão o mesmo conjunto de permissões de produto.

## Direitos nomeados{#use-named-rights}

O Adobe Campaign vem com um conjunto de direitos nomeados que permitem definir as permissões atribuídas a usuários e grupos de usuários. Esses direitos podem ser editados no **[!UICONTROL Administration > Access management > Named rights]** pasta do explorador do Campaign.

Permissões de concessão de direitos nomeados para:

* Executar operações Por exemplo, a variável **Analisar** no Editor de delivery é ativado para membros do **Operador Delivery** grupo que tem o **Preparar entrega** Nomeado à direita

* Acesso a pastas A associação de grupos de operadores pode conceder ou restringir direitos de acesso a pastas, alterando as configurações de segurança em pastas. [Saiba mais](folder-permissions.md#restrict-access-to-a-folder).

   Por exemplo, pode afetar: **Acesso de gravação** para criar novas entidades (como deliveries, perfis etc.), **Acesso de leitura** para usar entidades, **Excluir acesso** para excluir entidades.

Os direitos nomeados padrão no Adobe Campaign são:

* **[!UICONTROL ADMINISTRATION]**: operadores com o direito **[!UICONTROL ADMINISTRATION]** têm acesso total na instância. Os usuários administradores podem executar/criar/editar/excluir qualquer objeto, como workflow, delivery, scripts etc.

* **[!UICONTROL APPROVAL ADMINISTRATION]**: é possível definir várias etapas de aprovação em workflows e deliveries para garantir que o estado atual tenha sido aprovado por um operador ou grupo atribuído. Os usuários com o direito **[!UICONTROL APPROVAL ADMINISTRATION]** podem definir etapas de aprovação e também atribuir um operador ou grupo de operadores que devem aprovar essas etapas.

* **[!UICONTROL CENTRAL]**: direito de gerenciamento central (marketing distribuído).

* **[!UICONTROL DELETE FOLDER]**: direito de excluir pastas. Com esse direito, os usuários podem excluir pastas da visualização do explorador.

* **[!UICONTROL EDIT FOLDERS]**: direito de alterar as propriedades da pasta, como nome interno, rótulo, imagem associada, pedido de subpastas etc.

* **[!UICONTROL EXPORT]**: os usuários podem exportar dados de suas instâncias do Adobe Campaign para um arquivo no servidor ou computador local usando a atividade de workflow **[!UICONTROL EXPORT]**.

* **[!UICONTROL FILES ACCESS]**: direito de ler e gravar o acesso de arquivos por meio de um script que pode ser gravado na atividade de workflow **[!UICONTROL JavaScript]** para arquivos de leitura/gravação em um servidor.

* **[!UICONTROL IMPORT]**: direito de importação de dados genéricos. **[!UICONTROL IMPORT]** permite importar dados para qualquer outra tabela, enquanto o direito **[!UICONTROL RECIPIENT IMPORT]** permite importar somente para a tabela do recipient.

* **[!UICONTROL INSERT FOLDERS]**: direito de inserir pastas. Os usuários com o direito **[!UICONTROL INSERT FOLDERS]** podem criar novas pastas na árvore de pastas na visualização do explorador.

* **[!UICONTROL LOCAL]**: direito para gerenciamento local (marketing distribuído).

* **[!UICONTROL MERGE]**: direito de unir os registros selecionados em um. Se houver recipients duplicados, o direito **[!UICONTROL MERGE]** permitirá que o usuário selecione os duplicados e os mescle em um recipient primário.

* **[!UICONTROL PREPARE DELIVERIES]**: direito de criar, editar e salvar um delivery. Os usuários com o direito **[!UICONTROL PREPARE DELIVERIES]** também podem iniciar o processo de análise do delivery.

* **[!UICONTROL PRIVACY DATA RIGHT]**: direito de coletar e excluir dados de privacidade. [Saiba mais](privacy.md).

* **[!UICONTROL PROGRAM EXECUTION]**: direito de executar comandos em várias linguagens de programação.

* **[!UICONTROL RECIPIENT IMPORT]**: direito de importar recipients. Os usuários com o direito **[!UICONTROL RECIPIENT IMPORT]** podem importar um arquivo local para a tabela do recipient.

* **[!UICONTROL SQL SCRIPT EXECUTION]** Direito de executar qualquer comando SQL diretamente no banco de dados.

* **[!UICONTROL START DELIVERIES]**: Direito de aprovar deliveries anteriormente analisados. Após a análise, o delivery pausará em várias etapas de aprovação e precisará ser aprovado para retomar. Os usuários com o direito **[!UICONTROL START DELIVERIES]** podem aprovar deliveries.

* **[!UICONTROL USE SQL DATA MANAGEMENT ACTIVITY]**: Direito de escrever seus próprios scripts SQL usando a atividade de Gestão de Dados SQL, para criar e preencher tabelas de trabalho. [Saiba mais](../../automation/workflow/sql-data-management.md).

* **[!UICONTROL WORKFLOW]**: Esse direito nomeado é específico para workflows: ele permite criar, iniciar e parar workflows. Os direitos de leitura no arquivo de workflow são necessários para que o direito nomeado seja aplicável. Para workflows para construção do target, a leitura no campo **[!UICONTROL Profiles and Targets]** é necessária.


* **[!UICONTROL WEBAPP]**: direito de usar aplicações web.

>[!NOTE]
>
>Essa lista pode ser diferente dependendo dos complementos instalados no seu ambiente.



## Recursos adicionais{#additional-res}

* [Gerenciar permissões para workflows](../../automation/workflow/managing-rights.md)
* [Gerenciar permissões para marketing distribuído](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [Gerenciar permissões do módulo de interação](../interaction/interaction-operators.md)
* [Filtrar o acesso a esquemas](../dev/filter-schema.md)
* [Restringir visualização de IP](../dev/restrict-pi-view.md)
