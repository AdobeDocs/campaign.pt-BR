---
title: Alterar a tabela de destinatários padrão
description: Saiba como usar uma tabela de recipient personalizada
feature: Custom Resources, Profiles
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Usar tabela de recipient personalizada{#gs-ac-custom-recipient}

O Adobe Campaign vem com uma tabela de perfil integrada: **nmsRecipient**. Essa tabela tem vários campos e tabelas predefinidos que podem ser facilmente estendidos. Saiba mais sobre esta tabela em [esta página](datamodel.md#ootb-profiles).

A extensão de tabela integrada oferece flexibilidade, mas não permite remover alguns campos ou links não utilizados. Como consequência, usar uma tabela de recipient personalizada pode ser uma boa opção quando o modelo de dados for diferente drasticamente da estrutura da tabela de recipients integrada do Campaign ou se você tiver um grande número de perfis.  No entanto, este método requer certas precauções ao implementá-lo.

![](../assets/do-not-localize/book.png) Saiba como configurar sua instância para usar uma tabela de recipient personalizada no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target=&quot;_blank&quot;}.