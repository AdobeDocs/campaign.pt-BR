---
title: Criar filtros no Adobe Campaign
description: Saiba como filtrar os dados e salvar filtros no Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 873578f6-6af9-4d0c-8df3-cce320fc6a4e
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '1638'
ht-degree: 33%

---

# Criar e gerenciar filtros{#create-filters}

A filtragem de dados é o processo de selecionar uma parte menor do conjunto de dados, apenas os registros que correspondem a determinados critérios e o uso desse subconjunto para ações específicas (atualizações, criação de públicos-alvo) ou análise.

Ao navegar pelo Campaign a partir do **[!UICONTROL Explorer]**, os dados são exibidos em listas. Você pode usar filtros internos existentes para acessar um subconjunto específico desses dados: endereços em quarentena, recipients não alvos, um intervalo de idades específico ou data de criação, por exemplo.

Você também pode criar seus próprios filtros, salvá-los para uso futuro ou compartilhá-los com outros usuários do Campaign.

A configuração de filtro permite selecionar dados de uma lista **[!UICONTROL dynamically]**: quando os dados são modificados, os dados filtrados são atualizados.

>[!NOTE]
>
>As configurações da interface do usuário são definidas localmente no nível do dispositivo. Às vezes, poderá ser necessário limpar esses dados, principalmente se surgirem problemas ao atualizar dados. Para fazer isso, use o menu **[!UICONTROL File > Clear the local cache]**.

Os seguintes tipos de filtro estão disponíveis no Adobe Campaign:

## Filtros predefinidos{#predefined-filters}

Os filtros predefinidos estão disponíveis no **Filtros** acima de cada lista.

Por exemplo, para os perfis, os seguintes filtros incorporados estão disponíveis:

![](assets/built-in-filters.png)

Você pode acessar os detalhes dos filtros na **[!UICONTROL Profiles and Targets > Pre-defined filters]** do Explorer.

>[!NOTE]
>
>Para todas as outras listas de dados, os filtros predefinidos são armazenados no  **[!UICONTROL Administration > Configuration > Predefined filters]** nó .

Selecione um filtro para exibir sua definição.

![](assets/predefined-filter-list.png)

Use a última guia para visualizar os dados filtrados.

![](assets/built-in-filter-preview.png)


Os filtros predefinidos incorporados são:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Query</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Aberto<br /> </td> 
   <td> Seleciona destinatários que abriram um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberto, mas não clicado<br /> </td> 
   <td> Seleciona destinatários que abriram um delivery, mas não clicaram em um link.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatários inativos<br /> </td> 
   <td> Seleciona destinatários que não abriram um delivery em X meses.<br /> </td> 
  </tr> 
  <tr> 
   <td> Última atividade por tipo de dispositivo<br /> </td> 
   <td> Seleciona destinatários que clicaram em ou abriram delivery Y usando o dispositivo X nos últimos Z dias.<br /> </td> 
  </tr> 
  <tr> 
   <td> Última atividade por tipo de dispositivo (rastreamento)<br /> </td> 
   <td> Seleciona destinatários que clicaram em ou abriram delivery Y usando o dispositivo X nos últimos Z dias.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatários não direcionados<br /> </td> 
   <td> Seleciona destinatários que nunca foram direcionados por canal Y em X meses.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatários muito ativos<br /> </td> 
   <td> Seleciona destinatários que clicaram em um delivery pelo menos X vezes nos últimos Y meses.<br /> </td> 
  </tr> 
  <tr> 
 <td> Incluir endereço de email na lista de bloqueios<br /> </td> 
    <td> Seleciona os recipients cujo endereço de email está na lista de bloqueios.<br/> </td>
  </tr> 
  <tr> 
   <td> Endereço de email na quarentena<br /> </td> 
   <td> Seleciona destinatários cujo endereço de email está em quarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Endereços de email duplicados na pasta<br /> </td> 
   <td> Seleciona destinatários cujo endereço de email está duplicado na pasta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Não aberto nem clicado<br /> </td> 
   <td> Seleciona destinatários que não abriram ou não clicaram em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Novos destinatários (dias)<br /> </td> 
   <td> Seleciona destinatários que foram criados nos últimos X dias.<br /> </td> 
  </tr> 
  <tr> 
   <td> Novos destinatários (minutos)<br /> </td> 
   <td> Seleciona destinatários que foram criados nos últimos X minutos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Novos destinatários (meses)<br /> </td> 
   <td> Seleciona destinatários que foram criados nos últimos X meses.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por assinatura<br /> </td> 
   <td> Seleciona destinatários por assinatura.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ao clicar em um link específico<br /> </td> 
   <td> Seleciona destinatários que clicaram em um determinado URL em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por comportamento pós-delivery<br /> </td> 
   <td> Seleciona destinatários de acordo com seu comportamento após receber um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por data de criação<br /> </td> 
   <td> Seleciona destinatários por data de criação, por um período variando de X meses (data atual menos n meses) para Y meses (data atual menos n meses).<br /> </td> 
  </tr> 
  <tr> 
   <td> Por lista<br /> </td> 
   <td> Seleciona destinatários por lista.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por número de cliques<br /> </td> 
   <td> Seleciona destinatários que clicaram em um delivery nos últimos X meses.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por número de mensagens recebidas<br /> </td> 
   <td> Seleciona destinatários de acordo com o número de mensagens recebidas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por número de aberturas<br /> </td> 
   <td> Seleciona destinatários que abriram deliveries entre X e Y ao longo da quantidade Z de tempo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por nome ou email<br /> </td> 
   <td> Seleciona destinatários de acordo com seu nome ou email.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por faixa etária<br /> </td> 
   <td> Seleciona destinatários de acordo com sua idade.<br /> </td> 
  </tr> 
 </tbody> 
