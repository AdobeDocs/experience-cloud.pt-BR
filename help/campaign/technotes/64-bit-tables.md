---
title: Interface do usuário da Web do Adobe Campaign
description: Tabelas de 64 bits
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
TQID: https://experienceleague.adobe.com/D0f4gYkyUcNVpGxpvj3JrBGRyIAgSq1mF7R4ld5COmk
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: ad84694f2f6f45e4ee30fc51379106835ac302be
workflow-type: tm+mt
source-wordcount: 175
ht-degree: 17%

---

# Esquemas de 64 bits {#sixty-four-bit-tables}

Para facilitar a transição do Campaign Standard para o Campaign v8, várias tabelas foram alteradas de 32 para 64 bits. Na verdade, o Campaign Standard oferece suporte a PK de 64 bits em vários esquemas prontos para uso, enquanto o Campaign v8 oferece suporte a PK de 32 bits na maioria dos esquemas.

## Limitações

* Essa alteração técnica se aplica somente aos clientes que estão migrando do Campaign Standard.
* O esquema e a extensão de broadlog não têm suporte em 64 bits. Ele permanecerá em 32 bits.
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
