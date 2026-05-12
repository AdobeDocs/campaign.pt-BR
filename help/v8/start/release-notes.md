---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
TQID: https://experienceleague.adobe.com/Zdo52RLQFbxlRNgE54yLDn3yAMmmOqxKyRhnCJa0Xwg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ffeb9430b382b598af412555b1b0a6ff42bc68d0
workflow-type: tm+mt
source-wordcount: 1747
ht-degree: 6%

---

# Versões mais recentes {#latest-release}

Esta página lista novos recursos, melhorias e correções das **últimas versões** do Campaign v8 (console). Saiba mais sobre lançamentos, versões e atualizações do Campaign [nesta página](upgrades.md). Outras versões estão listadas na seção Versões anteriores desta documentação.

## Versão 8.9.2 {#release-8-9-2}

>[!CAUTION]
>
> A atualização do Console do Cliente é obrigatória. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

_3 de maio de 2026_

### Melhorias de segurança {#security-8-9-2}

* Para manter segurança, estabilidade e conformidade ideais, todas as instâncias foram atualizadas para Debian 13 e PostgreSQL 17.

### Correções {#fixes-8-9-2}

>[!NOTE]
>
> As correções listadas abaixo foram progressivamente implementadas em builds 8.9.2 sucessivas. Navegue até o **[!UICONTROL Help > About...]** [menu](upgrades.md#version) para verificar se você tem a build 8.9.2 (11d1c68) mais recente. Entre em contato com seu representante da Adobe para obter mais informações.

* Correção de um problema em que as datas de evento em eventos transacionais eram definidas incorretamente devido a um problema de conversão do tipo de dados, causando datas incorretas em relatórios dinâmicos. (NEO-93923)
* Correção de um problema em que as notificações por push silenciosas do Android e do iOS falhavam durante a preparação do delivery quando os campos de título e corpo estavam vazios. (NEO-93739)
* Correção de um problema que impedia que o campo de idioma fosse capturado para tokens de registro de aplicativo do Android devido a chaves de reconciliação incorretas. (NEO-93100)
* Correção de um problema em que a preparação do delivery falhava ao aplicar regras de tipologia personalizadas com regras de pressão. (NEO-94457)
* Correção de um problema em que o console do cliente podia enfrentar falhas de processamento de solicitação HTTP. (NEO-94071)

<!-- BUILD 8.9.2.9829.9669833 -->

* O monitoramento FDA agora está desabilitado por padrão para evitar erros de inserção no log de conexão. (NEO-94841)
* Correção de um problema em que as chamadas de Interaction SOAP usadas para resgate de oferta podiam falhar com um erro de resolução de namespace. (NEO-94787)
<!-- infra * Fixed an issue where Snowflake connections using private key authentication could fail on ARM64 architectures. (NEO-94350) -->
* Correção de um problema em que campos de sequência com comprimento 1 podiam causar erros SQL em tabelas temporárias de workflow no PostgreSQL 17. (NEO-94487)
<!-- linked to previous build * Fixed an issue where the server could fail to restart after a Debian 13 build upgrade due to a missing dependency. (NEO-94598) -->

<!-- BUILD 8.9.2.9829.c90aa36 -->

* Correção de um problema em que a opção **Exibir página espelhada** no Console do Cliente e na Interface do Usuário da Web retornava um erro &quot;Página espelhada inválida&quot;. (NEO-93303)

<!-- BUILD 8.9.2.9830.4a6f868 -->

* Correção de um problema em que o fluxo de trabalho técnico **Rastreamento** pronto para uso poderia falhar após uma instalação de pacote multivariante em implantações FFDA. (NEO-94972)
* Correção de um problema em que a preparação do delivery poderia falhar ao adicionar qualquer recipient ao target quando o template do delivery usava uma fórmula de peso que referenciava o delivery atual. (NEO-94892)
<!-- hotfix -->
* Correção de um problema em que os enriquecimentos de workflow usando junções em dois links 1-N consecutivos podiam falhar com erros SQL após uma atualização. (NEO-94893)

<!-- BUILD 8.9.2.9831.f53d3d2 -->

* Correção de um problema no pipeline de email que poderia resultar no consumo excessivo de memória ao longo do tempo. (NEO-95088)
* Correção de um problema em que a regra de tipologia de email conflitante podia excluir incorretamente recipients não duplicados de um target de delivery quando seed addresses ou endereços de prova eram usados. (NEO-95026)
* Correção de um problema em que o fluxo de trabalho técnico **Notificação de oferta** pronto para uso poderia falhar após uma atualização. (NEO-95064)
* O processo de instalação de pacote multivariante foi aprimorado para evitar falhas de fluxo de trabalho de rastreamento durante atualizações de build. (NEO-95018)

<!-- BUILD 8.9.2.9831.11d1c68 -->

* Correção de um problema que resultava em falha repetida do servidor, resultando em interrupções da instância. (NEO-95304)
* Correção de um problema em que os links de rastreamento e de mirror page podiam falhar ao carregar os deliveries. (NEO-95239)
* Correção de um problema que poderia causar um loop de redirecionamento ao fazer logon em aplicativos Web do Campaign protegidos por logon único IMS. (NEO-95188)
* Correção de um problema em que a data de criação do delivery não estava nos arquivos de extração do delivery após salvar o delivery. (NEO-95010)
* Correção de um problema em que os fluxos de trabalho filhos gerados em grande volume podiam permanecer presos no estado **Sendo editado**, reduzindo a capacidade do fluxo de trabalho transacional. (NEO-95131)
* Correção de um problema em que a atividade **Lista de Leitura** poderia substituir modelos de lista predefinidos por estruturas de lista geradas por fluxo de trabalho, causando falhas em fluxos de trabalho downstream. (NEO-95103)
* Correção de um problema em que o tratamento de feedback por notificação por push podia causar falha no servidor ao processar deliveries de alto volume. (NEO-95150)
* Correção de um problema em que a abertura da guia **Dados** no esquema `xtk:workflow` no explorador de esquemas poderia disparar uma mensagem de erro. (NEO-94923)
<!-- hotfixes -->
* Correção de um problema em que a atividade **Enriquecimento** não podia mais recuperar atributos de saída das atividades upstream **Subworkflow**, causando falha nos fluxos de trabalho. (NEO-95151)
* Correção de um problema de assimilação de dados de rastreamento que podia impedir atualizações de status do delivery e bloquear o processamento de mensagens downstream. (NEO-94666)
* Correção de um problema em que determinadas ações do Console do cliente relacionadas às apresentações de oferta podiam acionar consultas de longa execução em bancos de dados Snowflake, causando bloqueios e lentidão. (NEO-92936)
* Correção de um problema em que não era possível configurar opções personalizadas para armazenar chaves criptografadas em contas externas do Snowflake. (NEO-93302)

<!-- 
Internal/non-customer-facing:
* Internal test automation task added to cover NEO-94893. (NEO-94990) — autotest only
Customer-specific hotfixes:
* Fixed an issue affecting WhatsApp delivery preparation. (NEO-92480) — HeroMotoCorp only
* Added a feature-flagged optimization to use dynamic shared memory in Customer Targeting Audience (CTA) processing. (NEO-93542) — DerTour only
* Fixed an issue where the delivery alerting workflow could fire incorrect "long start pending" notifications even when deliveries were sent within the configured threshold. (NEO-93434) — non-ZDT hotfix, NORC only
* Added a new parameter in the mobile SDK to allow identification of the source instance for push notifications. (NEO-94650) — ICICI only
* Fixed an issue with the custom send time feature on the Web UI where deliveries waited until the contact date and time to execute instead of executing at the equivalent local time per recipient timezone, breaking parity with Campaign Standard behavior. (NEO-94762) — H&M only (in progress at time of writing)
-->

## Versão 8.9.1 {#release-8-9-1}

_27 de janeiro de 2026_

>[!CAUTION]
>
> A atualização do Console do Cliente é obrigatória. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

### Novos recursos {#new-8-9-1}

O **novo conector de envio de SMS** agora está disponível para todos os clientes (GA). Consulte a [documentação detalhada](../send/sms/sms.md).

Esta versão é fornecida com um conjunto de funcionalidades disponíveis na interface da Web do Campaign:

* [Recursos de entrega multilíngue (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=pt-BR){target="_blank"}
* [Enriquecimento de Perfil em Mensagens Transacionais (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=pt-BR){target="_blank"}
* [Adobe Experience Manager live e cópias de idioma](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html?lang=pt-BR){target="_blank"}
* [Experimentos de conteúdo - teste A/B](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=pt-BR){target="_blank"}
* [Atividade de entrega contínua](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=pt-BR){target="_blank"}
* [Gerenciamento de aprovação de campanha](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=pt-BR){target="_blank"}

Consulte as [notas de versão](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=pt-BR){target="_blank"} da interface da Web do Campaign

### Melhorias de segurança {#security-8-9-1}

* As contas externas do Snowflake agora oferecem suporte à autenticação OAuth2, fornecendo métodos de autenticação modernos e seguros para conexões de acesso a dados federados. (NEO-87013) [Leia mais](../config/external-accounts.md#snowflake-external-accounts)
* As contas externas de databricks agora oferecem suporte à autenticação OAuth2 por meio da entidade de serviço (fluxo de credenciais de cliente não interativo), fornecendo métodos de autenticação seguros para conexões de acesso a dados federados. A autenticação OAuth2 interativa estará disponível em uma versão futura. (NEO-87422) [Leia mais](../config/external-accounts.md#databricks-external-accounts)
* Correção de vulnerabilidades de acesso a arquivos de workflow restringindo operações a diretórios autorizados, impedindo o acesso não autorizado e a possível execução remota de código. (NEO-88460)
* Adição do URL FTP, que incluir na lista de permissões os controles às atividades de fluxo de trabalho do código JavaScript, restringindo as conexões de FTP de saída somente aos endereços autorizados. (NEO-89083)

### Outras alterações {#changes-8-9-1}

* Gerenciamento aprimorado da memória do contêiner ao implementar a limitação automática do fluxo de trabalho durante condições de alta memória, com recursos inteligentes de reinicialização do fluxo de trabalho e medidas de proteção de memória para processos não críticos. (NEO-89041)
* Adição de suporte para funções de criptografia assimétrica e descriptografia em workflows do Campaign. (NEO-80257)
* Desempenho aprimorado do agente de replicação e resiliência de memória para uploads de dados grandes em implantações FFDA. (NEO-88430)
* As atividades de fluxo de trabalho **[!UICONTROL SQL code]** e **[!UICONTROL SQL Data Management]** foram aprimoradas para proteger melhor os bancos de dados PostgreSQL e manter seus fluxos de trabalho em execução sem problemas quando o SQL personalizado é executado do Campaign. Consulte [SQL Data Management](../../automation/workflow/sql-data-management.md#important-notes) e [SQL code](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) para obter mais informações e práticas recomendadas. (NEO-86540)


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