</table>


### Filtros padrão{#default-filters}

Os campos acima de cada lista permitem usar a variável **filtro padrão predefinido** para esta lista. Para a lista de recipients, você pode filtrar o nome e o endereço de email por padrão.

![](assets/filter-recipient-name.png)


>[!NOTE]
>
>O caractere **%** substitui qualquer cadeia de caracteres. Por exemplo, insira `%@gmail.com` no campo Email para exibir todos os perfis com um endereço Gmail. Enter `%@L` no campo Last name para exibir todos os perfis com um L em seu sobrenome.

Para alterar o filtro padrão de uma lista de destinatários, navegue até o **[!UICONTROL Profiles and Targets > Predefined filters]** nó .

Para todos os outros tipos de dados, configure o filtro padrão por meio do nó **[!UICONTROL Administration > Configuration > Predefined filters]**.

Siga as etapas abaixo:

1. Selecione o filtro que deseja usar como padrão.
1. Clique na guia **[!UICONTROL Parameters]** e selecione **[!UICONTROL Default filter for the associated document type]**.

   ![](assets/change-default-filter.png)

1. Desmarque a mesma opção para o filtro predefinido padrão atual.
1. Clique em **[!UICONTROL Save]** para aplicar o filtro.
1. Navegue até a pasta Recipient e clique no link **[!UICONTROL Remove this filter]** ícone à direita do filtro atual: o novo filtro padrão está disponível.
   ![](assets/updated-default-filter.png)


## Filtros rápidos{#quick-filters}

Usar e combinar **Filtros rápidos** para definir filtros em campos específicos.

Depois de adicionados, os campos de filtro rápido são exibidos acima da lista de dados, um após o outro. Eles podem ser excluídos de maneira independente.

Os filtros rápidos são específicos para cada operador e são reiniciados cada vez que o operador limpa o cache do console do cliente.

