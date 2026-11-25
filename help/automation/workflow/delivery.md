---
product: campaign
title: Delivery
description: Saiba mais sobre a atividade de fluxo de trabalho de tipo Delivery
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 58574983-86c7-46f5-b41b-bae90171048d
TQID: 'https://experienceleague.adobe.com/ui9ry7GeEH28K6h0jTg6Eg0JHdMQFak9KogF-h6LkX0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: bce277d1-7efa-48d8-9a1b-b588bb45ba1c
    internal-label: Channels Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 81%
---
# Entrega{#delivery}

Uma atividade do tipo **Entrega** permite criar uma ação de entrega. Ele pode ser construído usando elementos de entrada.

Para configurá-la, edite a atividade e insira as opções de entrega.

![Janela de atividade de entrega com Entrega, Destinatários, Conteúdo e Ação para executar seções e transição de saída](assets/edit_diffusion.png)

1. **Entrega**

   É possível:

   * Atue na entrega especificada na transição de entrada. Para fazer isso, selecione a primeira opção de seção **[!UICONTROL Delivery]** da janela.

     Essa opção pode ser usada quando uma atividade de fluxo de trabalho anterior já criou ou especificou a entrega. Isso pode ter sido feito, como no exemplo abaixo, por uma atividade do mesmo tipo que gerou uma transição de saída.

     No exemplo a seguir, a entrega é criada pela primeira vez. A população e o conteúdo são definidos mais tarde. Em seguida, as informações desses três elementos são inseridas novamente em uma nova atividade de entrega usando a transição de entrada para que isso possa ser enviado.

     ![Fluxo de trabalho no qual uma atividade Criar a entrega alimenta uma segunda atividade de Entrega definida como Especificado na transição](assets/specified_transition_option_exemple.png)

   * Selecione diretamente a entrega envolvida. Para fazer isso, selecione a opção **[!UICONTROL Explicit]** e selecione o da lista suspensa no campo **[!UICONTROL Delivery]** Entrega.

     A lista exibe entregas não concluídos contidos na pasta **Entregas** por padrão. Para acessar outras campanhas, clique no ícone **[!UICONTROL Select link]**.

     ![Seção de entrega com Explicit selecionado e o ícone Selecionar link ao lado do campo Entrega](assets/diffusion_edit_1.png)

     Selecione a campanha da lista suspensa no campo **[!UICONTROL Folder]** ou clique em **[!UICONTROL Display sub-levels]** para exibir todas as entregas contidas em subpastas:

     ![Janela de seleção de entrega com o campo Pasta definido como Entregas e o ícone Exibir subníveis](assets/diffusion_edit_2.png)

     Após selecionar a ação de entrega, é possível exibir o conteúdo clicando em **[!UICONTROL Edit link]**.

   * Crie um script para calcular a entrega. Para fazer isto, clique na opção **[!UICONTROL Computed by a script]** e depois insira o script. É possível abrir uma janela de entrada clicando na opção **[!UICONTROL Edit...]**. O exemplo a seguir recupera o identificador da entrega:

     ![Calculado por uma opção de script com a janela Editar script mostrando a expressão vars.deliveryId](assets/diffusion_edit_3.png)

   * Criação de nova entrega Para fazer isso, selecione a opção **[!UICONTROL New, created from a template]** e selecione o modelo da entrega no qual a entrega será baseada.

     ![Novo, criado de uma opção de modelo com um modelo de entrega selecionado e o ícone Editar link](assets/diffusion_edit_4.png)

     Clique em **[!UICONTROL Select link]** para procurar as pastas e clique em **[!UICONTROL Edit link]** se desejar visualizar o conteúdo do modelo selecionado.

1. **Recipients**

   Os destinatários podem ser especificados pelos eventos de entrada, por exemplo, seguindo uma importação de arquivo ou especificado na ação de entrega. Eles também podem ser armazenados em um ou mais arquivos.

   ![Seção Recipients com opções Especificadas pelo(s) evento(s) de entrada, Especificada na entrega e Arquivo(s) especificado(s)](assets/diffusion_edit_5.png)

1. **Conteúdo**

   O conteúdo da mensagem pode ser definido na entrega ou no evento de entrada.

   ![Seção de conteúdo com Especificado pelo evento de entrada e Especificado nas opções de entrega](assets/diffusion_edit_6.png)

