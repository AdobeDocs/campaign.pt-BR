---
title: Análise de entrega
description: Saiba como preparar e verificar seu delivery
feature: Personalization
role: User
level: Beginner
source-git-commit: 51b333492ad50849751208c7549dc00f66140b82
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 62%

---

# Análise de entrega {#analyze-delivery}

A análise é a etapa de preparação do delivery. Ele pode ser iniciado assim que o público-alvo for definido e o conteúdo da mensagem estiver pronto e testado. Durante a análise de delivery, a população do target é calculada e o conteúdo do delivery é preparado. Uma vez concluído, o delivery estará pronto para ser enviado.

## Iniciar a análise {#start-the-analysis}

Para preparar o delivery, verifique se o conteúdo e o target do delivery foram definidos e siga as etapas abaixo:

1. Nas janelas de delivery, clique no botão **[!UICONTROL Send]** botão.
1. Selecionar **[!UICONTROL Deliver as soon as possible]** para executar o cálculo de público-alvo e a preparação do conteúdo para um envio imediato. Você também pode adiar o delivery para uma data posterior ou obter uma estimativa da população sem preparar o conteúdo.

   ![](assets/delivery-analysis-start.png)

1. Clique em **[!UICONTROL Analyze]** para iniciar a análise manualmente. A barra de progresso mostra o progresso da análise.

   Um conjunto de regras de verificação é aplicado durante a análise do delivery. Essas regras são definidas em um **tipologia**, que é selecionado no **[!UICONTROL Typology]** nas propriedades do delivery. Saiba mais sobre tipologias em [esta seção](../../automation/campaign-opt/campaign-typologies.md).

   Por padrão, para emails, a análise cobre os seguintes pontos:

   * Aprovando o objeto
   * Aprovando as URLs e imagens
   * Aprovação dos rótulos do URL
   * Aprovando o link de cancelamento de subscrição
   * Verificando o tamanho das provas
   * Verificando o período de validade
   * Verificando a programação de ondas


1. Você pode interromper a análise a qualquer momento clicando no botão **[!UICONTROL Stop]** botão.

   Não será enviada nenhuma mensagem durante a fase de preparo. Portanto, é possível iniciar ou cancelar a análise sem riscos.

   >[!IMPORTANT]
   >
   >Durante a execução, a análise congela o delivery (ou a prova). Qualquer modificação no delivery (ou na prova) deve ser seguida de outra análise antes de se tornar aplicável.

   Ao concluir a análise, a seção superior da janela indica se o preparo do delivery está concluído ou se ocorreram erros. Todas as etapas de validação, avisos e erros são listados. Os ícones coloridos mostram o tipo de mensagem:

   * Um ícone azul indica uma mensagem informativa.
   * Um ícone amarelo indica um erro de processamento não crítico.
   * Um ícone vermelho indica um erro crítico que impede o envio do delivery.

   ![](assets/delivery-analysis-results.png){width="800" align="left"}

1. Clique em **[!UICONTROL Close]** para corrigir os erros, se houver. Depois de fazer as alterações, reinicie a análise clicando em **[!UICONTROL Analyze]**.

   >[!NOTE]
   >
   >Clique no botão **[!UICONTROL Change the main delivery target]** link se o número de mensagens para enviar não corresponder às suas expectativas. Essa opção permite alterar a definição da população do target e reiniciar a análise.

1. Depois de verificar o resultado da análise, clique em **[!UICONTROL Confirm delivery]** para enviar a mensagem para o target principal.


## Configurações de análise {#analysis-settings}

Navegue até o **[!UICONTROL Analysis]** das propriedades de delivery para definir as configurações para a preparação da mensagem durante a fase de análise.

![](assets/delivery-properties-analysis-tab.png){width="800" align="left"}

Essa guia fornece acesso às seguintes opções:

* **[!UICONTROL Label and code of the delivery]**: as opções referentes a esta seção são usadas para calcular os valores desses campos durante a fase de análise do delivery. O campo **[!UICONTROL Compute the execution folder during the delivery analysis]** calcula o nome da pasta que conterá essa ação de delivery durante a fase de análise.

* **[!UICONTROL Approval mode]** : esse campo permite a definição do delivery manual ou automática quando a análise é concluída.

   Se os avisos forem gerados durante a análise (ex.: se certos caracteres estiverem acentuados no assunto do delivery etc.), você poderá configurar o delivery para definir se ele ainda deverá ou não ser executado. Por padrão, o usuário deverá confirmar o envio de mensagens no final da fase de análise: essa é a validação **manual**.

   Selecione outro modo de aprovação na lista suspensa no campo apropriado.

   Os seguintes modos de aprovação estão disponíveis:

   * **[!UICONTROL Manual]**: no final da fase de análise, o usuário deverá confirmar o delivery para começar a enviar. Para fazer isso, clique no botão **[!UICONTROL Start]** para iniciar o delivery.
   * **[!UICONTROL Semi-automatic]**: o envio começa automaticamente se a fase de análise não gerar mensagens de advertência.
   * **[!UICONTROL Automatic]**: o envio começa automaticamente no fim da fase de análise, independentemente do resultado.

* **[!UICONTROL Start job in a detached process]** : essa opção permite iniciar a análise do delivery em um processo separado. A função de análise usa o processo do servidor de aplicativos Adobe Campaign (Web nlserver) por padrão. Ao selecionar essa opção, você garante que a análise será concluída mesmo no caso de falha do servidor de aplicativos.
* **[!UICONTROL Log SQL queries generated during the analysis in the journal]**: essa opção adiciona os logs de consulta SQL ao journal de delivery durante a fase de análise.
* **[!UICONTROL Ignore personalization scripts during sending]**: essa opção permite ignorar a interpretação das diretivas JavaScript encontradas no conteúdo HTML. Eles serão exibidos como nos conteúdos entregues. Estas diretivas são introduzidas com `<%=` .


