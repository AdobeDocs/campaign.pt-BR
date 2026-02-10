---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: c7f1edc27a7e09a3a7da172af1df7de01118c516
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 17%

---

# Versões mais recentes {#latest-release}

Esta página lista novos recursos, melhorias e correções das **últimas versões** do Campaign v8 (console). Saiba mais sobre lançamentos, versões e atualizações do Campaign [nesta página](upgrades.md). Outras versões estão listadas na seção Versões anteriores desta documentação.

## Versão 8.9.1 {#release-8-9-1}

_27 de janeiro de 2026_

>[!CAUTION]
>
> A atualização do Console do Cliente é obrigatória. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

### Novos recursos {#new-8-9-1}

O **novo conector de envio de SMS** agora está disponível para todos os clientes (GA). Consulte a [documentação detalhada](../send/sms/sms.md).

Esta versão é fornecida com um conjunto de funcionalidades disponíveis na interface da Web do Campaign:

* [Recursos de entrega multilíngue (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [Enriquecimento de Perfil em Mensagens Transacionais (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Adobe Experience Manager live e cópias de idioma](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [Experimentos de conteúdo - teste A/B](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"}
* [Atividade de entrega contínua](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"}
* [Gerenciamento de aprovação de campanha](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"}

Consulte as [notas de versão](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=pt-BR){target="_blank"} da interface da Web do Campaign

### Melhorias de segurança {#security-8-9-1}

* As contas externas do Snowflake agora oferecem suporte à autenticação OAuth2, fornecendo métodos de autenticação modernos e seguros para conexões de acesso a dados federados. (NEO-87013)
* As contas externas de databricks agora oferecem suporte à autenticação OAuth2 por meio da entidade de serviço (fluxo de credenciais de cliente não interativo), fornecendo métodos de autenticação seguros para conexões de acesso a dados federados. A autenticação OAuth2 interativa estará disponível em uma versão futura. (NEO-87422)
* Correção de vulnerabilidades de acesso a arquivos de workflow restringindo operações a diretórios autorizados, impedindo o acesso não autorizado e a possível execução remota de código. (NEO-88460)
* Adição do URL FTP, que incluir na lista de permissões os controles às atividades de fluxo de trabalho do código JavaScript, restringindo as conexões de FTP de saída somente aos endereços autorizados. (NEO-89083)

### Outras alterações {#changes-8-9-1}

* Gerenciamento aprimorado da memória do contêiner ao implementar a limitação automática do fluxo de trabalho durante condições de alta memória, com recursos inteligentes de reinicialização do fluxo de trabalho e medidas de proteção de memória para processos não críticos. (NEO-89041)
* Adição de suporte para funções de criptografia assimétrica e descriptografia em workflows do Campaign. (NEO-80257)
* Desempenho aprimorado do agente de replicação e resiliência de memória para uploads de dados grandes em implantações FFDA. (NEO-88430)


### Correções {#fixes-8-9-1}

* Correção de um problema em que a estrutura do banco de dados não podia ser atualizada após alterações de sysFilter. (NEO-93306)
* Correção de um problema em que os dados de relatórios dinâmicos não apareciam após a migração. (NEO-92962)
* Correção de um problema em que o status do delivery não era atualizado corretamente. (NEO-92908)
* Correção de um problema relacionado à restrição do Catálogo de uso do Databricks FDA. (NEO-92900)
* Correção de um problema que poderia causar erros de layout do HTML na área de trabalho do Outlook Windows. (NEO-92611)
* Correção de um problema de integridade de dados em que as chaves primárias de entrega eram duplicadas na instância intermediária após uma atualização. (NEO-92424)
* Correção de um problema em que os links não podiam ser desativados na caixa de diálogo Tracking &amp; Images em um delivery. (NEO-92381)
* Correção de um problema em que a função nms.subscription.RecipientSubscribe() não funcionava para assinatura em massa. (NEO-92308)
* Correção de um problema em que as falhas de entrega ocorriam devido à falta de partes da entrega após uma atualização. (NEO-92278)
* Correção de um problema no workflow de rastreamento em que erros de status duplicados e erros de sintaxe SQL impediam a atualização dos indicadores de rastreamento. (NEO-92239)
* Correção de um problema em que os rótulos dos campos de enumeração estavam ausentes ou eram exibidos incorretamente em listas criadas por meio do fluxo de trabalho ao usar campos dbEnum. (NEO-91158)
* Correção de um problema em que a caixa de diálogo Publicar/desfazer publicação do RT não fechava e congelava. (NEO-91038)
* Correção de um problema que ocorria para destinatários com o status &quot;Considerado pelo provedor de serviço&quot;. (NEO-90927)
* Correção de um problema em que a origem da (des)assinatura estava ausente para links para opção de não participação. (NEO-90714)
* Correção de um problema em que a adição de cupons falhava na preparação do delivery. (NEO-90547)
* Correção de um problema em que Inserir contagem de rejeição não era refletida com precisão na guia Auditoria. (NEO-90318)
* Correção de um problema de segurança que poderia causar negação de serviço do aplicativo. (NEO-89984)
* Correção de um problema em que o PDF baixado do relatório Hotclick era interrompido. (NEO-89954)
* Correção de um erro SSL que ocorria após uma atualização, causando EOF inesperado ao ler erros. (NEO-89108)
* Correção de um problema em que os dados não podiam ser consultados em um esquema de dados após uma atualização. (NEO-88663)
* Correção de um erro que ocorria ao concatenar um campo &quot;char&quot; no PostgreSQL 15. (NEO-88028)
* Correção de um problema em que a ordem das variáveis do template do delivery era alterada ao salvar ou duplicar o template. (NEO-87845)
* Correção de um problema em que a criação de um novo esquema da Biblioteca de dados causava uma falha na interface da Web. (NEO-87816)
* Correção de um problema em que com conjuntos complementares na atividade Desduplicação. (NEO-87711)
* Correção de uma solicitação para o pacote de instalação sem dependência X11. (NEO-87471)
* Correção de um problema em que os códigos de segmento não podiam ser usados em relatórios dinâmicos. (NEO-87276)
* Correção de um problema em que os workflows travavam na atividade Atualizar dados. (NEO-87252)
* Correção de um problema em que o BigQuery estava usando um fuso horário incorreto. (NEO-86622)
* Correção de um erro de JavaScript que ocorria ao avaliar o script &quot;mcSynch_mcExec1/jsReplicateUrl&quot;. (NEO-86553)
* Correção de um problema em que eventos duplicados apareciam na tabela eventHisto devido a um método de cálculo de identificador incorreto. (NEO-86544)
* Correção de um problema em que a guia Avançado não era exibida para o iOS Push na cópia. (NEO-86231)
* Correção de um problema em que o fluxo de trabalho de replicação de tabelas de referência falhava ao replicar o esquema nms:delivery. (NEO-85884)
* Correção de um problema em que erros de domínio nulo correspondentes a endereços MXIP apareciam em logs de erro ao enviar deliveries. (NEO-85238)
* Correção de um problema em que os templates técnicos do delivery não eram atualizados após alterações feitas nas opções. (NEO-84149)
* Correção de um erro no fluxo de trabalho de faturamento pronto para uso. (NEO-83624)
* Correção de um problema com a exclusão de duplicatas com base apenas na chave primária de registros direcionados. (NEO-82910)
* Correção de discrepâncias nos relatórios da interface da Web do Campaign, em que as estatísticas de rastreamento exibiam valores diferentes em comparação ao console. (NEO-82339)
* Correção de um problema em que a data da última modificação era alterada mesmo se o registro não deveria ser atualizado na atividade Atualizar dados. (NEO-82002)
* Correção de um problema em que a adição de novos atributos em uma lista causava a falha dos workflows que liam a lista. (NEO-80258)
* Correção de um problema em que o relatório de Indicadores de rastreamento exibia valores incorretos para aberturas distintas. (NEO-79466)