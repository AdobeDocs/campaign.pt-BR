---
title: Notas de versão anteriores do Campaign v8
description: Lançamento antecipado do Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 695c481596271feef35c630c68d9bc52cbe1b6f8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notas de versão anteriores {#e-new-release}

Esta página descreve as melhorias e correções incluídas no próximo lançamento do Campaign v8. **As notas de versão antecipadas abaixo estão sujeitas a alterações sem aviso prévio até a data de disponibilidade do lançamento**. Links, telas e a documentação atualizada são publicados nas [notas de versão](release-notes.md) na data do lançamento.


## Versão 8.7.2 {#release-8-7-2}

_3 de setembro de 2024_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa transição na [documentação da interface da web do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Novos recursos {#new-8-7-2}

* **Novo conector de envio de SMS** - O conector de envio de SMS foi modernizado e aprimorado para habilitar conexões SMPP no modo transceptor, habilitar conexões SMPP persistentes e garantir melhor compatibilidade para ambientes em transição do Adobe Campaign Standard. Uma nova conta externa de SMS agora está disponível para todas as novas implementações de SMS. A implementação atual ainda é compatível, no entanto, recomenda-se mudar para esse novo conector moderno e estendido.

* **Notificação por push avançada (GA)** - Agora você pode enviar notificações por push avançadas. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. Com esta versão, um conjunto de modelos para notificações por push avançadas agora está disponível para aplicativos iOS e Android. [Leia mais](../send/rich-push-android.md).

* **Marcas** - As opções de marcas agora estão disponíveis para todos os canais, incluindo SMS e Correspondência direta. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=pt-BR){target="_blank"}


### Correções {#fixes-8-7-2}

Os seguintes problemas foram corrigidos nesta versão:

NEO48232, NEO56832, NEO72504, NEO74855, NEO75898, NEO76097, NEO76958, NEO77014, NEO77795, NEO78843, NEO7932 10.
