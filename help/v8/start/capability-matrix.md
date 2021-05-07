---
solution: Campaign
product: Adobe Campaign
title: Campaign Classic v7 - Matriz de recursos do Campaign v8
description: Entender as diferenças entre o Campaign Classic v7 e o Campaign v8
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
translation-type: tm+mt
source-git-commit: e1308398e5a33f2ad9659ad632aeb05af9916e69
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 3%

---

# Campaign Classic v7 - recursos do Campaign v8{#gs-matrix}


Como um usuário existente do Campaign Classic v7, você não deve esperar grandes interrupções na maneira como você normalmente interage com o Adobe Campaign. A maioria das alterações na v8 não está visível, exceto para pequenas alterações que surgiram na interface do usuário e nas etapas de configuração.

Alterações principais:

* Crie segmentos 200 vezes mais rápidos

* Aumentar a velocidade de entrega

* Relatório em tempo real

Como usuário do Campaign Classic, observe que a maioria dos recursos do Campaign Classic v7 está disponível com o Campaign v8, exceto um pequeno conjunto deles, listado em [this section](#gs-removed). Outros serão lançados em versões futuras. [Saiba mais](#gs-unavailable-features)


## Alterações na configuração do produto

### Campanha e [!DNL Snowflake] {#ac-gs-snowflake}

O armazenamento na nuvem é executado em [!DNL Snowflake]: uma nova conta externa garante a conectividade com o banco de dados da nuvem. [Saiba mais](#ac-gs-snowflake).

Esta é uma mudança fundamental na arquitetura de software. Agora os dados são remotos e o Campaign federa todos os dados, incluindo Perfis. Os processos de campanha agora escalam de ponta a ponta, do direcionamento à execução de mensagem: a assimilação de dados, a segmentação, o direcionamento, as consultas, os deliveries normalmente serão executados em minutos.

Esta nova versão resolve todo o desafio do dimensionamento, mantendo o mesmo nível de flexibilidade e extensibilidade. O número de perfis é quase ilimitado e a retenção de dados pode ser estendida.

Uma nova conta externa **incorporada** é dedicada ao FDA completo. Este é o coração da conectividade com o banco de dados da nuvem. Recomendamos partir como está.

Qualquer esquema/tabela interna que precise ser movida ou replicada no banco de dados do Cloud vem com uma extensão de schema incorporada no namespace **xxl**.

Essas extensões contêm qualquer modificação necessária para mover esquemas internos do banco de dados local do Campaign para o banco de dados do [!DNL Snowflake] Cloud e adaptar sua estrutura de acordo: novo UUID, links atualizados, etc.

>[!CAUTION]
>
> Os dados do cliente não são armazenados no banco de dados local do Campaign. Como consequência, qualquer tabela personalizada precisa ser criada no banco de dados do Cloud.


### Replicação de dados

Um workflow técnico específico trata da replicação de tabelas que precisam estar presentes em ambos os lados (banco de dados local do Campaign e banco de dados do Cloud). Esse workflow é acionado a cada hora e depende de uma nova biblioteca JavaScript integrada.

>[!NOTE]
>
> Várias políticas de replicação foram criadas, com base no tamanho da tabela (XS, XL etc.).
> Algumas tabelas são replicadas em tempo real, outras são replicadas de hora em hora. Algumas tabelas terão atualizações incrementais; outras terão uma atualização completa.


[Saiba mais sobre replicação de dados](../config/replication.md)

### Gerenciamento de ID

Os objetos do Campaign v8 agora usam um **ID universal exclusiva (UUID)**, que permite que valores exclusivos ilimitados identifiquem dados

Não que essa ID seja baseada em sequência e não sequencial.

### Manutenção simplificada

Usuários do Campaign não precisam ser especialistas no banco de dados: não há mais necessidade de operações complexas de manutenção de banco de dados ou indexação de tabela complexa.

## Recursos temporários indisponíveis{#gs-unavailable-features}

Observe que alguns recursos ainda não estão disponíveis nessa primeira versão, como:

* Gerenciamento de recursos de marketing
* Marketing distribuído
* Gerenciamento de ofertas de entrada (módulo de interação)
* Otimização de campanha
* Gestor de Resposta
* Modelos de implantação híbridos/no local

## Recursos removidos{#gs-removed}

Para alinhar-se à nova arquitetura e ao novo modelo de implantação do Campaign v8, alguns recursos históricos do Campaign Classic v7 não estão mais disponíveis no Campaign v8.

* Cupons
* Acompanhamento da Web
* Pesquisas
* Marketing social
* ACS Connector (primeira oferta)

