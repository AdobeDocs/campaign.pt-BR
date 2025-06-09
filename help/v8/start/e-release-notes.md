---
title: Notas de versão anteriores do Campaign v8
description: Lançamento antecipado do Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 9ce5acd97e077105316c81029e3ccbc6fa4389dc
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 86%

---

# Notas de versão anteriores {#e-new-release}

Esta página descreve as melhorias e correções incluídas no próximo lançamento do Campaign v8. **As notas de versão antecipadas abaixo estão sujeitas a alterações sem aviso prévio até a data de disponibilidade do lançamento**. Links, telas e a documentação atualizada são publicados nas [notas de versão](release-notes.md) na data do lançamento.


## Versão 8.7.2 {#release-8-7-2}

_3 de setembro de 2024_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como um usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa transição na [documentação da interface do usuário da Web do Campaign v8](https://experienceleague.adobe.com/docs/campaign-web/v8/start/acs-migration.html){target="_blank"}.

### Novos recursos {#new-8-7-2}

* **Novo conector de envio de SMS**: o conector de envio de SMS foi modernizado e aprimorado para permitir conexões SMPP no modo transceptor, permitir conexões SMPP persistentes e garantir uma melhor compatibilidade para ambientes em transição do Adobe Campaign Standard. Uma nova conta externa de SMS agora está disponível para todas as novas implementações de SMS. A implementação atual ainda é compatível, no entanto, recomenda-se mudar para esse novo conector moderno e estendido.

* **Notificação por push avançada (GA)**: agora, você pode enviar notificações por push avançadas. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. Com esta versão, um conjunto de modelos para notificações por push avançadas agora está disponível para aplicativos iOS e Android. [Leia mais](../send/rich-push-android.md).

* **Identidade visual**: agora, as opções de identidade visual estão disponíveis para todos os canais, inclusive SMS e correspondência direta. [Leia mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=pt-BR){target="_blank"}


### Correções {#fixes-8-7-2}

Os seguintes problemas foram corrigidos nesta versão:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.
