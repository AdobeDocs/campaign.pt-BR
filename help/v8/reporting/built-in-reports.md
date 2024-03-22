---
title: Relatórios integrados do Adobe Campaign
description: Relatórios integrados
feature: Reporting
role: User
level: Beginner
exl-id: b63e6905-3bd4-4de4-9e7e-7638e5fc1192
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 88%

---

# Relatórios integrados do Adobe Campaign {#ootb-reports}

Esta página fornece a lista de relatórios internos do Adobe Campaign, seu conteúdo e seu contexto. O Adobe Campaign fornece uma variedade de relatórios internos, acessíveis com o console do cliente ou com um navegador da Internet.

Os seguintes tipos de relatório estão disponíveis:

* Relatórios sobre toda a plataforma. [Saiba mais](global-reports.md).
* Relatórios de entrega. [Saiba mais](delivery-reports.md).

Você pode acessar relatórios internos na página inicial do Campaign, no painel de relatórios dedicado ou na lista de delivery. A forma como o relatório é exibido na interface depende do contexto.

Uma lista dos principais relatórios está disponível na home page e permite acessar os dados de delivery rapidamente. Essa lista pode ser alterada para atender às suas necessidades. Você também pode aprender a adicionar seus próprios relatórios à **[!UICONTROL Reports]** guia.

Para obter mais informações sobre essas configurações personalizadas, consulte esta [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/configuring-access-to-the-report.html?lang=pt-BR){target="_blank"}.


## Acessar relatórios integrados {#access-ootb-reports}

Para acessar os relatórios internos do Campaign:

1. Selecione a guia **[!UICONTROL Reports]** da interface do Adobe Campaign.

   ![](assets/reporting-access-from-home.png)

1. Use os campos de pesquisa para filtrar os relatórios exibidos.

1. Em seguida, clique no relatório que deseja exibir.

   ![](assets/edit-a-report.png)

1. O link **[!UICONTROL Back]** na parte superior da tela o redirecionará para a lista de relatórios.

   ![](assets/back-button.png)

Os relatórios específicos a uma campanha ou uma entrega são acessíveis por meio de seus respectivos painéis.

![](assets/reporting-on-delivery.png)

O princípio é o mesmo para listas, serviços, ofertas, etc., conforme mostrado abaixo:

![](assets/reporting-on-offer.png)


## Relatórios de entregas {#reports-on-deliveries}

Os relatórios internos fornecidos pelo Adobe Campaign podem ser encontrados na tabela abaixo.