Se precisar reutilizar um filtro, crie um **filtro avançado** e salve-o. [Saiba mais](#advanced-filters).

Para criar um **filtro rápido** siga as etapas:

1. Clique com o botão direito do mouse no campo que deseja filtrar e selecione **[!UICONTROL Filter on this field]**.

   ![](assets/quick-filter-on-this-field.png)

   Os campos de filtro padrão são exibidos acima da lista.

   ![](assets/quick-filter-above-list.png)

1. Selecione as opções de filtro.
1. Se necessário, use o ícone cinza no lado direito de um filtro para removê-lo.
1. Você pode combinar filtros para refinar seu filtro.

   ![](assets/add-filter-above-the-list.png)


Se você precisar filtrar em um campo que não está disponível no formulário, em colunas e filtrar nessa coluna. Para fazer isso,

1. Clique no ícone **[!UICONTROL Configure list]**.

   ![](assets/configure-list.png)

1. Selecione a coluna a ser exibida, por exemplo, a idade dos recipients, e clique em **Ok**.

   ![](assets/add-age-column.png)

1. Clique com o botão direito do mouse na coluna **Age** na lista de destinatários, e depois selecione **[!UICONTROL Filter on this column]**.

   ![](assets/age-filter-on-this-column.png)

   Em seguida, é possível selecionar as opções de filtragem por idade. Adicione outro filtro à página para definir um intervalo.

   ![](assets/filter-on-age.png)

## Filtros avançados{#advanced-filters}

Combinar critérios complexos em **Filtros avançados**. Use esses filtros para criar uma consulta complexa ou uma combinação de consultas sobre seus dados. Esses filtros podem ser salvos e compartilhados com outros usuários do Campaign.

### Criar um filtro avançado{#create-adv-filters}

Para criar um **filtro avançado**, clique no botão **[!UICONTROL Filters]** e selecione **[!UICONTROL Advanced filter...]**.

![](assets/adv-filter.png)

Além disso, é possível clicar com o botão direito do mouse na lista de dados e selecionar **[!UICONTROL Advanced filter...]**.

Defina as condições do filtro. No exemplo abaixo, você filtrará os recipients cujo número de conta não inicia com NL e que vivem em Paris ou Los Angeles.

1. Clique no botão **[!UICONTROL Edit expression]** ícone da **[!UICONTROL Expression]** coluna.

   ![](assets/edit-exp.png)

1. Selecione o campo no qual deseja filtrar.
1. Selecione o operador a ser aplicado na lista suspensa .

   ![](assets/select-operator.png)

1. Selecione um valor esperado na coluna **[!UICONTROL Value]**. Você pode combinar vários filtros para refinar seu query. Para adicionar uma condição de filtro, clique em **[!UICONTROL Add]**.

   ![](assets/add-an-exp.png)

   >[!NOTE]
   >
   >É possível atribuir uma hierarquia para as expressões ou alterar a ordem das expressões de query utilizando as setas da barra de ferramentas.

1. Três operadores estão disponíveis para combinar expressões:  **E**, **Ou**, **Exceto**. Clique na seta para alternar para **Ou**.

   ![](assets/select-or-operator.png)

1. Clique em **[!UICONTROL Ok]** para criar o filtro e aplicá-lo à lista atual.

O filtro aplicado é exibido acima da lista.

![](assets/adv-filter-link.png)

Para editar ou modificar esse filtro, clique no link de descrição em azul, acima da lista.


### Salvar um filtro avançado{#save-adv-filters}

Você pode salvar um filtro avançado como um  [filtro predefinido](#predefined-filters), para que você possa reutilizá-la e compartilhá-la com outros usuários do Campaign.

Para salvar um filtro avançado, siga as etapas abaixo:

1. Clique na descrição do filtro para editá-lo.
1. Clique no botão **[!UICONTROL Save as filter]** na seção superior direita da janela.

   ![](assets/save-as-filter.png)

1. Insira um nome para esse filtro e salve-o.

   ![](assets/application-filter-save.png)

O filtro é adicionado ao [filtros predefinidos](#predefined-filters). Ele pode ser atualizado a partir desse nó.

![](assets/added-to-predefined-filters.png)

>[!NOTE]
>
>É possível adicionar um atalho para o filtro ativar pelo teclado.



Esse filtro também está disponível nos filtros predefinidos da lista de recipients.

![](assets/access-to-new-predefined-filter.png)



### Usar um filtro para definir um segmento {#filter-as-segment}

Você pode usar e combinar filtros para criar um segmento de população do target.

Depois de salvos, filtros avançados ficam disponíveis ao selecionar a população do target de uma mensagem, no **[!UICONTROL User filters]** seção.

![](assets/adv-filter-target-type.png)


>[!NOTE]
>
>Use o **[!UICONTROL Exclude recipients from this segment]** para direcionar somente contatos que não correspondem aos critérios de filtro.


### Usar funções para criar filtros avançados{#use-functions-adv-filters}

Para executar recursos de filtragem avançados, use funções para definir o conteúdo do filtro. O editor de filtro Avançado aproveita todos os recursos do editor de query do Campaign.

Saiba como criar consultas avançadas nessas amostras completas:

* Saiba como direcionar em atributos de recipients simples no [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).
* Saiba como filtrar recipients não contatados nos últimos 7 dias em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html).
* Saiba como recuperar a lista de operadores que pode ser filtrada por contas ativas em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/create-a-filter.html).
* Saiba como criar um público-alvo de e-mail de aniversário no  [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html).


### Parâmetros avançados para filtros predefinidos {#param-for-data-filters}

Parâmetros avançados estão disponíveis para filtros predefinidos. Para acessá-los, navegue até a guia **[!UICONTROL Parameters]** do filtro.

* Para exibir o filtro por padrão para todas as listas baseadas nesse tipo de documento, selecione a opção **[!UICONTROL Default filter for the associated document type]** opção.

   Por exemplo, a variável **[!UICONTROL By name or login]** filtro é aplicado aos operadores Essa opção é selecionada, de modo que o filtro é sempre exibido em todas as listas de operadores.

* Para disponibilizar um filtro para todos os operadores do Campaign, selecione o  **[!UICONTROL Filter shared with other operators]** opção.

* Para definir um formulário para selecionar os critérios de filtragem, selecione a variável  **[!UICONTROL Use parameter entry form]** opção. Este formulário deve ser inserido no formato XML na função **[!UICONTROL Form]** guia . Por exemplo, o filtro predefinido incorporado **[!UICONTROL Recipients who have opened]**, disponível na lista de recipients, exibe um campo de filtro que permite selecionar o delivery ao qual o filtro se aplica.

![](assets/predefined-filters-parameters.png)


* O link **[!UICONTROL Advanced parameters]** permite definir configurações adicionais.

   * Você pode associar uma tabela SQL ao filtro para torná-la comum a todos os editores que a compartilham.
   * Para impedir que um usuário substitua o filtro, selecione a variável **[!UICONTROL Do not restrict the filter]** opção. Por exemplo, essa opção está ativa para os filtros &quot;Destinatários de um delivery&quot; e &quot;Destinatários de deliveries pertencentes a uma pasta&quot; que estão disponíveis no assistente de delivery. Esses filtros não podem ser sobrecarregados.
