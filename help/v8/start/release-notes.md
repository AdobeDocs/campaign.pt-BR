---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e119c415ce363a635f9f0318e3fd70f90f4bde06
workflow-type: ht
source-wordcount: '801'
ht-degree: 100%

---

# Versões mais recentes {#latest-release}

O Adobe Campaign é atualizado regularmente. Essa frequência regular de atualizações tem como objetivo disponibilizar a você o que há de melhor e mais recente, mantendo seu ambiente seguro e melhorando sua experiência com nosso produto. A Adobe recomenda que todos os clientes atualizem para a versão mais recente. Esta página lista novos recursos, melhorias e correções que acompanham as versões mais recentes do Campaign v8 (console). Saiba mais sobre as versões e atualizações do Campaign [nesta página](upgrades.md).

Como usuário do Managed Cloud Services, sua instância é atualizada pela Adobe a cada nova versão. A Adobe entrará em contato com você e atualizará seus ambientes. O console do cliente do Campaign **precisa ser atualizado para a mesma versão** dos servidores do Campaign. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

Além disso, como cliente, verifique se você está usando a versão compatível mais recente dos sistemas listados na [Matriz de compatibilidade](compatibility-matrix.md).

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
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa transição na [documentação da interface da web do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Novos recursos {#new-8-7-1}

* **Modelos avançados de notificação por push**: agora você pode enviar notificações por push avançadas via Android. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. [Leia mais](../send/rich-push.md).

* **Identidade visual**: como um usuário migrado do Campaign Standard, os administradores técnicos podem agora definir uma ou várias marcas para centralizar os parâmetros que afetam a identidade de uma marca. Isso inclui o logotipo da marca, o domínio do URL de acesso da página de destino ou as configurações de rastreamento de mensagens. Você pode criar essas marcas e vinculá-las a mensagens ou páginas de destino. Essa configuração é gerenciada em modelos. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=pt-BR){target="_blank"}

* **APIs REST**: como um usuário migrado do Campaign Standard, você pode usar as APIs REST para criar integrações com o Adobe Campaign e criar seu próprio ecossistema, conectando o Adobe Campaign ao painel de tecnologias que você usa. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=pt-BR){target="_blank"}

* **Relatórios dinâmicos**: como um usuário migrado do Campaign Standard, você pode acessar os relatórios dinâmicos, que fornecem relatórios totalmente personalizáveis e em tempo real para medir o impacto de suas atividades de marketing. Eles adicionam acesso aos dados do perfil, permitindo análises demográficas por dimensões do perfil, como gênero, cidade e idade, além de dados funcionais de campanha de email, como aberturas e cliques. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=pt-BR){target="_blank"}




### Atualizações de compatibilidade {#comp-8-7-1}

* Os databricks agora são compatíveis como um banco de dados externo com o Federated Data Access (FDA) do Adobe Campaign. Saiba mais [nesta página](compatibility-matrix.md#FederatedDataAccessFDA).

### Migração para a credencial OAuth de servidor para servidor {#change-8-7-1}

A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. A Adobe executará a migração de JWT para OAuth em suas integrações de saída, como a integração do Campaign-Analytics ou a integração dos Acionadores da Experience Cloud.

Se você implementou integrações de entrada com o Campaign, é necessário migrar a conta técnica conforme detalhado [nesta documentação](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. As credenciais da conta de serviço (JWT) existentes continuarão a funcionar até **27 de janeiro de 2025**. Além disso, o Developer Console continuará a oferecer suporte à criação de novas credenciais de conta de serviço (JWT) até **3 de junho de 2024**. Novas credenciais de conta de serviço (JWT) não poderão ser criadas ou adicionadas a projetos após essa data.


### Melhorias gerais {#improvements-8-7-1}

* Vários esquemas foram alterados de 32 para 64 bits. Isso se aplica somente aos clientes que estão migrando do Campaign Standard. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=pt-BR){target="_blank"}

* Nas tabelas do Campaign, os seguintes atributos agora são preenchidos por padrão pela data/hora do servidor: `lastModified` e `created`. O valor do atributo `createdBy-id` agora é preenchido com a ID de logon atual por padrão. Os valores fornecidos pelos usuários em chamadas da API são ignorados. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

### Correções {#fixes-8-7-1}

Os seguintes problemas foram corrigidos nessa versão:
NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054
