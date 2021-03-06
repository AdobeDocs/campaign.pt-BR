---
product: campaign
title: Templates de campanha de marketing
description: Templates de campanha de marketing
feature: Campaigns, Templates
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 55%

---

# Criar e configurar modelos de campanha {#campaign-templates}

Todas as campanhas de marketing são baseadas em um modelo, que armazena as principais características e recursos. O Campaign vem com um template incorporado para criar campanhas. Este template tem todas as funcionalidades habilitadas: Documentos, Seed addresses, Aprovações, Delivery outlines etc.

As funcionalidades disponíveis dependem de suas permissões, complementos e da configuração da sua plataforma Adobe Campaign.


>[!NOTE]
>
>A árvore é exibida ao clicar no ícone **[!UICONTROL Explorer]** na home page.

Um modelo integrado é fornecido para criar uma campanha para a qual nenhuma configuração específica foi definida. Você pode criar e configurar seus modelos de campanha e, em seguida, criar campanhas com base nesses modelos.

## Criar um template de campanha {#create-a-campaign-template}

Para criar um template de campanha, siga as etapas abaixo:

1. Abrir campanha **Explorer** e navegue até **Resources > Templates > Campaign templates**.
1. Clique em **Novo** na barra de ferramentas acima da lista de templates.

![](assets/campaign-template-node.png)

Você também pode **duplicate** o template incorporado para reutilizar e adaptar sua configuração. Para fazer isso, clique com o botão direito do mouse no template e selecione **Duplicar**.

1. Insira o rótulo do seu novo template de campanha.
1. Clique em **Save** e abra seu template novamente.
1. No **Editar** , defina as propriedades do template.
1. Selecionar **Parâmetros de campanha avançada...** para adicionar um workflow ao seu template de campanha.

   ![](assets/campaign-template-parameters.png)

