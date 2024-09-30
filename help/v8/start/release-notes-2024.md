---
title: Notas de versão do Campaign v8 (console) 2023
description: Lista de recursos e melhorias disponíveis com as versões do Campaign v8 de 2023
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: fb7abba9009591a2757c07f584c0a7c59c6eb01a
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 91%

---

# Notas de versão de 2024 {#2024-rn}

Esta página lista novos recursos, melhorias e correções que vêm com as **Versões do Campaign v8 de 2024**.



## Versão 8.5.3 {#release-8-5-3}

_28 de maio de 2024_

### Migração para a credencial OAuth de servidor para servidor {#change-8-5-3}

A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. [Saiba mais](#change-8-7-1)

### Correções {#fixes-8-5-3}

Os seguintes problemas foram corrigidos nesta versão:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542


## Atualizações de maio {#may-updates}

A seguinte alteração foi lançada em maio e agora está disponível para usuários do Campaign v8:

* **Novo complemento de segurança aprimorado**: para proteger sua conexão de rede e fornecer mais segurança para seus recursos, o Adobe Campaign oferece um novo complemento de segurança aprimorado, que inclui dois recursos: integração de CMK segura e túneis seguros de VPN. [Leia mais](../config/enhanced-security.md)


## Versão 8.7.1 {#release-8-7-1}

_2 de maio de 2024_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa transição na [documentação da interface da web do Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Novos recursos {#new-8-7-1}

* **Modelos avançados de notificação por push**: agora você pode enviar notificações por push avançadas via Android. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. [Leia mais](../send/rich-push-ios.md).

* **Identidade visual**: como um usuário migrado do Campaign Standard, os administradores técnicos podem agora definir uma ou várias marcas para centralizar os parâmetros que afetam a identidade de uma marca. Isso inclui o logotipo da marca, o domínio do URL de acesso da página de destino ou as configurações de rastreamento de mensagens. Você pode criar essas marcas e vinculá-las a mensagens ou páginas de destino. Essa configuração é gerenciada nos modelos. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=pt-BR){target="_blank"}

* **APIs REST**: como um usuário migrado do Campaign Standard, você pode usar as APIs REST para criar integrações com o Adobe Campaign e criar seu próprio ecossistema, conectando o Adobe Campaign ao painel de tecnologias que você usa. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=pt-BR){target="_blank"}

* **Relatórios dinâmicos**: como um usuário migrado do Campaign Standard, você pode acessar os relatórios dinâmicos, que fornecem relatórios totalmente personalizáveis e em tempo real para medir o impacto de suas atividades de marketing. Eles adicionam acesso aos dados do perfil, permitindo análises demográficas por dimensões do perfil, como gênero, cidade e idade, além de dados funcionais de campanha de email, como aberturas e cliques. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=pt-BR){target="_blank"}

### Atualizações de compatibilidade {#comp-8-7-1}

* Os databricks agora são compatíveis como um banco de dados externo com o Federated Data Access (FDA) do Adobe Campaign. Saiba mais [nesta página](compatibility-matrix.md#FederatedDataAccessFDA).

### Migração para a credencial OAuth de servidor para servidor {#change-8-7-1}

A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. A Adobe executará a migração de JWT para OAuth em suas integrações de saída, como a integração do Campaign-Analytics ou a integração dos Acionadores da Experience Cloud.

Se você implementou integrações de entrada com o Campaign, é necessário migrar a conta técnica conforme detalhado [nesta documentação](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. As credenciais da conta de serviço (JWT) já existentes continuarão a funcionar até **27 de janeiro de 2025**. 

### Melhorias gerais {#improvements-8-7-1}

* Vários esquemas foram alterados de 32 para 64 bits. Isso se aplica somente aos clientes que estão migrando do Campaign Standard. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=pt-BR){target="_blank"}

* Nas tabelas do Campaign, os seguintes atributos agora são preenchidos por padrão pela data/hora do servidor: `lastModified` e `created`. O valor do atributo `createdBy-id` agora é preenchido com a ID de logon atual por padrão. Os valores fornecidos pelos usuários em chamadas da API são ignorados. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Para aumentar a segurança de todas as comunicações entre aplicativos, o mTLS agora é compatível com chamadas de API externas.

### Correções {#fixes-8-7-1}

Os seguintes problemas foram corrigidos nesta versão:

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

Os seguintes problemas foram corrigidos nesta versão:

NEO67892, NEO67235, NEO66797, NEO66462, NEO65091, NEO65036, NEO64984, NEO64680, NEO63973, NEO63879, NEO638795, NEO63657, NEO63539, NEO63387, NEO63294, NEO63174, NEO62964, NEO62750, NEO62686, NEO62455, NEO62406, NEO611 580, NEO61199, NEO60786, NEO59544, NEO59198, NEO59059, NEO58637, NEO55197, NEO52542, NEO50488, NEO47789