Para obter mais informações sobre o conteúdo desses relatórios, consulte [esta seção](delivery-reports.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo e nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Schema</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Atividades do usuário (recipientActivity)<br /> </td> 
   <td> Detalhamento de aberturas, cliques e transações por período de tempo.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de transferência de entrega (produtividade)<br /> </td> 
   <td> Gráficos de taxa de transferência de entrega, em mensagens/hora e Mbits/s.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Falhas e devoluções (erros)<br /> </td> 
   <td> Devoluções e não entregues por causa e domínio.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Indicadores de rastreamento (deliveryFeedback)<br /> </td> 
   <td> Resumo dos principais indicadores para rastrear o comportamento do destinatário.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Indicadores de rastreamento (mobileAppDeliveryFeedback)<br /> </td> 
   <td> Indicadores de rastreamento de uma entrega para um aplicativo móvel.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Navegadores (browserStatistics)<br /> </td> 
   <td> Estatísticas em navegadores usados por destinatários que clicaram em mensagens.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> Compartilhamento para redes sociais (deliveryForward)<br /> </td> 
   <td> Compartilhamento de atividades e estatísticas de aberturas de email.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Hot clicks (hoturls)<br /> </td> 
   <td> Exibe a mensagem e as taxas de clique sobrepostas.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatório Hipótese (deliveryHypothesis)<br /> </td> 
   <td> Exibe o resumo das medidas na hipótese de entrega.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Estatísticas de entrega (statisticsPerDelivery)<br /> </td> 
   <td> Estatísticas (mensagens processadas, mensagens entregues, devoluções permanentes, devoluções temporárias, cliques, unsubscriptions) por domínio de email.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Estatísticas de atividades de compartilhamento (forwardActivities)<br /> </td> 
   <td> Análise de atividades de compartilhamento, aberturas e subscrições por período de tempo.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Estatísticas de rastreamento (trackingStatistics)<br /> </td> 
   <td> Relatório de aberturas, cliques e taxas de transação.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Resumo da entrega (deliverySending)<br /> </td> 
   <td> Resumo dos indicadores de entrega: target, exclusão e mensagens enviadas.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Resumo da entrega (deliveryStatistics)<br /> </td> 
   <td> Tabela de resumo para entregas selecionadas: targets, exclusões e mensagens enviadas.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Sistemas operacionais (osStatistics)<br /> </td> 
   <td> Estatísticas dos sistemas operacionais usados por destinatários que clicaram em uma mensagem.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de reatividade (deliveryFeedbackSocial)<br /> </td> 
   <td> Detalhamento da reação e da taxa de reatividade de entrega.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de transferência de cliques e URLs (topUrlDelivery)<br /> </td> 
   <td> A maioria das URLs reativas e fluxos de clique associados.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Relatórios sobre campanhas {#reports-on-campaigns}

Os relatórios sobre campanhas se relacionam aos dados na tabela de **nms:operation** .

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo e nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Atividades do usuário (operationRecipientActivity)<br /> </td> 
   <td> O detalhamento de aberturas, cliques e transações por período de tempo depende do Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de transferência de entrega (operationThroughput)<br /> </td> 
   <td> Os gráficos de taxa de transferência de entrega, em emails/hora e Mbits/s, dependem do Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Despesas de campanha (budgetOperationExpenses)<br /> </td> 
   <td> Exibe os itens da linha de campanha em detalhes, depende do Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Falhas e devoluções (operationErrors)<br /> </td> 
   <td> Devoluções e não entregues por causa do domínio, depende do Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploração de linhas de custo (budgetExplorerOperation)<br /> </td> 
   <td> A análise descritiva das linhas de custo depende da Gestão dos Recursos de Marketing (MRM).<br /> </td> 
  </tr> 
  <tr> 
   <td> Indicadores de rastreamento (operationFeedback)<br /> </td> 
   <td> Visão geral dos indicadores principais de rastreamento: aberturas, cliques e transações que dependem do Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Compartilhamento para redes sociais (operationForward)<br /> </td> 
   <td> O compartilhamento de atividades e estatísticas de email aberto depende do Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatório Hipótese (operationHypothesis)<br /> </td> 
   <td> Exibe o resumo das medidas da hipótese para as entregas da campanha, depende do Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Estatísticas de atividades de compartilhamento (forwardActivityOpt)<br /> </td> 
   <td> A análise de atividades de compartilhamento, abertura e subscrições por período de tempo depende do Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Resumo da entrega (operationStatistics)<br /> </td> 
   <td> Gráfico de resumo das entregas da campanha: targets, exclusões e mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de transferência de clique e URLs (operationTopUrlDelivery)<br /> </td> 
   <td> A maioria das URLs reativas e fluxos de cliques associados dependem do Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Relatórios sobre serviços {#reports-on-services}

Os relatórios sobre serviços diz respeito aos dados na tabela de **nms:service** .

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo e nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Aquisições de fã (socialAcquisitionsByWebapp)<br /> </td> 
   <td> Quais aplicativos Web permitiram aquisições de prospecto? Depende de add-on de marketing social.<br /> </td> 
  </tr> 
  <tr> 
   <td> Detalhamento de subscrições (mobileAppDistribution)<br /> </td> 
   <td> O detalhamento de subscrições ativas por aplicativo móvel depende do add-on do canal de aplicativo móvel.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rastreamento de subscrição (subscriptionsProgress)<br /> </td> 
   <td> Evolução das subscrições para serviços de informação<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de Reatividade (socialReactionRate)<br /> </td> 
   <td> Quais são as taxas de reatividade para as entregas mais recentes? Depende de add-on de marketing social.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de Reatividade (mobileAppReactivityRate)<br /> </td> 
   <td> A taxa de reatividade para as entregas mais recentes depende do add-on de canal de aplicativo móvel.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Relatórios de orçamento {#budget-reports}

Os relatórios internos fornecidos pelo Adobe Campaign podem ser encontrados na tabela abaixo.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo e nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Schema</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Custos vinculados ao(s) programa(s) (budgetProgramCost)<br /> </td> 
   <td> Detalhamento dos custos de programa.<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> Evolução do orçamento (budgetEvolution)<br /> </td> 
   <td> Evolução dos custos orçamentários por nível de comprometimento.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Evolução cumulativa do orçamento (budgetCumulativeEvolution)<br /> </td> 
   <td> Evolução dos custos do orçamento acumulado divididos por nível de<br /> compromisso. </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploração de linhas de custo (budgetExplorerBudget)<br /> </td> 
   <td> Análise descritiva de linhas de custo.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploração de linhas de custo (budgetExplorer)<br /> </td> 
   <td> Análise descritiva de linhas de custo.<br /> </td> 
   <td> nms:costLine<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploração de linhas de custo (budgetExplorerPlan)<br /> </td> 
   <td> Análise descritiva de linhas de custo.<br /> </td> 
   <td> nms:plan<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploração de linhas de custo (budgetExplorerProgram)<br /> </td> 
   <td> Análise descritiva de linhas de custo.<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> Resumo do(s) orçamento(s) (orçamento)<br /> </td> 
   <td> Instantâneo dos custos principais, categorias de despesas e orçamentos.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Relatórios sobre simulações {#reports-on-simulations}

Os relatórios sobre simulações dizem respeito aos dados na tabela de **nms:simulation**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo e nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Detalhe das exclusões de simulação (dlvSimuLossesDetail)<br /> </td> 
   <td> Tabela detalhada de todas as causas da exclusão.<br /> </td> 
  </tr> 
  <tr> 
   <td> Detalhamento de ofertas por classificação (offerSimulationRanking)<br /> </td> 
   <td> Detalhamento de ofertas na simulação, por classificação.<br /> </td> 
  </tr> 
  <tr> 
   <td> Resumo de simulação (dlvSimuLossesSummary)<br /> </td> 
   <td> Resumo de volumes e exclusões de simulação.<br /> </td> 
  </tr> 
  <tr> 
   <td> Estatística de sobreposição (dlvSimuOverlapping)<br /> </td> 
   <td> Volumes de sobreposição de target de entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Resumo das exclusões devido à simulação (dlvSimuLossesSimu)<br /> </td> 
   <td> Tabela de exclusões devido à simulação.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Relatórios sobre aplicativos web {#reports-on-web-applications}

Os relatórios em aplicativos Web dizem respeito aos dados na tabela de **nms:WebApp** .

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo e nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Documentação (surveyDictionary)<br /> </td> 
   <td> A descrição da estrutura de pesquisa depende do add-on do Gerenciador de Pesquisa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Principal (surveyProperties)<br /> </td> 
   <td> Propriedades da pesquisa<br /> </td> 
  </tr> 
  <tr> 
   <td> Detalhamento de respostas (surveyDistribution)<br /> </td> 
   <td> Detalhamento de respostas às perguntas.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Outros relatórios OOTB {#other-ootb-reports}

Os relatórios a seguir também são fornecidos internamente. Para obter mais informações, consulte o documento na funcionalidade relacionada a eles.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo e nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Schema</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Análise de oferta (offerAnalysis)<br /> </td> 
   <td> A análise de oferta por data e canal depende do add-on Interaction.<br /> </td> 
   <td> nms:ofer<br /> </td> 
  </tr> 
  <tr> 
   <td> Eficiência de re-marketing (remarketingEffect)<br /> </td> 
   <td> Medição da eficiência do re-marketing<br /> </td> 
   <td> nms:webEvent<br /> </td> 
  </tr> 
  <tr> 
   <td> Histórico de aquisições de prospecto social (socialVisitorStatistics)<br /> </td> 
   <td> O histórico de aquisições de clientes em potencial do X (anteriormente conhecido como Twitter) e do Facebook depende do complemento de marketing social.<br /> </td> 
   <td> nms:visitor<br /> </td> 
  </tr> 
  <tr> 
   <td> Rastreamento de apresentação recente (recentPropositions)<br /> </td> 
   <td> Rastreamento de apresentação em tempo real<br /> </td> 
   <td> nms:propositionRcp<br /> </td> 
  </tr> 
 </tbody> 
</table>
