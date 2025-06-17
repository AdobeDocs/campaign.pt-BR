---
title: Notas de versão do Campaign v8 (console) de 2025
description: Lista de recursos e melhorias disponíveis com as versões do Campaign v8 de 2025
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 66e4b59915eae595b28076622f7bcfb5b5a0ffa4
workflow-type: ht
source-wordcount: '428'
ht-degree: 100%

---

# Notas de versão de 2025 {#2025-rn}

Esta página lista novos recursos, melhorias e correções incluídos nas **versões do Campaign v8 de 2025**.  As últimas versões estão listadas [nesta página](release-notes.md).

>[!BEGINSHADEBOX]

**Nesta página**

* Campaign v8.7: [Versão 8.7.2](#release-8-7-2) | [Versão 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]


## Versão 8.7.3 {#release-8-7-3}

_14 de fevereiro de 2025_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa migração na [documentação da interface do Campaign Web v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Novos recursos {#features-8-7-3}

* **Relatórios dinâmicos para mensagens transacionais**: agora você pode monitorar as mensagens transacionais na interface de relatórios dinâmicos. Esses relatórios oferecem a profissionais de marketing a capacidade de visualizar todas as métricas e dimensões de relatórios de mensagens transacionais, além de detalhar entregas enviadas por meio de um modelo em tempo real. [Leia mais](https://experienceleague.adobe.com/pt-br/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **APIs REST de mensagens transacionais**: as APIs transacionais baseadas em eventos agora estão disponíveis para emails. [Leia mais](https://experienceleague.adobe.com/pt-br/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### Correções {#fixes-8-7-3}

Os seguintes problemas foram corrigidos nesta versão:

NEO-79373, NEO-81908, NEO-83081

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

* **Identidade visual**: agora, as opções de identidade visual estão disponíveis para todos os canais, inclusive SMS e correspondência direta. [Leia mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=pt-BR){target="_blank"}

### Correções {#fixes-8-7-2}

Os seguintes problemas foram corrigidos nesta versão:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.
