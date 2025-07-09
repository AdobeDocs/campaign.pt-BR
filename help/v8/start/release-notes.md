---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d607981e99c22bed81aa6c321b891226816a8004
workflow-type: tm+mt
source-wordcount: '2168'
ht-degree: 13%

---

# Versões mais recentes {#latest-release}

Esta página lista novos recursos, melhorias e correções das **últimas versões** do Campaign v8 (console). Saiba mais sobre lançamentos, versões e atualizações do Campaign [nesta página](upgrades.md). Outras versões estão listadas na seção Versões anteriores desta documentação.

## Versão 8.8.1 {#release-8-8-1}

_quinta-feira, 9 de julho de 2025_

### Novos recursos {#features-8-8-1}

Anteriormente lançado para um pequeno conjunto de clientes, o seguinte recurso agora está disponível para todos os ambientes FDA do Campaign:

* **Novo conector de envio de SMS** - O conector de envio de SMS foi modernizado e aprimorado para habilitar conexões SMPP no modo transceptor, habilitar conexões SMPP persistentes e garantir melhor compatibilidade. Uma nova conta externa de SMS agora está disponível para todas as novas implementações de SMS. A implementação atual ainda é compatível, mas é recomendável mudar para esse novo conector moderno e estendido. [Leia mais](../send/sms/sms.md)

  >[!NOTE]
  >
  >Este recurso **não** está disponível para [implantações do FFDA do Campaign](../architecture/enterprise-deployment.md).

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

Anteriormente lançado com Disponibilidade Limitada, o seguinte recurso agora está disponível **sob demanda**:

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **APIs Rest** - Agora você pode usar as APIs Rest para criar integrações com o Adobe Campaign e criar seu próprio ecossistema, conectando o Adobe Campaign ao painel de tecnologias que você usa. A API REST de mensagens transacionais também está disponível para o canal SMS. Quando email e mobilePhone estão presentes no conteúdo, você pode usar o campo “wishedChannel” para especificar o canal. Se não for fornecido, o email será usado por padrão, a menos que wishedChannel solicite explicitamente SMS. APIs transacionais baseadas em eventos também estão disponíveis para emails. [Leia mais](../dev/api/get-started-apis.md)

  >[!NOTE]
  >
  >Este recurso **não** está disponível para [implantações do FFDA do Campaign](../architecture/enterprise-deployment.md).

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

Além dos recursos listados acima, esta versão também vem com um conjunto de funcionalidades disponíveis no Campaign, na interface do usuário da Web:

