---
title: Campaign Classic v7 - Matriz de recursos do Campaign v8
description: Entender as diferenças entre o Campaign Classic v7 e o Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 2d0b40e49afdfd71e8bb5c3f0b1d569a715420b2
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 100%

---

# [!DNL Campaign Classic] v7 - recursos do [!DNL Campaign] v8{#gs-matrix}

Como usuário do [!DNL Campaign Classic] v7, você não deve esperar nenhuma grande interrupção na maneira como costuma interagir com o [!DNL Adobe Campaign]. A maioria das alterações na v8 não é visível, exceto pequenas alterações que surgiram na interface e nas etapas de configuração.

Alterações principais:

* Criar segmentos 200 vezes mais rápidos
* Aumentar a velocidade de entrega
* Relatórios em tempo real com Cubos

Como usuário do [!DNL Campaign Classic], observe que a maioria dos recursos do [!DNL Campaign Classic] v7 está disponível com o [!DNL Campaign] v8, exceto um pequeno conjunto listado [nesta seção](#gs-removed). Outros serão lançados em versões futuras. [Saiba mais nesta seção](#gs-unavailable-features)

![](../assets/do-not-localize/glass.png) Saiba mais sobre a arquitetura do [!DNL Campaign] v8 [nesta página](../dev/architecture.md).

## Alterações na configuração do produto

### [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

O [!DNL Adobe Campaign] v8 funciona com dois bancos de dados: um banco de dados local para a interface do usuário de mensagens em tempo real e consultas unitárias e gravação por meio de APIs, e um banco de dados em nuvem para execução de campanha, consultas em lote e execução de fluxo de trabalho.

É uma mudança fundamental na arquitetura de software. Agora os dados são remotos e o Campaign federa todos os dados, incluindo Perfis. Os processos do [!DNL Campaign] agora são escalonados de ponta a ponta, desde o direcionamento até a execução da mensagem: assimilação de dados, segmentação, direcionamento, consultas e entregas agora normalmente são executados em minutos. Esta nova versão resolve todo o desafio do dimensionamento, mantendo o mesmo nível de flexibilidade e extensibilidade. O número de perfis é quase ilimitado e a retenção de dados pode ser estendida.

O armazenamento na nuvem é feito no **[!DNL Snowflake]**: uma nova **conta externa** incorporada garante a conectividade com o banco de dados na nuvem. Ele é configurado pela Adobe e não deve ser modificado. [Saiba mais](../config/external-accounts.md)

Qualquer esquema/tabela interna que precise ser movido ou replicado no banco de dados na nuvem vem com uma extensão de esquema incorporada no namespace **xxl**. Essas extensões contêm as modificações necessárias para mover esquemas integrados do banco local do [!DNL Campaign] para o banco de dados na nuvem do [!DNL Snowflake] e adaptar sua estrutura em conformidade: novo UUID, links atualizados, etc.

>[!CAUTION]
>
> Os dados do cliente não são armazenados no banco de dados local do [!DNL Campaign]. Como consequência, qualquer tabela personalizada precisa ser criada no banco de dados na nuvem.

APIs específicas estão disponíveis para gerenciar dados entre o banco de dados local e na nuvem. Saiba como essas novas APIs funcionam e como usá-las [nesta página](../dev/new-apis.md).

### Replicação de dados

Um fluxo de trabalho técnico específico trata da replicação de tabelas que precisam estar presentes em ambos os lados (banco de dados local do Campaign e banco de dados da nuvem). Esse fluxo de trabalho é acionado a cada hora e depende de uma nova biblioteca JavaScript integrada.

>[!NOTE]
>
> Várias políticas de replicação foram criadas, com base no tamanho da tabela (XS, XL etc.).
> Algumas tabelas são replicadas em tempo real, outras são replicadas de hora em hora. Algumas tabelas terão atualizações incrementais; outras terão uma atualização completa.

[Saiba mais sobre replicação de dados](../config/replication.md)

### Gerenciamento de ID

Os objetos do Campaign v8 agora usam um **Identificador exclusivo universal (UUID)**, que permite que valores exclusivos ilimitados identifiquem dados.

Observe que essa ID é baseada em uma sequência e não é sequencial. A chave primária não é um valor numérico no Campaign v8 e você precisa usar os atributos **autouuid** e **autopk** em seus esquemas.

No Campaign Classic v7 e em versões anteriores, a unicidade de uma chave em um esquema (ou seja, tabela) é manipulada no nível do mecanismo de banco de dados. Em geral, os mecanismos do banco de dados do Classic como PostgreSQL, Oracle ou SQL Server incluem um mecanismo nativo para impedir a inserção de linhas duplicadas com base em uma coluna ou um conjunto de colunas por meio de chaves principais e/ou índices únicos. A ID duplicada não existe nessas versões quando o índice adequado e as chaves principais são definidos no nível do banco de dados.

O Adobe Campaign v8 vem com o Snowflake como o banco de dados principal. Como aumenta drasticamente a escala de consultas, a arquitetura distribuída do banco de dados do Snowflake não fornece esses mecanismos para gerenciar e impor a unicidade de uma chave dentro de uma tabela. Como consequência, com o Adobe Campaign v8, nada impede a assimilação de chaves duplicadas em uma tabela. Os usuários finais agora são responsáveis por garantir a consistência das chaves no banco de dados do Adobe Campaign. [Saiba mais](../dev/keys.md)

### Manutenção simplificada

Usuários do Campaign não precisam ser especialistas em banco de dados: não há mais necessidade de operações complexas de manutenção de banco de dados ou indexação de tabela complexa.

## Conexão com o Campaign

Os usuários do Campaign se conectam por meio da Adobe ID. A mesma Adobe ID é usada para manter todos os seus planos e produtos da Adobe associados a uma única conta.

![](../assets/do-not-localize/glass.png)Saiba como se conectar ao [!DNL Campaign] [nesta página](connect.md).

## Relatórios

Observe que os relatórios do Adobe Campaign são otimizados e oferecem recursos de melhor escala que o Campaign Classic v7. As limitações existentes em cubos não se aplicam.

## Fluxo de trabalho {#workflow}

O Campaign v8 oferece uma atividade adicional de fluxo de trabalho para direcionamento: **[!UICONTROL Change data source]**.

A atividade **[!UICONTROL Change data source]** permite alterar a fonte de dados de um fluxo de trabalho **[!UICONTROL Working table]** para gerenciar dados em diferentes fontes de dados, como FDA, FFDA e banco de dados local.

![](../assets/do-not-localize/glass.png) Saiba mais sobre a atividade **[!UICONTROL Change data source]** [nesta página](../config/workflows.md#change-data-source-activity).

## Recursos indisponíveis{#gs-unavailable-features}

Observe que alguns recursos ainda não estão disponíveis nessa versão do Campaign, como:

* Gerenciamento de recursos de marketing
* Marketing distribuído
* Gestor de Resposta
* Modelos de implantação híbridos/no local

>[!CAUTION]
>
>* Por enquanto, o Campaign v8 está disponível **apenas** como um serviço na nuvem gerenciado e não pode ser implantado em um ambiente local ou híbrido.
>
>* A migração de um ambiente do Campaign Classic v7 existente ainda não está disponível.
>
>* Se não tiver certeza do modelo de implantação ou se tiver dúvidas, entre em contato com a equipe de conta.


## Recursos incompatíveis{#gs-removed}

Para alinhar-se à nova arquitetura e ao novo modelo de implantação do Campaign v8, alguns recursos históricos do Campaign Classic v7 não são mais compatíveis com o Campaign v8, como:

* Cupons
* Rastreamento web
* Pesquisas
* Marketing social o Facebook
* Conector ACS (oferta principal)
* Integração com o LDAP
* Logon de usuário/senha

>[!NOTE]
>
>Alguns recursos não disponíveis ou incompatíveis ainda estão visíveis na interface do usuário.
