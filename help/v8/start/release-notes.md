---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 07e0bfdade0356eedb24641259aa754fdb1c6155
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 78%

---

# Versões mais recentes {#latest-release}

O Adobe Campaign é atualizado regularmente. Essa frequência regular de atualizações tem como objetivo disponibilizar a você o que há de melhor e mais recente, mantendo seu ambiente seguro e melhorando sua experiência com nosso produto. A Adobe recomenda que todos os clientes atualizem para a versão mais recente. Esta página lista novos recursos, melhorias e correções que acompanham as versões mais recentes do Campaign v8 (console). Saiba mais sobre as versões e atualizações do Campaign [nesta página](upgrades.md).

Como usuário do Managed Cloud Services, sua instância é atualizada pela Adobe a cada nova versão. A Adobe entrará em contato com você e atualizará seus ambientes. O console do cliente do Campaign **precisa ser atualizado para a mesma versão** dos servidores do Campaign. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

Além disso, como cliente, verifique se você está usando a versão compatível mais recente dos sistemas listados na [Matriz de compatibilidade](compatibility-matrix.md).


## Versão 8.7.2 {#release-8-7-2}

_3 de setembro de 2024_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa transição na [documentação da interface da web do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Novos recursos {#new-8-7-2}

* **Novo conector de envio de SMS** - O conector de envio de SMS foi modernizado e aprimorado para habilitar conexões SMPP no modo transceptor, habilitar conexões SMPP persistentes e garantir melhor compatibilidade para ambientes em transição do Adobe Campaign Standard. Uma nova conta externa de SMS agora está disponível para todas as novas implementações de SMS. A implementação atual ainda é compatível, no entanto, recomenda-se mudar para esse novo conector moderno e estendido. [Leia mais](../send/sms/sms.md).

* **Notificação por push avançada (GA)** - Agora você pode enviar notificações por push avançadas. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. Com esta versão, um conjunto de modelos para notificações por push avançadas agora está disponível para aplicativos iOS e Android. [Leia mais](../send/rich-push-android.md).

* **Marcas** - As opções de marcas agora estão disponíveis para todos os canais, incluindo SMS e Correspondência direta. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=pt-BR){target="_blank"}


### Correções {#fixes-8-7-2}

Os seguintes problemas foram corrigidos nesta versão:

NEO48232, NEO56832, NEO72504, NEO74855, NEO75898, NEO76097, NEO76958, NEO77014, NEO77795, NEO78843, NEO7932 10.


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
