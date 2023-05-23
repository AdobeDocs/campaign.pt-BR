---
product: campaign
title: Nota técnica - Atualizações de sistema da Adobe Campaign
description: Atualização do sistema Adobe Campaign
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: f1e963a880e8499dbbb16c44831a4ce1b537601f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---

# Atualizações de ambiente do Adobe Campaign 2023 {#ac-system-upgrade}

A infraestrutura do Campaign depende de sistemas de terceiros que devem ser atualizados regularmente com as versões e correções mais recentes. Essas atualizações são obrigatórias para garantir a continuidade do serviço e proteger os ambientes do Campaign contra riscos de segurança. Além disso, uma atualização do Campaign é necessária para garantir a compatibilidade com alterações no sistema de terceiros.

Como um **Cliente Cloud Services gerenciado**, o Adobe informa sobre essas atualizações quando elas são necessárias. Seus ambientes precisarão ser atualizados de acordo com as recomendações para garantir a conformidade.

Por motivos de segurança, o Adobe deve [instalar a build mais recente do Campaign](#ac-upgrade)e, em seguida, atualize seu [sistema operacional](#os-upgrade) e/ou seu [Sistema de gerenciamento de banco de dados relacional (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>Em caso de dúvidas sobre essas alterações, entre em contato com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

## Atualização de build do Campaign {#ac-upgrade}

**Você será afetado?**

Se você for afetado pelo [atualização do sistema operacional](#os-upgrade) e/ou a [atualização do sistema de banco de dados](#pg-upgrade) detalhado abaixo, o Adobe deve atualizar seus ambientes do Campaign para [a versão 8.4.3 mais recente](../../v8/start/release-notes.md), compatível com esses sistemas.

**Como atualizar?**

Como cliente do Managed Cloud Services, o Adobe entrará em contato com você e atualizará a versão do Campaign.

## Atualização do sistema operacional {#os-upgrade}

**Você será afetado?**

Se você estiver executando o Campaign em um sistema operacional Debian, para se beneficiar das atualizações de segurança mais recentes do Debian, o Adobe precisará mover sua infraestrutura do Campaign para **Debian 11**. Observe que o suporte de segurança para Debian 9 estará disponível até 30 de junho de 2023.

**Como atualizar?**

Como cliente do Managed Cloud Services, o Adobe entrará em contato com você e atualizará seu ambiente.

## Atualização do sistema de banco de dados {#pg-upgrade}

**Você será afetado?**

Se o sistema de banco de dados para o Campaign for PostgreSQL, para se beneficiar das inovações e atualizações de segurança mais recentes do PostgreSQL, o Adobe precisa atualizar para **PostgreSQL 14**. Observe que o PostgreSQL 11 chegará ao fim da vida útil em 9 de novembro de 2023.

**Como atualizar?**

Como cliente do Managed Cloud Services, o Adobe entrará em contato e atualizará seu sistema de banco de dados do PostgreSQL 11 para o PostgreSQL 14.
