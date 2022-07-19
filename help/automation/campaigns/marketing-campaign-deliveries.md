---
product: campaign
title: Deliveries de campanha de marketing
description: Saiba mais sobre deliveries de campanha de marketing
feature: Campaigns, Resource Management, Cross Channel Orchestration
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 48%

---

# Entregas de campanha de marketing {#marketing-campaign-deliveries}

Organize seus deliveries entre canais em suas campanhas: simplifique suas comunicações com o Adobe Campaign por meio de emails personalizados, SMS, notificações por push e mensagens no aplicativo. Você pode usar mídias avançadas como vídeos, emojis ou GIF e integrá-los diretamente.

As entregas podem ser criadas por meio do painel da campanha, de um fluxo de trabalho de campanha ou diretamente na visão geral das entregas. Quando criados a partir de uma campanha, os deliveries serão vinculados a essa campanha e consolidados em seu nível.

## Criar entregas {#create-deliveries}

Você tem duas maneiras de adicionar deliveries às suas campanhas de marketing:

* No **[!UICONTROL Add a delivery]** no painel de campanha.

![](assets/campaign_op_add_delivery.png)

Depois de salvo, o delivery é adicionado ao painel de campanha.

* Em um workflow de campanha, no **[!UICONTROL Targeting and workflows]** , adicionando o delivery.

   ![](assets/campaign-wf-delivery.png)

   Depois que o workflow for iniciado, o delivery será adicionado ao painel de campanha.

Saiba como configurar e executar o fluxo de aprovação de delivery [nesta página](marketing-campaign-approval.md).

## Iniciar um delivery {#start-a-delivery}

Um delivery pode ser enviado depois que todas as aprovações tiverem sido concedidas. O processo de execução do delivery depende do canal.

* Para deliveries de email ou canal móvel, consulte [esta seção](#start-an-online-delivery)

* Para deliveries de correspondência direta, consulte [esta seção](#start-an-offline-delivery)

### Iniciar um delivery de email ou móvel {#start-an-online-delivery}

Depois que todas as solicitações de aprovação tiverem sido concedidas, o status do delivery será alterado para **[!UICONTROL Pending confirmation]** e pode ser iniciado. Revisores que podem iniciar o delivery são notificados de que um delivery está pronto para ser iniciado.

![](assets/confirm-delivery.png)

As informações também aparecem no painel de campanha. O link **[!UICONTROL Confirm delivery]** permite iniciar o delivery.

![](assets/confirm-delivery-from-dashboard.png)

A confirmação do delivery é restrita a Administradores e ao operador ou grupo de operadores explicitamente mencionados nas propriedades do delivery ou da campanha. Se nenhum operador for projetado, os administradores e o proprietário da campanha poderão aprovar.

![](assets/select-delivery-reviewers.png)

No entanto, também é possível permitir que o proprietário da campanha confirme o envio, mesmo se revisores específicos tiverem sido definidos nas propriedades de delivery ou campanha. Para fazer isso, como Administrador, crie a **NmsCampaign_Ativate_OwnerConfirmation** e defina-a como **1**. As opções são gerenciadas no nó **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]** no explorador do Adobe Campaign.


### Iniciar um delivery de mala direta {#start-an-offline-delivery}

Após todas as aprovações serem concedidas, o status do delivery será alterado para **[!UICONTROL Pending extraction]**. Os arquivos de extração são criados por um [fluxo de trabalho técnico](../workflow/technical-workflows.md) que, em uma configuração padrão, é iniciada automaticamente quando um delivery de correspondência direta está com extração pendente. Quando um processo está em andamento, ele é exibido no painel e pode ser editado através do link.

Após executar o workflow de extração com sucesso, o arquivo de extração deve ser aprovado (fornecido de forma que a aprovação do arquivo de extração tenha sido selecionada nas configurações do delivery). [Saiba mais](marketing-campaign-approval.md#approving-an-extraction-file).

Siga as etapas abaixo para validar o conteúdo e enviar o arquivo para o provedor:

1. Depois que o arquivo de extração for aprovado, é possível gerar a prova do email de notificação do roteador. Esta mensagem de email é construída com base em um template de delivery. Deve ser aprovado.

   Essa etapa só estará disponível se a variável **[!UICONTROL Enable the sending and validation of proofs (Direct mail)]** foi ativada em **[!UICONTROL Approvals]** dos parâmetros avançados da campanha.

   ![](assets/enable-proof-validation.png)

1. Clique no botão **[!UICONTROL Send a proof]** para criar as provas.

   O target da prova deve ser definido com antecedência.

   Você pode criar quantas provas forem necessárias. Elas são acessadas por meio do link **[!UICONTROL Direct mail...]** dos detalhes de delivery.

1. O status do delivery é alterado para **[!UICONTROL To submit]**. Clique no botão **[!UICONTROL Submit proofs]** para iniciar o processo de aprovação.

1. O status do delivery muda para **[!UICONTROL Proof to validate]**, e um botão permite aceitar ou rejeitar a aprovação.

   Você pode aceitar ou rejeitar esta aprovação ou retornar à etapa de extração.

1. Depois que a prova for aprovada, o arquivo de extração será enviado para o roteador e o delivery será concluído.

### Cálculo de orçamento e custos {#compute-costs-and-stocks}

A extração de arquivos inicia dois processos: cálculo de orçamento e cálculo de estoque. As entradas do orçamento são atualizadas.

* A guia **[!UICONTROL Budget]** permite gerenciar os orçamentos da campanha. O total das entradas de custo é exibido no campo **[!UICONTROL Calculated cost]** da guia principal da campanha e o programa ao qual ele pertence. Os montantes também são refletidos no orçamento da campanha.

   ![](assets/campaign-budget-tab.png)

   O custo real será calculado de acordo com as informações fornecidas pelo roteador. Apenas mensagens enviadas são faturadas.

* Os stocks são definidos na variável **[!UICONTROL Administration > Campaign management > Stocks]** nó da árvore.

   ![](assets/campaign-stocks.png)

   Estruturas de custo na **[!UICONTROL Administration > Campaign management > Service providers]** nó .

   ![](assets/campaign-service-providers.png)

   As linhas de estoque estão visíveis na seção de estoque. Para definir o estoque inicial, abra uma linha de estoque. O estoque é reduzido sempre que um delivery ocorre. Você pode definir um nível de alerta e notificações.


   >[!NOTE]
   >
   >Saiba mais sobre orçamentos [nesta seção](providers--stocks-and-budgets.md).
