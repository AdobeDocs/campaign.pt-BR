---
title: Introdução à implantação do Campaign FDA
description: Introdução à implantação do Campaign FDA
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 53%

---

# [!DNL Campaign] Implantação FFDA{#gs-ac-ffda}

Por alavancagem [[!DNL Snowflake]](https://www.snowflake.com/), uma tecnologia de banco de dados em nuvem, a implantação do Adobe Campaign Enterprise Full Federated Access (FDA) melhora consideravelmente sua escala e velocidade, com a capacidade de gerenciar um número mais significativo de perfis de clientes, bem como taxas de delivery e transações por hora mais altas.

## Benefícios {#ffda-benefits}

O Campaign v8 Enterprise (FDA) oferece escala completa em qualquer etapa do processo, desde o direcionamento até o relatório final:

* Dimensione o volume de dados que você pode manipular (até 8 TB)
* Dimensione o desempenho das consultas para segmentação e direcionamento, mas também a assimilação e a saída de dados
* Dimensionar a preparação da entrega (de horas a minutos)

É uma mudança fundamental na arquitetura de software. Agora os dados são remotos e o Campaign federa todos os dados, incluindo Perfis. Os processos do [!DNL Campaign] agora são escalonados de ponta a ponta, desde o direcionamento até a execução da mensagem: assimilação de dados, segmentação, direcionamento, consultas e entregas agora normalmente são executados em minutos. Esta nova versão resolve todo o desafio do dimensionamento, mantendo o mesmo nível de flexibilidade e extensibilidade. O número de perfis é quase ilimitado e a retenção de dados pode ser estendida.

O armazenamento na nuvem é feito no **[!DNL Snowflake]**: uma nova **conta externa** incorporada garante a conectividade com o banco de dados na nuvem. Ele é configurado pela Adobe e não deve ser modificado. [Saiba mais](../config/external-accounts.md)

Qualquer esquema/tabela interna que precise ser movido ou replicado no banco de dados na nuvem vem com uma extensão de esquema incorporada no namespace **xxl**. Essas extensões contêm as modificações necessárias para mover esquemas integrados do banco local do [!DNL Campaign] para o banco de dados na nuvem do [!DNL Snowflake] e adaptar sua estrutura em conformidade: novo UUID, links atualizados, etc.

>[!CAUTION]
>
> Os dados do cliente não são armazenados no banco de dados local do [!DNL Campaign]. Como consequência, qualquer tabela personalizada precisa ser criada no banco de dados na nuvem.

## Arquitetura do Campaign Enterprise (FDA){#ffda-archi}

Em um [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] O v8 funciona com dois bancos de dados: um local [!DNL Campaign] banco de dados para a interface do usuário, mensagens em tempo real e consultas unitárias e gravação por meio de APIs, e uma nuvem [!DNL Snowflake] banco de dados para execução da campanha, consultas em lote e execução do workflow.

O Campaign v8 Enterprise traz o conceito de **Acesso completo a dados federados** (FFDA): todos os dados agora são remotos no banco de dados da nuvem.

APIs específicas estão disponíveis para gerenciar dados entre o banco de dados local e na nuvem. Saiba como essas novas APIs funcionam e como usá-las [nesta página](new-apis.md).

A comunicação geral entre servidores e processos é realizada de acordo com o seguinte schema:

![](assets/architecture.png)

* Os módulos de gerenciamento de execução e rejeição estão desabilitados na instância.
* O aplicativo é configurado para executar a execução de mensagens em um servidor remoto &quot;mid-sourcing&quot;, que é orientado por chamadas SOAP (via HTTP ou HTTPS).

O [!DNL Snowflake] o banco de dados do lado do marketing é usado para:

* Armazenar todos os dados do cliente: perfis, dados personalizados, como transações, produtos, locais etc.
* Armazene todos os eventos e dados de comportamento gerados ou coletados pelo Campaign, como logs do delivery, logs de rastreamento, registros de push etc.
* Armazene todos os agregados de dados do acima.
* Armazene uma cópia (h+1) das tabelas de referência (como deliveries, enumerações, países etc.) que são usadas em workflows, campanhas e relatórios.
* Executar todos os processos e cargas de trabalho em lote


O banco de dados PostgreSQL na instância de marketing é usado para:

* Execute determinadas cargas de trabalho, como APIs de baixo volume.
* Armazene todos os dados do Campaign, incluindo configurações de delivery e campanha, definições de workflow e de serviço.
* Armazene todas as tabelas de referência integradas (enumerações, países etc.) que sejam replicados para [!DNL Snowflake].

   No entanto, não é possível:
   * criar personalizações para dados de clientes, por exemplo, não crie uma tabela de família no PostgreSQL, mas somente no Snowflake
   * armazene todos os logs do delivery, logs de rastreamento etc. no targeting dimension FDA.
   * armazene um grande volume de dados.


O banco de dados PostgreSQL na instância mid-sourcing é usado para:

* Execute deliveries em lote e em tempo real (RT).
* Enviar logs de delivery e rastreamento - observe que as IDs de log de delivery e rastreamento são UUIDs e não IDs de 32 bits.
* Colete e armazene dados de rastreamento.


## Impactos{#ffda-impacts}

### [!DNL Campaign] Mecanismo de preparo da API{#staging-api}

Com [!DNL Campaign] O banco de dados da nuvem, as chamadas unitárias de explosão não são recomendadas devido ao desempenho (latência e simultaneidade). A operação em lote é sempre preferida. Para garantir desempenho ideal das APIs, o Campaign continua lidando com chamadas de API no nível do banco de dados local.

![](../assets/do-not-localize/glass.png) [O mecanismo de preparo da API é detalhado nesta página](staging.md)

### Novas APIs{#new-apis}

Novas APIs estão disponíveis para gerenciar a sincronização de dados entre [!DNL Campaign] banco de dados local e banco de dados do Cloud. Um novo mecanismo também foi introduzido para lidar com chamadas de API no nível do banco de dados local, a fim de evitar latência e aumentar o desempenho geral.

![](../assets/do-not-localize/glass.png) [As novas APIs são detalhadas nesta página](new-apis.md)


### Replicação de dados{#data-replication}

Um fluxo de trabalho técnico específico trata da replicação de tabelas que precisam estar presentes em ambos os lados (banco de dados local do Campaign e banco de dados da nuvem). Esse fluxo de trabalho é acionado a cada hora e depende de uma nova biblioteca JavaScript integrada.

>[!NOTE]
>
> Várias políticas de replicação foram criadas, com base no tamanho da tabela (XS, XL etc.).
> Algumas tabelas são replicadas em tempo real, outras são replicadas de hora em hora. Algumas tabelas terão atualizações incrementais; outras terão uma atualização completa.

[Saiba mais sobre replicação de dados](replication.md)

### Gerenciamento de ID{#id-mgt-ffda}

Os objetos do Campaign v8 agora usam um **Identificador exclusivo universal (UUID)**, que permite que valores exclusivos ilimitados identifiquem dados.

Observe que essa ID é baseada em uma sequência e não é sequencial. A chave primária não é um valor numérico no Campaign v8 e você precisa usar os atributos **autouuid** e **autopk** em seus esquemas.

No Campaign Classic v7 e em versões anteriores, a unicidade de uma chave em um esquema (ou seja, tabela) é manipulada no nível do mecanismo de banco de dados. Em geral, os mecanismos do banco de dados do Classic como PostgreSQL, Oracle ou SQL Server incluem um mecanismo nativo para impedir a inserção de linhas duplicadas com base em uma coluna ou um conjunto de colunas por meio de chaves principais e/ou índices únicos. A ID duplicada não existe nessas versões quando o índice adequado e as chaves principais são definidos no nível do banco de dados.

O Adobe Campaign v8 vem com o Snowflake como o banco de dados principal. Como aumenta drasticamente a escala de consultas, a arquitetura distribuída do banco de dados do Snowflake não fornece esses mecanismos para gerenciar e impor a unicidade de uma chave dentro de uma tabela. Como consequência, com o Adobe Campaign v8, nada impede a assimilação de chaves duplicadas em uma tabela. Os usuários finais agora são responsáveis por garantir a consistência das chaves no banco de dados do Adobe Campaign. [Saiba mais](keys.md)

**Tópicos relacionados**

* [Práticas recomendadas do modelo de dados](../dev/datamodel-best-practices.md)
