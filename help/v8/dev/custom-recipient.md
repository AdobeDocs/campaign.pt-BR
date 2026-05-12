---
title: Alterar a tabela de destinatários padrão
description: Saiba como usar uma tabela de recipient personalizada
feature: Custom Resources, Profiles, Configuration
role: User, Developer
level: Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
TQID: https://experienceleague.adobe.com/W67Z2xVEBDpju5xlL2WiE5ZTzvrFmhuByMvfPb4x6nM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 149
ht-degree: 3%

---

# Usar tabela de destinatário personalizada{#gs-ac-custom-recipient}

O Adobe Campaign vem com uma tabela de perfil interna: **nmsRecipient**. Essa tabela tem vários campos e tabelas predefinidos que podem ser facilmente estendidos. Saiba mais sobre esta tabela em [esta página](datamodel.md#ootb-profiles).

A extensão de tabela integrada oferece flexibilidade, mas não permite remover alguns campos ou links não usados. Como consequência, o uso de uma tabela de recipients personalizada pode ser uma boa opção quando o modelo de dados difere bastante da estrutura integrada da tabela de recipients do Campaign ou se você tiver um grande número de perfis.  No entanto, esse método requer determinadas precauções ao implementá-lo.

Saiba como configurar sua instância para usar uma tabela de destinatários personalizada na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target="_blank"}.