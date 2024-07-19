---
title: Alterar a tabela de destinatários padrão
description: Saiba como usar uma tabela de recipient personalizada
feature: Custom Resources, Profiles, Configuration
role: User, Developer
level: Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 3%

---

# Usar tabela de destinatário personalizada{#gs-ac-custom-recipient}

O Adobe Campaign vem com uma tabela de perfil interna: **nmsRecipient**. Essa tabela tem vários campos e tabelas predefinidos que podem ser facilmente estendidos. Saiba mais sobre esta tabela em [esta página](datamodel.md#ootb-profiles).

A extensão de tabela integrada oferece flexibilidade, mas não permite remover alguns campos ou links não usados. Como consequência, o uso de uma tabela de recipients personalizada pode ser uma boa opção quando o modelo de dados difere drasticamente da estrutura integrada da tabela de recipients do Campaign ou se você tiver um grande número de perfis.  No entanto, esse método requer determinadas precauções ao implementá-lo.

Saiba como configurar sua instância para usar uma tabela de destinatários personalizada na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target="_blank"}.