---
title: Notas de versão do Campaign v8 (console) de 2024
description: Lista de recursos e melhorias disponíveis nas versões do Campaign v8 2024
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 91%

---

# Notas de versão de 2024 {#2024-rn}

Esta página lista novos recursos, melhorias e correções incluídos nas **versões do Campaign v8 de 2024**.  Para obter a versão mais recente, consulte [esta página](release-notes.md).

Para qualquer nova implementação ou atualização para um ambiente existente, instale a [versão mais recente](release-notes.md).


>[!BEGINSHADEBOX]

**Nesta página**

* Campaign v8.7: [Versão 8.7.1](#release-8-7-1) | [Versão 8.7.2](#release-8-7-2)
* Campaign v8.6 - [Versão 8.6.1](#release-8-6-1) | [Versão 8.6.2](#release-8-6-2) | [Versão 8.6.3](#release-8-6-3)
* Campaign v8.5 - [Versão 8.5.3](#release-8-5-3)

>[!ENDSHADEBOX]

## Versão 8.7.2 {#release-8-7-2}

_3 de setembro de 2024_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa migração na [documentação da interface do Campaign Web v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Novos recursos {#new-8-7-2}

* **Novo conector de envio de SMS**: o conector de envio de SMS foi modernizado e aprimorado para permitir conexões SMPP no modo transceptor, permitir conexões SMPP persistentes e garantir uma melhor compatibilidade para ambientes em transição do Adobe Campaign Standard. Uma nova conta externa de SMS agora está disponível para todas as novas implementações de SMS. A implementação atual ainda é compatível, mas é recomendável mudar para esse novo conector moderno e estendido. [Leia mais](../send/sms/sms.md).

* **Notificação por push avançada (GA)**: agora, você pode enviar notificações por push avançadas. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. Com esta versão, um conjunto de modelos para notificações por push avançadas agora está disponível para aplicativos iOS e Android. [Leia mais](../send/rich-push-android.md).

* **Identidade visual**: agora, as opções de identidade visual estão disponíveis para todos os canais, inclusive SMS e correspondência direta. [Leia mais](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

### Correções {#fixes-8-7-2}

Os seguintes problemas foram corrigidos nesta versão:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.

## Versão 8.7.1 {#release-8-7-1}

_2 de maio de 2024_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa migração na [documentação da interface do Campaign Web v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Novos recursos {#new-8-7-1}

* **Modelos avançados de notificação por push**: agora você pode enviar notificações por push avançadas via Android. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. [Leia mais](../send/rich-push-ios.md).

* **Identidade visual**: como um usuário migrado do Campaign Standard, os administradores técnicos podem agora definir uma ou várias marcas para centralizar os parâmetros que afetam a identidade de uma marca. Isso inclui o logotipo da marca, o domínio do URL de acesso da página de destino ou as configurações de rastreamento de mensagens. Você pode criar essas marcas e vinculá-las a mensagens ou páginas de destino. Essa configuração é gerenciada nos modelos. [Leia mais](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

* **APIs REST**: como um usuário migrado do Campaign Standard, você pode usar as APIs REST para criar integrações com o Adobe Campaign e criar seu próprio ecossistema, conectando o Adobe Campaign ao painel de tecnologias que você usa. [Leia mais](../dev/api/get-started-apis.md)

* **Relatórios dinâmicos**: como um usuário migrado do Campaign Standard, você pode acessar os relatórios dinâmicos, que fornecem relatórios totalmente personalizáveis e em tempo real para medir o impacto de suas atividades de marketing. Eles adicionam acesso aos dados do perfil, permitindo análises demográficas por dimensões do perfil, como gênero, cidade e idade, além de dados funcionais de campanha de email, como aberturas e cliques. [Leia mais](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

### Atualizações de compatibilidade {#comp-8-7-1}

Os seguintes conectores FDA foram adicionados. Consulte esta [página](compatibility-matrix.md#FederatedDataAccessFDA).

* Os databricks agora são compatíveis como um banco de dados externo no Federated Data Access (FDA) do Adobe Campaign. 

* Agora há um novo conector ODBC de FDA do Amazon Redshift disponível. Ele oferece conectividade aprimorada, manutenção mais fácil e compatibilidade aprimorada. Essa nova versão traz as seguintes melhorias:

   * O novo conector é baseado na interface ODBC que se alinha aos conectores FDA mais recentes. Isso garante suporte a longo prazo.
   * Ele também introduz um novo mecanismo de carregamento de dados usando buckets s3, melhorando significativamente o desempenho.

  O conector legado ainda pode ser usado. Se quiser experimentar o novo, entre em contato com um(a) representante da Adobe.

### Migração para a credencial OAuth de servidor para servidor {#change-8-7-1}

A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. A Adobe executará a migração de JWT para OAuth em suas integrações de saída, como a integração do Campaign-Analytics ou a integração dos Acionadores da Experience Cloud.

Se você implementou integrações de entrada com o Campaign, é necessário migrar a Conta técnica conforme detalhada em [esta documentação](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. As credenciais da conta de serviço (JWT) já existentes continuarão a funcionar até **terça-feira, 30 de junho de 2025**. 

### Melhorias gerais {#improvements-8-7-1}

* Vários esquemas foram alterados de 32 para 64 bits. Isso se aplica somente aos clientes que estão migrando do Campaign Standard. [Leia mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=pt-BR){target="_blank"}

* Nas tabelas do Campaign, os seguintes atributos agora são preenchidos por padrão pela data/hora do servidor: `lastModified` e `created`. O valor do atributo `createdBy-id` agora é preenchido com a ID de logon atual por padrão. Os valores fornecidos pelos usuários em chamadas da API são ignorados. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Para aumentar a segurança de todas as comunicações entre aplicativos, o mTLS agora é compatível com chamadas de API externas.

### Correções {#fixes-8-7-1}

Os seguintes problemas foram corrigidos nesta versão:

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054



## Versão 8.6.3 {#release-8-6-3}

_30 de julho de 2024_

### Novos recursos {#new-8-6-3}

* **Notificação por push avançada**: agora você pode enviar notificações por push avançadas. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. Com esta versão, um conjunto de modelos para notificações por push avançadas agora está disponível para aplicativos iOS e Android. [Leia mais](../send/rich-push-android.md).

* A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. [Saiba mais](release-notes-2024.md#change-8-7-1)

### Melhorias gerais {#improvements-8-6-3}

* Para aumentar a segurança de todas as comunicações entre aplicativos, o mTLS agora é compatível com chamadas de API externas.

### Correções {#fixes-8-6-3}

Os seguintes problemas foram corrigidos nesta versão:

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## Atualizações de maio de 2024 {#may-updates}

A seguinte alteração foi lançada em maio e agora está disponível para usuários do Campaign v8:

* **Novo complemento de segurança aprimorado**: para proteger sua conexão de rede e fornecer mais segurança para seus recursos, o Adobe Campaign oferece um novo complemento de segurança aprimorado, que inclui dois recursos: integração de CMK segura e túneis seguros de VPN. [Leia mais](../config/enhanced-security.md)

## Versão 8.6.2 {#release-8-6-2}

_23 de fevereiro de 2024_

### Correções {#fixes-8-6-2}

Esta versão corrige o seguinte problema:

* Correção de um problema de desempenho que poderia ocorrer na instância mid-sourcing (NEO-72595).

## Versão 8.6.1 {#release-8-6-1}

_14 de fevereiro de 2024_

### Novos recursos {#new-8-6-1}

* A partir desta versão, você terá acesso à nova **Interface do Campaign Web**, disponível por meio do ambiente central do Adobe Experience Cloud. A Experience Cloud é a família integrada de aplicativos, produtos e serviços de marketing digital da Adobe. Com sua interface intuitiva, você pode acessar rapidamente os aplicativos em nuvem, recursos do produto e serviços. Saiba como se conectar à Adobe Experience Cloud e acessar a interface do Adobe Campaign Web [nesta página](campaign-ui.md#ac-web-ui).

  >[!AVAILABILITY]
  >
  >A interface do Campaign Web só está disponível para usuários que se conectam ao Adobe Campaign com sua Adobe ID. Saiba mais sobre o [Sistema de gerenciamento de identidades (IMS) da Adobe](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"}.
  >

* O Adobe Campaign v8 agora se integra ao **Adobe Experience Manager as a Cloud Service**, com criação disponível exclusivamente por meio da interface do Adobe Campaign Web. [Saiba mais](../connect/ac-aem.md)

* Agora é possível usar a **Biblioteca do Adobe Experience Manager Assets** junto com o Experience Cloud Assets, mesmo se o pacote de Integração com o Adobe Experience Cloud estiver instalado em sua instância do Adobe Campaign. [Saiba mais](../connect/ac-aem.md#assets-library)

### Melhorias gerais {#improvements-8-6-1}

* O Campaign v8.6 oferece taxa de transferência aprimorada para **indicadores de rastreamento de entregas de email**. Com nossos processos otimizados, o rastreamento da ingestão e do tempo de computação é reduzido, e você pode verificar os indicadores-chave da entrega muito mais rápido.


### Atualizações sobre capacidade de entrega {#deliverability-8-6-1}

* Até fevereiro de 2024, qualquer empresa que envie mais de 5.000 mensagens de email através do Google ou do Yahoo! terá que começar a usar uma tecnologia de autenticação conhecida como DMARC (Domain-based Message Authentication Reporting and Conformance). Certifique-se de que o registro DMARC esteja configurado para todos os subdomínios usados com o Adobe Campaign. [Saiba mais](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=pt-BR){target="_blank"}

* A partir de 1º de junho de 2024, o Google e o Yahoo! exigirão que os remetentes cumpram o Cancelamento de inscrição na lista com um clique. O Adobe Campaign agora é compatível com essa opção. [Saiba mais](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"}


### Correções {#fixes-8-6-1}

Os seguintes problemas foram corrigidos nesta versão:

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-6911 NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789



## Versão 8.5.3 {#release-8-5-3}

_28 de maio de 2024_

### Migração para a credencial OAuth de servidor para servidor {#change-8-5-3}

A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. [Saiba mais](#change-8-7-1)

### Correções {#fixes-8-5-3}

Os seguintes problemas foram corrigidos nesta versão:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542