* [Criação de entrega multilíngue](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html#multilingual-delivery){target="_blank"}
* [Alerta de entrega](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
* [Melhorias nas páginas de aterrissagem](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html){target="_blank"}
* [Dynamic Reporting](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"} (somente sob demanda)
* [Marca Centralizada](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

Consulte as [notas de versão](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=pt-BR){target="_blank"} da interface da Web do Campaign.

### Melhorias gerais {#improvements-8-8-1}

* O Microsoft Fabrics agora é compatível como um banco de dados externo com o FDA (Federated Data Access — Acesso a Dados Federados) da Adobe Campaign. [Leia mais](../config/external-accounts.md#transfer-data-external-accounts)
* O Campaign v8 agora é compatível com notificações por push no Android 15 e iOS 18. [Leia mais](../start/compatibility-matrix.md#MobileSDK)
* Os bancos de dados em nuvem agora são suportados, além dos bancos de dados locais para o encapsulamento de Rede privada virtual segura. [Leia mais](../config/enhanced-security.md#vpn-databases)
* Um novo conjunto de campos &quot;ID do provedor&quot; foi adicionado na seção &quot;Tráfego de entrada&quot; do conector SMS 2.0. [Leia mais](../send/sms/smpp-external-account.md#incoming-traffic)
* Os recipients não inscritos por meio do método &quot;mailto&quot; List-Unsubscribe não são mais enviados para quarentena. Eles têm a subscrição cancelada do serviço associado ao delivery ou são enviados para a inclui na lista de bloqueios (seção &quot;Não entrar em contato mais&quot; do perfil) se nenhum serviço tiver sido definido para o delivery. [Leia mais](../send/quarantines.md)
* Uma versão renovada do relatório de renderização da caixa de entrada agora está disponível no console do cliente do Adobe Campaign. [Leia mais](../send/inbox-rendering.md)

### Correções {#fixes-8-8-1}

* Correção de um problema em que as respostas automáticas não eram recebidas devido a um período de validade inválido no SMS 2.0. Isso garante a entrega adequada de mensagens após a migração. (NEO-88088)
* Solução de um problema no SMS 2.0 em que determinados campos na tabela `inSms` não eram atualizados corretamente, garantindo a inserção de dados precisos para funcionalidades de SMS. (NEO-87906)

<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
-->

* Um mecanismo de instalação silenciosa foi fornecido para o console do cliente para facilitar atualizações em massa sem a intervenção do usuário. Isso soluciona os desafios das instalações manuais. (NEO-69772)
* Correção de falhas no fluxo de trabalho de limpeza do banco de dados devido a referências de coluna ausentes ou incorretas em consultas SQL. Isso garante a limpeza adequada de logs e dados de visitantes. (NEO-86813)
* Solução de um problema em que as datas de evento estavam ausentes nos logs de entrega. Essa correção garante o preenchimento preciso da data do evento, essencial para acionadores e workflows programados. (NEO-86708)
* Correção de problemas de inserção de log de entrega de SMS no SMS 2.0, garantindo o logon adequado na tabela `nmsBroadLogMid`. (NEO-86556)
* Solucionado o problema de extração de arquivos com o modo de entrega externa em modelos de correspondência direta, garantindo a compatibilidade e a funcionalidade. (NEO-86520)
* Solução de problemas de processamento de delivery que envolviam o roteamento dividido em várias instâncias MID, garantindo atualizações precisas do status do delivery e taxa de transferência. (NEO-86500)
* Correção de dados ausentes de rastreamento em relatórios dinâmicos após a migração do Campaign Standard para o Campaign v8, garantindo relatórios precisos para logs de rastreamento de delivery. (NEO-86419)
* Correção de problemas de acionamento de workflows em que eram executados duas vezes, causando violações de chave duplicadas. Essa correção garante a manipulação e a execução adequadas dos eventos. (NEO-86154)
* Correção de problemas de compatibilidade com as funções SQL OOTB do Redshift após a implantação, garantindo a execução adequada de funções como `GetDate()` em fluxos de trabalho. (NEO-85834)
* Problemas de renderização resolvidos em builds de email em que as imagens desapareciam quando os URLs eram anexados. Essa correção garante a exibição adequada da imagem nas visualizações da caixa de entrada. (NEO-85716)
* Renderização corrigida de aspas de fechamento curvas na WebUI, garantindo a exibição precisa de caracteres nos deliveries de email. (NEO-85687)
* Correção da funcionalidade de link de mirror page, garantindo a navegação adequada entre variantes de idioma nas mirror pages. (NEO-85625)
* Solução de problemas de formato de data em seletores de data de aplicativo Web, garantindo a compatibilidade com formatos de data japoneses (`yyyy-mm-dd`). (NEO-85234)
* Correção de problemas de workflow pós-processamento com configurações alternativas de roteamento no midsourcing, garantindo a execução adequada do workflow. (NEO-85111)
* Taxa de transferência de delivery do Android aprimorada ao usar ondas, garantindo que as partes do delivery sejam processadas na ordem correta com base no agendamento. (NEO-84324)
* Correção de falhas na preparação da entrega devido a erros de processamento nulos na função `to_varchar`, garantindo inicializações de campanha sem problemas. (NEO-84108)
* Solução de problemas de conexão SFTP causados por versões `libcurl` e `libssh2` desatualizadas, garantindo a compatibilidade com servidores SFTP hospedados pelo Azure. (NEO-84038)
* Correção de problemas de conector FDA do Snowflake que envolviam erros de autenticação de par de chaves, garantindo conexões de banco de dados bem-sucedidas. (NEO-84024)
* Problemas de funcionalidade da regra de tipologia resolvidos, garantindo a aplicação adequada das regras de pressão nos deliveries de PUSH. (NEO-84010)
* Correção de erros de consulta do BigQuery causados por comparações incompatíveis de data e carimbo de data e hora após a atualização, garantindo a compatibilidade com condições de filtragem. (NEO-83826)
* Solução de um problema em que as atividades de delivery falhavam ao retomar deliveries pausados devido a erros de personalização. Essa correção garante workflows de delivery mais suaves e evita erros relacionados a atividades pausadas. (NEO-83809)
* Correção de um problema no FFDA ao usar a opção &quot;target record load query&quot;. Foi adicionado suporte às cláusulas &quot;pedir por&quot; e &quot;onde&quot;. (NEO-83793)
* Endereçadas as falhas recorrentes de delivery causadas pela gravação de valores nulos em colunas não anuláveis na tabela broadLogRcp. Essa correção melhora a confiabilidade do delivery e evita erros durante campanhas ativas. (NEO-83729)
* Solução de um problema em que os seed addresses eram duplicados durante a preparação do delivery, gerando discrepâncias nas contagens de mensagens. Essa correção garante o direcionamento preciso e evita erros de duplicação. (NEO-83703)
* Correção de um problema crítico em que os deliveries de produção eram enviados após o período de validade, possivelmente causando preocupações legais. Os deliveries agora seguem estritamente os períodos de validade definidos. (NEO-83350)
* Solucionado o problema de espaço encontrado ao carregar grandes volumes de dados em tabelas do Teradata. Essa correção otimiza o processamento de dados e soluciona erros intermitentes em ambientes de produção. (NEO-83252)
* Correção de uma falha técnica de fluxo de trabalho relacionada aos erros SendMetricsToNewRelic, que causavam atrasos no processamento do evento RT. Essa correção garante uma execução de fluxo de trabalho mais tranquila e evita registros retroativos de eventos. (NEO-83143)
* Correção de uma falha no fluxo de trabalho de limpeza do banco de dados causada por problemas de conversão de ID em UUID nas instâncias de interação do FFDA. Essa atualização garante operações de limpeza adequadas e reduz a carga do sistema. (NEO-83138)
* Correção de falhas de delivery causadas por restrições nos comprimentos de nome interno do membro de seed. Essa correção permite nomes internos mais longos sem afetar a personalização de delivery. (NEO-83044)
* Correção de um problema em que as entregas ficavam presas na personalização devido a erros aleatórios. Essa atualização garante processos de personalização mais simples e execução de delivery confiável. (NEO-82781)
* Correção de um problema em que as apresentações de oferta não podiam ser revisadas no console devido a erros de API e lentidão. Essa correção melhora a capacidade de resposta da interface do usuário e garante a funcionalidade de oferta adequada. (NEO-82742)
* Solução de falhas intermitentes no console do Adobe Campaign ao usar objetos de entrega personalizados. Essa correção garante a estabilidade e a confiabilidade ao trabalhar com workflows personalizados. (NEO-82675)
* Correção de falhas de processamento lento e de fluxo de trabalho relatadas após a migração da v7 para a v8. Essa atualização otimiza os workflows da campanha e garante a execução oportuna. (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* Correção de um problema crítico em que os processos filho do MTA estavam travados, bloqueando os deliveries de Push e WhatsApp. Essa atualização garante workflows de comunicação mais tranquilos e evita gargalos de delivery. (NEO-82351)
* Foi resolvido um problema de migração de dados em que os campos de sequência de caracteres das tabelas GCP causavam erros durante as atualizações do Teradata. Essa correção elimina a necessidade de soluções alternativas e melhora a eficiência do fluxo de trabalho. (NEO-82260)
* Atualização da lógica de limpeza do banco de dados para levar em conta os bancos de dados principais em instâncias do FFDA, evitando tentativas desnecessárias de limpar tabelas inexistentes. Essa correção otimiza as operações de limpeza. (NEO-81879)
* Correção de falhas de console causadas pelo uso de subworkflows em combinação com campos enum. Essa correção garante a estabilidade ao trabalhar com workflows enriquecidos. (NEO-81864)
* Correção de um problema em que os campos de subafinidade nos target mappings eram modificados incorretamente após a duplicação do delivery, causando falhas no workflow. Essa atualização garante valores consistentes de subafinidade. (NEO-81809)
* Adição de suporte a caracteres curingas em atividades de transferência de arquivos no Adobe Campaign Classic v8, permitindo que os usuários carreguem arquivos com nomes dinâmicos (por exemplo, `abc_*`) em fluxos de trabalho. (NEO-81758)
* Introdução de uma opção para habilitar o sinalizador `content-available` nas notificações por push do iOS para Adobe Campaign Classic v8. Esse aprimoramento permite que os aplicativos móveis armazenem notificações na caixa de entrada e oferece suporte a atualizações em segundo plano, solucionando problemas de descarte de delivery causados por limitações de APNS. (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* Adicionada uma opção de configuração de tempo limite para conexões do BigQuery no Adobe Campaign Classic v8. Esse aprimoramento permite que os usuários ajustem o período de tempo limite para consultas, resolvendo problemas com falhas de consulta devido a limites de tempo limite padrão. (NEO-81222)
* Correção de um problema intermitente em que os URLs de mirror page falhavam em entregas enviadas por contas externas de Divisão e Roteamento alternativo após a migração v8. As partes de entrega subjacentes foram copiadas corretamente para `mirrorPageInfo`. (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* Correção do botão &quot;Acessar a nova interface da Web&quot; no console do cliente para apontar para a URL correta (`https://experience.adobe.com`) para instâncias de produção. Isso soluciona problemas com URLs inválidos em ambientes de produção. (NEO-80673)
* Correção de um problema na atividade Split em que o uso de Classificação e Tamanho (como uma porcentagem do segmento) causava erros de SQL. A funcionalidade agora funciona corretamente. (NEO-80432)
* Solução de um problema de falha em fluxos de trabalho usando o `CCurlAzureBlobStorage::UploadStream`. Agora os fluxos de trabalho são executados sem falhas de segmentação durante os uploads do Armazenamento Azure Blob. (NEO-79598)
* Solução de um problema em que as mirror pages não eram visualizadas no console do cliente em ambientes de produção. Os links da mirror page agora funcionam corretamente nas exibições de email e do console. (NEO-78946)
* Correção de um problema de log de delivery em que alguns logs eram marcados incorretamente como &quot;Delivery canceled&quot; apesar do delivery bem-sucedido da mensagem. A causa raiz relacionada às discrepâncias de data de contato e data do evento foi abordada. (NEO-78933)
* Atualização da biblioteca `com.google.code.gson:gson` para melhorar a segurança. (NEO-78299)
* Correção de erros de restrição de chave duplicada nos logs de conexão FDA (`nmsconnectionlogs`) que causaram falhas de fluxo de trabalho. A lógica de inserção foi ajustada para evitar IDs duplicadas. (NEO-78050)
* Correção de um problema em que os endereços de email em quarentena eram sinalizados incorretamente como móveis na tabela de endereços, causando erros de análise do delivery. A lógica de reconciliação entre os objetos de entrega foi corrigida. (NEO-76986)
* Corrigida uma falha de preparação de delivery ao usar grupos de controle com um banco de dados do Oracle. A geração de consultas SQL foi corrigida para garantir a compatibilidade com bancos de dados Oracle. (NEO-76947)
* Correção de falhas de delivery causadas pela criação simultânea de pastas durante transições de novos meses. A lógica de criação da pasta de entrega foi ajustada para evitar violações de chave duplicadas. (NEO-76824)
* Correção de problemas de conversão de fuso horário inconsistentes em contas externas do Teradata. Os carimbos de data e hora exibidos agora estão alinhados corretamente às configurações de fuso horário definidas. (NEO-76716)
* Workflows de limpeza de banco de dados aprimorados para lidar com grandes conjuntos de dados com eficiência. Uma nova abordagem usando IDs de linha e variáveis de ligação foi implementada para otimizar o desempenho da exclusão. (NEO-76439)
* Solução de um problema em que os deliveries externos com o canal &quot;Outro&quot; não geravam arquivos de saída. As propriedades de delivery agora incluem corretamente o caminho do arquivo para arquivos gerados. (NEO-75962)
* Correção de erros no fluxo de trabalho `ffdaReplicateStagingData` causados por atualizações de dados grandes. As configurações de tempo limite e o gerenciamento de tamanho de tabela foram otimizados para evitar falhas no fluxo de trabalho. (NEO-75643)
* Correção de um problema em que a pré-visualização de arquivos de saída de correspondência direta fazia com que os painéis ficassem em branco. O painel agora é exibido corretamente após as visualizações de arquivo. (NEO-75359)
* Indicadores de rastreamento aprimorados para notificações por push para incluir cliques e aberturas. Indicadores como `@recipientClick`, `@personClick` e `@totalRecipientClick` agora são responsáveis por cliques de notificação móvel. (NEO-75240)
* Correção de erros em workflows de limpeza para deliveries com status externos de cancelamento pendente. A lógica de recuperação de registros do banco de dados foi corrigida. (NEO-74833)
* Solução de um problema de discrepância de fuso horário na Rússia (UTC+3:00 Moscou) em que os horários de saída de `nlserver` estavam incorretos. A lógica de sincronização de tempo foi atualizada. (NEO-74754)
* Correção de erros no fluxo de trabalho `defaultMidSourcingDlvStat` causados por sintaxe SQL incorreta para bancos de dados MSSQL. A lógica de geração de consulta foi ajustada para fins de compatibilidade. (NEO-74156)
* Foram solucionadas várias falhas no processo da Web. (NEO-73174)
* Correção de um problema em que as consultas do BigQuery falhavam quando apóstrofos estavam presentes em condições. A lógica de manipulação de consultas foi atualizada para interpretar corretamente caracteres especiais. (NEO-72547)
* Correção de um problema em que as regras de tipologia com filtros de exclusão não funcionavam corretamente. A geração de consultas SQL para preparação de entrega foi corrigida. (NEO-72292)
* Discrepâncias abordadas em datas de evento e datas de contato para o gerenciamento de rejeição. A lógica de manipulação de fuso horário foi aprimorada. (NEO-72277)
* Manuseio aprimorado de caracteres UTF-8 convertidos incorretamente em deliveries de correspondência direta. Os caracteres ocultos agora são processados corretamente para evitar falhas de delivery. (NEO-72148)
* Correção de erros na atividade de SMS de Entrada, em que os filtros causavam problemas de salvamento. O workflow agora é salvo corretamente sem gerar erros. (NEO-70427)
* Geração de consulta SQL corrigida para critérios de qualificação agrupados em espaços de oferta. Parênteses ausentes nas condições SQL foram adicionados para garantir a filtragem adequada. (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* Correção de erros intermitentes em workflows de carregamento de dados do BigQuery causados por conteúdo HTTP ou problemas de codificação de transferência. A lógica de manipulação de conexões foi aprimorada. (NEO-66989)

