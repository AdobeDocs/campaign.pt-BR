---
title: Alterar a tabela de destinatários padrão
description: Saiba como usar uma tabela de recipient personalizada
feature: Custom Resources, Profiles, Configuration
role: User, Developer
level: Beginner, Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Usar tabela de recipient personalizada{#gs-ac-custom-recipient}

O Adobe Campaign vem com uma tabela de perfil incorporada: **nmsRecipient**. Essa tabela tem vários campos e tabelas predefinidos que podem ser facilmente estendidos. Saiba mais sobre esta tabela em [esta página](datamodel.md#ootb-profiles).

A extensão de tabela integrada oferece flexibilidade, mas não permite remover alguns campos ou links não usados. Como consequência, o uso de uma tabela de recipients personalizada pode ser uma boa opção quando o modelo de dados difere drasticamente da estrutura integrada da tabela de recipients do Campaign ou se você tiver um grande número de perfis.  No entanto, esse método requer determinadas precauções ao implementá-lo.

![](../assets/do-not-localize/book.png) Saiba como configurar sua instância para usar uma tabela de recipient personalizada no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target="_blank"}.