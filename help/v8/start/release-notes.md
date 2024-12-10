---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e0dbeb7402a46f76a26c28dd226bc069d52f2609
workflow-type: ht
source-wordcount: '422'
ht-degree: 100%

---

# Versões mais recentes {#latest-release}

Esta página lista novos recursos, melhorias e correções que acompanham as versões mais recentes do Campaign v8 (console). Saiba mais sobre lançamentos, versões e atualizações do Campaign [nesta página](upgrades.md).

## Versão 8.7.2 {#release-8-7-2}

_3 de setembro de 2024_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa transição na [documentação da interface da web do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Novos recursos {#new-8-7-2}

* **Novo conector de envio de SMS**: o conector de envio de SMS foi modernizado e aprimorado para permitir conexões SMPP no modo transceptor, permitir conexões SMPP persistentes e garantir uma melhor compatibilidade para ambientes em transição do Adobe Campaign Standard. Uma nova conta externa de SMS agora está disponível para todas as novas implementações de SMS. A implementação atual ainda é compatível, mas é recomendável mudar para esse novo conector moderno e estendido. [Leia mais](../send/sms/sms.md).

* **Notificação por push avançada (GA)**: agora, você pode enviar notificações por push avançadas. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. Com esta versão, um conjunto de modelos para notificações por push avançadas agora está disponível para aplicativos iOS e Android. [Leia mais](../send/rich-push-android.md).

* **Identidade visual**: agora, as opções de identidade visual estão disponíveis para todos os canais, inclusive SMS e correspondência direta. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=pt-BR){target="_blank"}


### Correções {#fixes-8-7-2}

Os seguintes problemas foram corrigidos nesta versão:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.


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
