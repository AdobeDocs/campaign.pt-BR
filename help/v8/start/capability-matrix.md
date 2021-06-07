---
product: Adobe Campaign
title: Campaign Classic v7 - Matriz de recursos do Campaign v8
description: Entender as diferenças entre o Campaign Classic v7 e o Campaign v8
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 93b690d815f73d11de7de90b92ae188082a3e9e4
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 44%

---

# [!DNL Campaign Classic] v7 - recursos  [!DNL Campaign] v8{#gs-matrix}

Como um usuário [!DNL Campaign Classic] v7 existente, você não deve esperar grandes interrupções na maneira como geralmente interage com [!DNL Adobe Campaign]. A maioria das alterações na v8 não é visível, exceto pequenas alterações que surgiram na interface e nas etapas de configuração.

Alterações principais:

* Criar segmentos 200 vezes mais rápidos
* Aumentar a velocidade de entrega
* Relatórios em tempo real com Cubos

Como usuário [!DNL Campaign Classic], observe que a maioria dos recursos [!DNL Campaign Classic] v7 está disponível com [!DNL Campaign] v8, exceto um pequeno conjunto deles, listado em [esta seção](#gs-removed). Outros serão lançados em versões futuras. [Saiba mais nesta seção](#gs-unavailable-features)

[!DNL :bulb:] Saiba mais sobre a arquitetura  [!DNL Campaign] v8  [nesta página](../dev/architecture.md).

## Alterações na configuração do produto

### [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] O v8 funciona com dois bancos de dados: um banco de dados local para a interface do usuário, mensagens em tempo real e consultas unitárias e gravação por meio de APIs, e um banco de dados do Cloud para execução de campanha, consultas em lote e execução de workflows.

É uma mudança fundamental na arquitetura de software. Agora os dados são remotos e o Campaign federa todos os dados, incluindo Perfis. [!DNL Campaign]Os processos do agora escalam de ponta a ponta, do direcionamento à execução da mensagem: a assimilação de dados, a segmentação, o direcionamento, as consultas e as entregas normalmente serão executados em minutos. Esta nova versão resolve todo o desafio do dimensionamento, mantendo o mesmo nível de flexibilidade e extensibilidade. O número de perfis é quase ilimitado e a retenção de dados pode ser estendida.

O armazenamento na nuvem é executado em **[!DNL Snowflake]**: uma nova **conta externa** integrada garante a conectividade com o banco de dados da nuvem. Ele é configurado pelo Adobe e não deve ser modificado. [Saiba mais](../config/external-accounts.md)

Qualquer esquema/tabela interna que precise ser movido ou replicado no banco de dados da nuvem vem com uma extensão de esquema incorporada no namespace **xxl.** Essas extensões contêm qualquer modificação necessária para mover esquemas internos do banco de dados local [!DNL Campaign] para o banco de dados do [!DNL Snowflake] Cloud e adaptar sua estrutura de acordo: novo UUID, links atualizados, etc.

>[!CAUTION]
>
> Os dados do cliente não são armazenados no banco de dados local [!DNL Campaign]. Como consequência, qualquer tabela personalizada precisa ser criada no banco de dados da nuvem.


APIs específicas estão disponíveis para gerenciar dados entre o banco de dados local e da nuvem. Saiba como essas novas APIs funcionam e como usá-las em [this page](../dev/new-apis.md).

### Replicação de dados

Um fluxo de trabalho técnico específico trata da replicação de tabelas que precisam estar presentes em ambos os lados (banco de dados local do Campaign e banco de dados da nuvem). Esse fluxo de trabalho é acionado a cada hora e depende de uma nova biblioteca JavaScript integrada.

>[!NOTE]
>
> Várias políticas de replicação foram criadas, com base no tamanho da tabela (XS, XL etc.).
> Algumas tabelas são replicadas em tempo real, outras são replicadas de hora em hora. Algumas tabelas terão atualizações incrementais; outras terão uma atualização completa.


[Saiba mais sobre replicação de dados](../config/replication.md)

### Gerenciamento de ID

Os objetos do Campaign v8 agora usam um **Identificador exclusivo universal (UUID)**, que permite que valores exclusivos ilimitados identifiquem dados.

Observe que essa ID é baseada em sequência e não sequencial. A chave primária não é um valor numérico no Campaign v8 e você precisa usar os atributos **autouuid** e **autopk** em seus esquemas.

No Campaign Classic v7 e em versões anteriores, a unicidade de uma chave em um schema (ou seja, tabela) é manipulada no nível do mecanismo de banco de dados. Em geral, os mecanismos do Banco de Dados Clássico como PostgreSQL, Oracle ou SQL Server incluem um mecanismo nativo para impedir a inserção de linhas duplicadas com base em uma coluna ou um conjunto de colunas por meio de chaves primárias e/ou índices exclusivos. A ID duplicada não existe nessas versões quando o índice adequado e as chaves primárias são definidos no nível do banco de dados.

O Adobe campaign v8 vem com o Snowflake como o banco de dados principal. Como aumenta drasticamente a escala de queries, a arquitetura distribuída do banco de dados do Snowflake não fornece esses mecanismos para gerenciar e impor a unicidade de uma chave dentro de uma tabela. Como consequência, com o Adobe Campaign v8, nada impede a assimilação de chaves duplicadas em uma tabela. Os usuários finais agora são responsáveis por garantir a consistência das chaves no banco de dados do Adobe Campaign. [Saiba mais](../dev/keys.md)

### Manutenção simplificada

Usuários do Campaign não precisam ser especialistas em banco de dados: não há mais necessidade de operações complexas de manutenção de banco de dados ou indexação de tabela complexa.

## Relatórios

Observe que os relatórios do Adobe Campaign são otimizados e oferecem recursos de melhor escala que o Campaign Classic v7. As limitações existentes em cubos não se aplicam.

## Recursos indisponíveis{#gs-unavailable-features}

Observe que alguns recursos não estão disponíveis nesta primeira versão, como:

* Gerenciamento de recursos de marketing
* Marketing distribuído
* Gerenciamento de ofertas de entrada (módulo de interação)
* Otimização de campanha
* Gestor de Resposta
* Modelos de implantação híbridos/no local
* Mensagens LINE
* Painel de controle do Campaign

>[!CAUTION]
>
>Por enquanto, o Campaign v8 é **only** disponível como um Cloud Service gerenciado e não pode ser implantado em um ambiente local ou híbrido.
>
>A migração de um ambiente Campaign Classic v7 existente ainda não está disponível.
>
>Se não tiver certeza do modelo de implantação ou se tiver dúvidas, entre em contato com a equipe de conta.

## Recursos removidos{#gs-removed}

Para alinhar-se à nova arquitetura e ao novo modelo de implantação do Campaign v8, alguns recursos históricos do Campaign Classic v7 não estão mais disponíveis no Campaign v8.

* Cupons
* Rastreamento web
* Pesquisas
* Marketing social
* Conector ACS (oferta principal)

