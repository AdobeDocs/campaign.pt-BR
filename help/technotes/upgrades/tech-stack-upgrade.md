---
product: campaign
title: Nota técnica - Atualizações de sistema da Adobe Campaign
description: Atualização do sistema Adobe Campaign
hide: true
hidefromtoc: true
exl-id: cc64cce1-2473-4136-aadc-8b13e89ef7f9
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# Atualizações de ambiente do Adobe Campaign 2023 {#ac-system-upgrade}

A infraestrutura do Campaign depende de sistemas de terceiros que devem ser atualizados regularmente com as versões e correções mais recentes. Essas atualizações são obrigatórias para garantir a continuidade do serviço e proteger os ambientes do Campaign contra riscos de segurança. Além disso, uma atualização do Campaign é necessária para garantir a compatibilidade com alterações no sistema de terceiros.

Como um **cliente do Managed Cloud Services**, a Adobe informa você sobre essas atualizações quando elas são necessárias. Seus ambientes precisarão ser atualizados de acordo com as recomendações para garantir a conformidade.

Por motivos de segurança, a Adobe deve [instalar a compilação mais recente do Campaign](#ac-upgrade) e atualizar seu [sistema operacional](#os-upgrade) e/ou seu [Sistema de Gerenciamento de Banco de Dados Relativo (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>Em caso de dúvidas sobre essas alterações, entre em contato com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>

## Atualização de build do Campaign {#ac-upgrade}

**Você será afetado?**

Se você for afetado pela [atualização do sistema operacional](#os-upgrade) e/ou pela [atualização do sistema de banco de dados](#pg-upgrade) detalhada abaixo, a Adobe deverá atualizar seus ambientes do Campaign para a [versão 8.4.3 mais recente](../../v8/start/release-notes.md), que é compatível com esses sistemas.

**Como atualizar?**

Como cliente do Managed Cloud Services, a Adobe entrará em contato com você e atualizará sua versão do Campaign.

## Atualização do sistema operacional {#os-upgrade}

**Você será afetado?**

Se você estiver executando o Campaign em um sistema operacional Debian, para se beneficiar das atualizações de segurança mais recentes do Debian, a Adobe precisará mover sua infraestrutura do Campaign para **Debian 11**. Observe que o suporte de segurança para Debian 9 estará disponível até 30 de junho de 2023.

**Como atualizar?**

Como cliente do Managed Cloud Services, a Adobe entrará em contato com você e atualizará seu ambiente.

## Atualização do sistema de banco de dados {#pg-upgrade}

**Você será afetado?**

Se o sistema de banco de dados do Campaign for PostgreSQL, para se beneficiar das inovações e atualizações de segurança mais recentes do PostgreSQL, o Adobe precisará atualizar para o **PostgreSQL 14**. Observe que o PostgreSQL 11 chegará ao fim da vida útil em 9 de novembro de 2023.

**Como atualizar?**

Como cliente do Managed Cloud Services, a Adobe entrará em contato e atualizará seu sistema de banco de dados do PostgreSQL 11 para o PostgreSQL 14.
