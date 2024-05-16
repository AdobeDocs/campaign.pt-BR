---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: b4f54deaf35c852012a88d1445268bce9be4e8c1
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 100%

---

# Versão mais recente{#latest-release}

O Adobe Campaign é atualizado regularmente. Essa frequência regular de atualizações tem como objetivo disponibilizar a você o que há de melhor e mais recente, mantendo seu ambiente seguro e melhorando sua experiência com nosso produto. A Adobe recomenda que todos os clientes atualizem para a versão mais recente.

Como usuário do Managed Cloud Services, sua instância é atualizada pela Adobe a cada nova versão. A Adobe entrará em contato com você e atualizará seus ambientes. O console do cliente do Campaign **precisa ser atualizado para a mesma versão** dos servidores do Campaign. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

Além disso, como cliente, verifique se você está usando a versão compatível mais recente dos sistemas listados na [Matriz de compatibilidade](compatibility-matrix.md).

## Versão 8.7.1 {#release-8-7-1}

_2 de maio de 2024_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como um usuário Campaign Standard em transição para o Campaign v8, consulte [Transição do Campaign Standard para o Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/release-notes/acs-migration) e os [Recursos para usuários do Campaign Standard](https://experienceleague.adobe.com/docs/experience-cloud/campaign/campaign-standard-migration-home.html?lang=pt-BR).

### Novos recursos {#new-8-7-1}

* **Modelos avançados de notificação por push**: agora você pode enviar notificações por push avançadas via Android. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. [Leia mais](../send/rich-push.md)

* **Identidade visual**: como um usuário migrado do Campaign Standard, os administradores técnicos podem agora definir uma ou várias marcas para centralizar os parâmetros que afetam a identidade de uma marca. Isso inclui o logotipo da marca, o domínio do URL de acesso da página de destino ou as configurações de rastreamento de mensagens. Você pode criar essas marcas e vinculá-las a mensagens ou páginas de destino. Essa configuração é gerenciada em modelos. [Leia mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=pt-BR)

* **APIs REST**: como um usuário migrado do Campaign Standard, você pode usar as APIs REST para criar integrações com o Adobe Campaign e criar seu próprio ecossistema, conectando o Adobe Campaign ao painel de tecnologias que você usa. [Leia mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=pt-BR)

* **Relatórios dinâmicos**: como um usuário migrado do Campaign Standard, você pode acessar os relatórios dinâmicos, que fornecem relatórios totalmente personalizáveis e em tempo real para medir o impacto de suas atividades de marketing. Eles adicionam acesso aos dados do perfil, permitindo análises demográficas por dimensões do perfil, como gênero, cidade e idade, além de dados funcionais de campanha de email, como aberturas e cliques. [Leia mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=pt-BR)

<!--
* **New Enhanced security add-on**: To make your network connection more secure and provide improved security for your resources, Adobe Campaign offers a new Enhanced security add-on, which includes two features: Secure CMK integration and Secure VPN tunneling.
-->

### Atualizações de compatibilidade {#comp-8-7-1}

Os databricks agora são compatíveis como um banco de dados externo com o Federated Data Access (FDA) do Adobe Campaign. Saiba mais [nesta página](compatibility-matrix.md#FederatedDataAccessFDA).

### Melhorias gerais {#improvements-8-7-1}

* Vários esquemas foram alterados de 32 para 64 bits. Isso se aplica somente aos clientes que estão migrando do Campaign Standard. [Leia mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=pt-BR).

* Nas tabelas do Campaign, um novo sinalizador permite manipular modificações nos atributos lastModified, created e createdBy-id. Quando o sinalizador está ativado, os valores fornecidos pelos usuários para esses atributos são ignorados. Somente a hora e a ID do servidor do contexto do usuário são usadas. Quando o sinalizador está desativado, os valores fornecidos pelo usuário para esses atributos são usados. O sinalizador ignoreTimestampsID está localizado em serverConf.xml no nó “compartilhado”.

### Correções {#fixes-8-7-1}

Os seguintes problemas foram corrigidos nessa versão:
NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054

## Versão 8.6.2 {#release-8-6-2}

_23 de fevereiro de 2024_

### Correções {#fixes-8-6-2}

Esta versão corrige o seguinte problema:

* Correção de um problema de desempenho que poderia ocorrer na instância mid-sourcing (NEO-72595).

## Versão 8.6.1 {#release-8-6-1}

_14 de fevereiro de 2024_

### Novos recursos {#new-8-6-1}

* A partir desta versão, você terá acesso à nova **Interface do Campaign Web**, disponível por meio do ambiente central do Adobe Experience Cloud. A Experience Cloud é a família integrada de aplicativos, produtos e serviços de marketing digital da Adobe. Com sua interface intuitiva, você pode acessar rapidamente os aplicativos em nuvem, recursos do produto e serviços. Saiba como se conectar à Adobe Experience Cloud e acessar a interface do Adobe Campaign Web [nesta página](campaign-ui.md#ac-web-ui).


* O Adobe Campaign v8 agora se integra ao **Adobe Experience Manager as a Cloud Service**, com criação disponível exclusivamente por meio da interface do Adobe Campaign Web. [Saiba mais](../connect/ac-aem.md)

* Agora é possível usar a **Biblioteca do Adobe Experience Manager Assets** junto com o Experience Cloud Assets, mesmo se o pacote de Integração com o Adobe Experience Cloud estiver instalado em sua instância do Adobe Campaign. [Saiba mais](../connect/ac-aem.md#assets-library)

### Melhorias gerais {#improvements-8-6-1}

* O Campaign v8.6 oferece taxa de transferência aprimorada para **indicadores de rastreamento de entregas de email**. Com nossos processos otimizados, o rastreamento da ingestão e do tempo de computação é reduzido, e você pode verificar os indicadores-chave da entrega muito mais rápido.


### Atualizações sobre capacidade de entrega {#deliverability-8-6-1}

* Até fevereiro de 2024, qualquer empresa que envie mais de 5.000 mensagens de email através do Google ou do Yahoo! terá que começar a usar uma tecnologia de autenticação conhecida como DMARC (Domain-based Message Authentication Reporting and Conformance). Certifique-se de que o registro DMARC esteja configurado para todos os subdomínios usados com o Adobe Campaign. [Saiba mais](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=pt-BR){target="_blank"}

* A partir de 1º de junho de 2024, o Google e o Yahoo! exigirão que os remetentes cumpram o Cancelamento de inscrição na lista com um clique. O Adobe Campaign agora é compatível com essa opção. [Saiba mais](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=pt-BR#one-click-list-unsubscribe){target="_blank"}


### Correções {#fixes-8-6-1}

Os seguintes problemas foram corrigidos nessa versão:
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789