1. Altere o **Direcionamento e workflows** para **Sim** e confirme. Saiba como adicionar funcionalidades no [esta seção](#typology-of-enabled-modules).
1. O **Direcionamento e workflows** é adicionada ao modelo. Clique em **Adicionar um fluxo de trabalho...**, insira um **Rótulo** e clique em **Ok**.
1. Crie o workflow de acordo com suas necessidades.

   ![](assets/campaign-template-create-wf.png)

1. Clique em **Save**. Seu template está pronto para ser usado para criar uma nova campanha.

As várias guias e subguias do template de campanha permitem que você acesse as configurações, descritas em [Configuração geral](#general-configuration).

## Selecionar módulos {#select-modules}

O link **[!UICONTROL Advanced campaign parameters...]** permite habilitar e desabilitar tarefas para as campanhas com base neste modelo. Selecione os recursos que deseja habilitar nas campanhas criadas com base neste modelo.

![](assets/campaign-template-select-modules.png)

Se uma funcionalidade não estiver selecionada, os elementos relativos ao processo (menus, ícones, opções, guias, subguias etc.) não aparecem na interface do template ou em campanhas baseadas nesse template. As guias à esquerda dos detalhes da campanha e as guias disponíveis coincidem com as funcionalidades selecionadas no template. Por exemplo, a variável **Despesas e objetivos** não estiver ativada, a variável correspondente **[!UICONTROL Budget]** não mostrar em campanhas baseadas nesse template.

Além disso, os atalhos para as janelas de configuração são adicionados ao painel de campanha. Quando uma funcionalidade é habilitada, um link direto dá acesso a ela a partir do painel de campanha.

### Exemplos de configuração

* Por exemplo, com as seguintes configurações:

   ![](assets/campaign-template-select-functionalities.png)

   O painel de campanha mostra:

   ![](assets/campaign-template-dashboard-sample-1.png)

   Observe que a variável **[!UICONTROL Targeting and workflows]** está ausente.

   As seguintes funcionalidades estão disponíveis:

   ![](assets/campaign-template-edit-sample-1.png)

   Observe que a variável **[!UICONTROL Budget]** está ausente.

   As configurações avançadas da campanha também refletem essa configuração.

   ![](assets/campaign-template-parameters-sample-1.png)

   Observe que a variável **[!UICONTROL Approvals]** não está disponível.

* Com esta configuração:
   ![](assets/campaign-template-dashboard-sample-2.png)

   O painel de campanha mostra:

   ![](assets/campaign-template-select-functionalities-2.png)

   Observe que a variável **[!UICONTROL Targeting and workflows]** está disponível, mas a guia **Adicionar um documento** link ausente.

   As seguintes funcionalidades estão disponíveis:

   ![](assets/campaign-template-edit-sample-2.png)

   Observe que a variável **[!UICONTROL Budget]** estiver disponível.

   As configurações avançadas da campanha também refletem essa configuração.

   ![](assets/campaign-template-parameters-sample-2.png)

   Observe que a variável **[!UICONTROL Approvals]** está disponível, mas a guia **[!UICONTROL Control population]** e **[!UICONTROL Seed addresses]** as guias não estão ativadas.


## Tipologia de módulos {#typology-of-enabled-modules}

* **Grupo de controle**

   Quando este módulo está selecionado, uma guia adicional é adicionada às configurações avançadas do template e às campanhas baseadas nesse template. A configuração pode ser definida por meio do modelo ou individualmente para cada campanha. Saiba mais sobre grupos de controle [nesta seção](marketing-campaign-deliveries.md#defining-a-control-group).

   ![](assets/template-activate-1.png)


* **Seed addresses**

   Quando este módulo está selecionado, uma guia adicional é adicionada às configurações avançadas do template e às campanhas baseadas nesse template. A configuração pode ser definida por meio do template ou individualmente para cada campanha.

   ![](assets/template-activate-2.png)

* **Documentos**

   Quando este módulo é selecionado, uma guia adicional é adicionada à guia **[!UICONTROL Edit]** do template e às campanhas com base nesse template. Os documentos anexados podem ser adicionados do modelo ou individualmente para cada campanha. Saiba mais sobre documentos [nesta seção](marketing-campaign-deliveries.md#manage-associated-documents).

   ![](assets/template-activate-3.png)

* **Delivery outline**

   Quando esse módulo é selecionado, uma subguia **[!UICONTROL Delivery outlines]** é adicionada à guia **[!UICONTROL Documents]** para definir os delivery outlines da campanha. Saiba mais sobre delivery outlines [nesta seção](marketing-campaign-assets.md#delivery-outlines).

   ![](assets/template-activate-4.png)

* **Direcionamento e workflows**

   Ao selecionar o módulo **[!UICONTROL Targeting and workflows]**, uma guia é adicionada para permitir que você crie um ou mais workflows para campanhas com base nesse template. Os workflows também podem ser configurados individualmente para cada campanha com base neste modelo. Saiba mais sobre workflows da campanha [nesta seção](marketing-campaign-deliveries.md#build-the-main-target-in-a-workflow).

   ![](assets/template-activate-5.png)

   Quando este módulo é ativado, um **[!UICONTROL Jobs]** é adicionada às configurações avançadas da campanha para definir a sequência de execução do processo.

* **Aprovações**

   Se você ativar a variável **[!UICONTROL Approvals]**, é possível selecionar os processos a serem aprovados e os operadores de aprovação. Saiba mais sobre aprovações [nesta seção](marketing-campaign-approval.md#select-reviewers).

   ![](assets/template-activate-6.png)

   Você pode optar por habilitar ou não a aprovação do processo por meio da variável **[!UICONTROL Approvals]** da seção configurações avançadas dos modelos.

* **Despesas e objetivos**

   Quando esse módulo for selecionado, uma guia **[!UICONTROL Budget]** é adicionada aos detalhes do modelo e às campanhas com base nesse modelo para que o orçamento associado possa ser selecionado.

   ![](assets/template-activate-7.png)


## Propriedades do template {#template-properties}

![](assets/template-op-type.png)

Ao criar um template de campanha, você precisa inserir as seguintes informações:

* Insira o **label** do modelo: o rótulo é obrigatório e é o rótulo padrão para todas as campanhas com base nesse template.
* Selecione a **natureza** da campanha na lista suspensa. Os valores disponíveis nesta lista são os que foram salvos na lista discriminada **[!UICONTROL natureOp]**.
   <!--
  >[!NOTE]
  >
  >For more information on enumerations, refer to the [Getting Started](../../platform/using/managing-enumerations.md) section.-->

* Selecione o **tipo de campanha**: exclusiva, recorrente ou periódica. Por padrão, os templates de campanha se aplicam a campanhas exclusivas. As campanhas recorrentes e periódicas são detalhadas [nesta seção](recurring-periodic-campaigns.md).
* Especifique a duração da campanha, ou seja, o número de dias em que a campanha ocorrerá. Ao criar uma campanha com base nesse template, as datas de início e término da campanha serão preenchidas automaticamente.

   Se a campanha for recorrente, você deverá especificar as datas de início e término da campanha diretamente no template.

* Especifique a **programa relacionado** do modelo: campanhas baseadas neste template são vinculadas ao programa selecionado.

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.-->
