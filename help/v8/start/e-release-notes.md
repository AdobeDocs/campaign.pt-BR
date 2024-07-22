---
title: Notas de versão anteriores do Campaign v8
description: Lançamento antecipado do Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 65efda7469c5ad35e8d03703951c3d1480b015f4
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 49%

---

# Notas de versão anteriores {#e-new-release}

Esta página descreve as melhorias e correções incluídas no próximo lançamento do Campaign v8. **As notas de versão antecipadas abaixo estão sujeitas a alterações sem aviso prévio até a data de disponibilidade do lançamento**. Links, telas e a documentação atualizada são publicados nas [notas de versão](release-notes.md) na data do lançamento.

## Versão 8.7.2 {#release-8-7-2}

_quarta-feira, 30 de julho de 2024_


>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa transição na [documentação da interface da web do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Novos recursos {#new-8-7-2}

* **Novo conector de envio de SMS** - O conector de envio de SMS foi modernizado e aprimorado para habilitar conexões SMPP no modo transceptor, habilitar conexões SMPP persistentes e garantir melhor compatibilidade para ambientes em transição do Adobe Campaign Standard. Uma nova conta externa de SMS agora está disponível para todas as novas implementações de SMS. A implementação atual ainda é compatível, no entanto, recomenda-se mudar para esse novo conector moderno e estendido.

* **Notificação por push avançada (GA)** - Agora você pode enviar notificações por push avançadas. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. Com esta versão, um conjunto de modelos para notificações por push avançadas agora está disponível para seus aplicativos iOS e Android. [Leia mais](../send/rich-push.md).

* **Marcas** - As opções de marcas agora estão disponíveis para todos os canais, incluindo SMS e Correspondência direta. [Saiba mais](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=pt-BR){target="_blank"}


### Correções {#fixes-8-7-2}

Os seguintes problemas foram corrigidos nesta versão:

NEO76592, NEO75400, NEO77406, NEO77674, NEO77899, NEO73989, NEO76064, NEO76039, NEO76040, NEO76845, NEO76664, NEO76682, NEO7663, NEO73602, NEO72915, NEO78134, NEO77000, NEO77002, NEO76955, NEO76864, NEO76926, NEO766 495, NEO77168, NEO41058, NEO75581, NEO74647, NEO74585, NEO74586, NEO74831, NEO77319, NEO78607.

## Versão 8.6.3 {#release-8-6-3}

_quarta-feira, 30 de julho de 2024_

### Novos recursos {#new-8-6-3}

* **Notificação por push avançada** - Agora você pode enviar notificações por push avançadas. A notificação por push avançada é uma forma aprimorada de notificação em dispositivos móveis que vai além das mensagens de texto simples, incorporando elementos multimídia, como imagens, botões interativos ou outros conteúdos de mídia avançada. Com esta versão, um conjunto de modelos para notificações por push avançadas agora está disponível para seus aplicativos iOS e Android. [Leia mais](../send/rich-push.md).

* A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. [Saiba mais](release-notes.md#change-8-7-1)

### Melhorias gerais {#improvements-8-6-3}

* Para aumentar a segurança em toda a comunicação entre aplicativos, o mTLS agora é compatível com chamadas de API externas.

### Correções {#fixes-8-6-3}

Os seguintes problemas foram corrigidos nesta versão:

NEO77014, NEO76958, NEO76097, NEO75898, NEO72504, NEO70263, NEO67620, NEO63197, NEO58596, NEO56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->