1. **Ação a ser executada**

   Você pode criar a entrega, prepará-la, iniciá-la, estimar o target ou enviar uma prova.

   ![Ação para executar opções de Salvar para Preparar e iniciar e a opção Gerar uma transição de saída](assets/diffusion_edit_7.png)

   Selecione o tipo de ação a ser executada:

   * **[!UICONTROL Save]**: esta opção permite criar a entrega e salvá-la. Ele não irá analisar nem enviá-la.
   * **[!UICONTROL Estimate the target]**: essa opção permite calcular o target da entrega para avaliar seu potencial (primeira fase de análise). Esta ação é equivalente a selecionar a opção **[!UICONTROL Estimate the population to be targeted]** e clicar em **[!UICONTROL Analyze]** ao enviar uma entrega para o target principal por meio de **Entrega**.
   * **[!UICONTROL Prepare]**: esta opção permite executar o processo de análise completa (cálculo de target e preparação de conteúdo). A entrega não é enviada. Esta ação é equivalente a selecionar a opção **[!UICONTROL Deliver as soon as possible]** e clicar em **[!UICONTROL Analyze]** ao enviar uma entrega para o target principal com **Entrega**.
   * **[!UICONTROL Send a proof]**: esta opção permite enviar uma prova da entrega. Esta ação é equivalente ao clicar em **[!UICONTROL Send a proof]** na barra de ferramentas de uma entrega com **Entrega**
   * **[!UICONTROL Prepare and start]**: esta opção inicia o processo de análise completa (cálculo de target e preparação de conteúdo) e envia a entrega. Esta ação é equivalente a clicar na opção **[!UICONTROL Deliver as soon as possible]**, **[!UICONTROL Analyze]** e **[!UICONTROL Confirm delivery]** ao enviar uma entrega ao target principal com **Entrega**.

   A atividade **[!UICONTROL Act on a delivery]** usada mais no fluxo de trabalho permite iniciar todas as etapas restantes necessárias para iniciar a entrega (cálculo de target, preparação de conteúdo, entrega). Para obter mais informações, consulte [Controle de entrega](delivery-control.md).

   As seguintes opções também estão disponíveis:

   * **[!UICONTROL Generate an outbound transition]**

     Cria uma transição de saída que será ativada no final da execução. Você pode escolher se quer recuperar ou não o target da entrega.

   * **[!UICONTROL Do not recover target]**

     Não recupera o target da ação de entrega realizada.

   * **[!UICONTROL Processing errors]**

     Consulte [Controle de entrega](delivery-control.md).

   A guia **Script** permite modificar os parâmetros de entrega.

   ![Guia Script da atividade Delivery com um script de modificação de objeto de entrega definindo o rótulo de entrega](assets/edit_diffusion_fil_script.png)

## Exemplo: fluxo de trabalho de entrega {#example--delivery-workflow}

Crie um novo fluxo de trabalho e adicione atividades conforme mostrado no gráfico abaixo:

![Fluxo de trabalho com atividades de Início, Entrega e Aprovação, depois Controle de Entrega em Sim e Fim em Não](assets/new-workflow-5.png)

Abra a atividade de **Entrega** e defina as propriedades da seguinte maneira:

* Na seção **[!UICONTROL Delivery]**, selecione **[!UICONTROL New, created from a template]** e selecione um modelo de entrega.
* Na seção **[!UICONTROL Recipients]**, selecione **[!UICONTROL Specified in the delivery]**.
* Na seção **[!UICONTROL Action to execute]**, mantenha a opção **[!UICONTROL Prepare]**.

![Atividade de entrega com Novo, criada a partir de um modelo, Especificada nos destinatários de entrega e Preparar selecionada](assets/new-workflow-param-delivery.png)

Clique em **[!UICONTROL OK]** para fechar a janela das propriedades. Você acabou de configurar uma atividade que consiste na criação e preparação de uma nova entrega com base em um modelo de entrega cujo destino será especificado.

Abra a atividade de **Aprovação** e defina as propriedades da seguinte maneira:

1. No campo **[!UICONTROL Assignment type]**, selecione um grupo no qual você está registrado. Se estiver conectado com a conta de administrador, selecione o grupo Administração.
1. Em seguida, insira um título e insira o seguinte texto no corpo da mensagem:

   ```
   Do you wish to approve delivery (<%= vars.recCount %> recipient(s))?
   ```

   Esta é uma mensagem que inclui uma expressão escrita em JavaScript: **[!UICONTROL vars.recCount]** representa o número de destinatários direcionados pela entrega da tarefa anterior. Para obter mais informações sobre expressões JavaScript, consulte [Scripts e modelos do JavaScript](javascript-scripts-and-templates.md).

   ![Atividade de aprovação com tipo de atribuição Group e uma mensagem usando vars.recCount pedindo a aprovação do target](assets/new-workflow-param-validation.png)

   A tarefa Approval é apresentada em [Approval](approval.md).

## Parâmetros de entrada {#input-parameters}

Identificador de entrega, se a opção **[!UICONTROL Specified in the transition]** estiver selecionada na seção **[!UICONTROL Delivery]**.

* deliveryId
* tableName
* esquema

Cada evento de entrada deve especificar um target definido por esses parâmetros.

>[!NOTE]
>
>Esse parâmetro só aparecerá se a opção **[!UICONTROL Specified by inbound event(s)]** estiver selecionada na seção **[!UICONTROL Recipients]**.

* filename

  Nome completo do arquivo gerado se a opção **[!UICONTROL File(s) specified by inbound event(s)]** estiver selecionada na seção **[!UICONTROL Recipients]**.

* contentId

  Identificador de conteúdo se a opção **[!UICONTROL Specified by inbound events]** estiver selecionada na seção **[!UICONTROL Content]**.

## Parâmetros de saída {#output-parameters}

* tableName
* esquema
* recCount

Esse conjunto de três valores identifica o target resultante da entrega. **[!UICONTROL tableName]** é o nome da tabela que armazena os identificadores do público-alvo, **[!UICONTROL schema]** é o esquema da população (geralmente nms:recipient) e **[!UICONTROL recCount]** é o número de elementos da tabela.

A transição associada ao complemento tem os mesmos parâmetros.

>[!NOTE]
>
>Não há parâmetros de saída quando a opção **[!UICONTROL Do not recover target]** estiver selecionada.
