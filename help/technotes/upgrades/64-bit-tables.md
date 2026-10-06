---
title: Esquemas de 64 bits
description: Saiba mais sobre os esquemas de 64 bits no Adobe Campaign v8 para clientes migrados do Campaign Standard
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: ab81f6c3-9317-564f-af92-6670a8784294
    internal-label: Technote
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
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
