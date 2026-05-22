---
title: Esquemas de 64 bits
description: Saiba mais sobre os esquemas de 64 bits no Adobe Campaign v8 para clientes migrados do Campaign Standard
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
source-git-commit: 25ce962e7c8b6a62fc2c1edb08a78afa839d264e
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 18%

---

# Esquemas de 64 bits {#sixty-four-bit-tables}

Para facilitar a transição do Campaign Standard para o Campaign v8, várias tabelas foram alteradas de 32 para 64 bits. Na verdade, o Campaign Standard oferece suporte a PK de 64 bits em vários esquemas prontos para uso, enquanto o Campaign v8 oferece suporte a PK de 32 bits na maioria dos esquemas.

## Limitações

* Essa alteração técnica se aplica somente aos clientes que estão migrando do Campaign Standard.
* O esquema e a extensão de catálogo não têm suporte em 64 bits. Ele permanecerá em 32 bits.
* Os logs relacionados aos deliveries enviados para usuários técnicos não estarão disponíveis no Campaign v8.
* Somente o PostgreSQL é compatível.

## Esquemas modificados

Esta é a lista de esquemas alterados para 64 bits e seus atributos modificados.

| Nome do esquema | Nome do atributo |
|--- |--- |
| nms:broadLogRcp | id |
| nms:trackingLogRcp | id |
| nms:excludeLogRcp | id |
| nms:broadLogVisitor | id |
| nms:trackingLogVisitor | id |
| nms:propositionRcp | interactionId |
| nms:propositionVisitor | interactionId |
| nms:webTrackingLog | id |
| nms:tmpBroadcast | message-id |
| nms:tmpMarketingPressure | message-id |
| nms:tmpBroadcastExclusion | message-id |
| nms:tmpBroadcastPaper | message-id |
| nms:broadLogAppSubRcp | id |
| nms:trackingLogAppSubRcp | id |
| nms:excludeLogAppSubRcp | id |
| nms:webEvent | broadLogSrc-id, broadLogRemkt-id |
| nms:broadLogMid | mktBroadLogId |
| nms:mirrorPageSearch | remoteMessageId |
