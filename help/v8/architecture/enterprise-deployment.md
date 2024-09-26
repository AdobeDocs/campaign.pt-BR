---
title: Introdução à implantação do FFDA do Campaign
description: Introdução à implantação do FFDA do Campaign
feature: Architecture, FFDA, Deployment
role: Admin, Developer
level: Beginner
exl-id: 0a6f6701-b137-4320-9732-31946509ee03
source-git-commit: 9d500f185a9e706b6558135978c4f8c79d92d0d4
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 50%

---

# [!DNL Campaign] implantação do FFDA {#gs-ac-ffda}

Ao utilizar o [[!DNL Snowflake]](https://www.snowflake.com/){target="_blank"}, uma tecnologia de banco de dados em nuvem, a implantação do Adobe Campaign Enterprise Full Federated Access (FFDA) melhora consideravelmente sua escala e velocidade, com a capacidade de gerenciar um número muito maior de perfis de clientes, bem como taxas de entrega e transações por hora muito mais altas.

## Benefícios {#ffda-benefits}

O Campaign v8 Enterprise (FFDA) traz uma escala completa em qualquer etapa do processo, desde o direcionamento até os relatórios finais:

* Dimensione o volume de dados que você pode manipular (até 8 TB)
* Dimensione o desempenho das consultas para segmentação e direcionamento, mas também a assimilação e a saída de dados
* Dimensionar a preparação da entrega (de horas a minutos)

É uma mudança fundamental na arquitetura de software. Agora os dados são remotos e o Campaign federa todos os dados, incluindo Perfis. Os processos do [!DNL Campaign] agora são escalonados de ponta a ponta, desde o direcionamento até a execução da mensagem: assimilação de dados, segmentação, direcionamento, consultas e entregas agora normalmente são executados em minutos. Esta nova versão resolve todo o desafio do dimensionamento, mantendo o mesmo nível de flexibilidade e extensibilidade. O número de perfis é quase ilimitado e a retenção de dados pode ser estendida.

O armazenamento na nuvem é feito no **[!DNL Snowflake]**: uma nova **conta externa** incorporada garante a conectividade com o banco de dados na nuvem. Ele é configurado pela Adobe e não deve ser modificado. [Saiba mais](../config/external-accounts.md)

Qualquer esquema/tabela interna que precise ser movido ou replicado no banco de dados na nuvem vem com uma extensão de esquema incorporada no namespace **xxl**. Essas extensões contêm as modificações necessárias para mover esquemas integrados do banco local do [!DNL Campaign] para o banco de dados na nuvem do [!DNL Snowflake] e adaptar sua estrutura em conformidade: novo UUID, links atualizados, etc.

>[!CAUTION]
>
> Os dados do cliente não são armazenados no banco de dados local do [!DNL Campaign]. Como consequência, qualquer tabela personalizada precisa ser criada no banco de dados na nuvem.
>

## Arquitetura corporativa (FFDA) do Campaign{#ffda-archi}

Em uma implantação [Corporativa (FFDA)](../architecture/enterprise-deployment.md), o [!DNL Adobe Campaign] v8 funciona com dois bancos de dados: um banco de dados [!DNL Campaign] local para a interface de mensagens em tempo real, consultas unitárias e gravações por meio de APIs, e um banco de dados [!DNL Snowflake] da Nuvem para execução de campanha, consultas em lote e execução de fluxo de trabalho.

O Campaign v8 Enterprise traz o conceito de **Full Federated Data Access** (FFDA): agora, todos os dados estão disponíveis remotamente no banco de dados da nuvem.

APIs específicas estão disponíveis para gerenciar dados entre o banco de dados local e na nuvem. Saiba como essas novas APIs funcionam e como usá-las [nesta página](new-apis.md).

A comunicação geral entre servidores e processos é realizada de acordo com o seguinte esquema:

![](assets/architecture.png)

* Os módulos de gerenciamento de execução e rejeição estão desativados na instância.
* O aplicativo é configurado para executar mensagens em um servidor remoto de &quot;origem intermediária&quot; que é orientado por chamadas SOAP (por HTTP ou HTTPS).

O banco de dados [!DNL Snowflake] no lado de marketing é usado para:

* Armazene todos os dados do cliente: perfis, dados personalizados, como transações, produtos, locais etc.
* Armazene todos os eventos e dados de comportamento gerados ou coletados pelo Campaign, como logs do delivery, logs de rastreamento, registros de push etc.
* Armazene todos os agregados de dados do acima.
* Armazenar uma cópia (h+1) de tabelas de referência (como deliveries, enumerações, países etc.) que são usados em workflows, campanhas e relatórios.
* Executar todos os processos em lote e cargas de trabalho


O banco de dados PostgreSQL na instância de marketing é usado para:

* Execute determinadas cargas de trabalho, como APIs de baixo volume.
* Armazene todos os dados do Campaign, incluindo configurações de entrega e campanha, fluxo de trabalho e definições de serviço.
* Armazenar todas as tabelas de referência integradas (listas discriminadas, países etc.) que são replicados para [!DNL Snowflake].

  No entanto, não é possível:
   * criar personalizações para dados do cliente, por exemplo, não crie uma tabela de família no PostgreSQL, mas somente no Snowflake
   * armazenar logs do delivery, logs de rastreamento etc. na targeting dimension FFDA.
   * armazenar grande volume de dados.


O banco de dados PostgreSQL na instância mid-sourcing é usado para:

* Execute deliveries em lote e em tempo real (RT).
* Enviar logs de entrega e rastreamento - observe que as IDs de log de entrega e rastreamento são UUIDs e não IDs de 32 bits.
* Colete e armazene dados de rastreamento.


## Impactos{#ffda-impacts}

### Mecanismo de preparo da API [!DNL Campaign]{#staging-api}

Com o banco de dados de nuvem do [!DNL Campaign], as chamadas unitárias de explosão não são recomendadas devido ao desempenho (latência e simultaneidade). A menos que você esteja enviando um volume de envio extremamente grande, a operação em lote deve ser usada para garantir o desempenho ideal das APIs. O Campaign continua lidando com chamadas de API no nível do banco de dados local.

[O mecanismo de preparo da API é detalhado nesta página](staging.md)

### Novas APIs{#new-apis}

Novas APIs estão disponíveis para gerenciar a sincronização de dados entre o banco de dados local do [!DNL Campaign] e o banco de dados na nuvem. Um novo mecanismo também foi introduzido para lidar com chamadas de API no nível do banco de dados local para evitar latência e aumentar o desempenho geral.

[As novas APIs estão detalhadas nesta página](new-apis.md)


### Replicação de dados{#data-replication}

Um fluxo de trabalho técnico específico trata da replicação de tabelas que precisam estar presentes em ambos os lados (banco de dados local do Campaign e banco de dados da nuvem). Esse fluxo de trabalho é acionado a cada hora e depende de uma nova biblioteca JavaScript integrada.

>[!NOTE]
>
> Várias políticas de replicação foram criadas, com base no tamanho da tabela (XS, XL etc.).
> Algumas tabelas são replicadas em tempo real, outras são replicadas de hora em hora. Algumas tabelas terão atualizações incrementais; outras terão uma atualização completa.
>

[Saiba mais sobre replicação de dados](replication.md)

### Gerenciamento de ID{#id-mgt-ffda}

Os objetos do Campaign v8 agora usam um **Identificador exclusivo universal (UUID)**, que permite que valores exclusivos ilimitados identifiquem dados.

Observe que essa ID é baseada em uma string e não é sequencial. A chave primária não é um valor numérico no Campaign v8 e você precisa usar os atributos **autouuid** e **autopk** em seus esquemas.

No Campaign Classic v7 e em versões anteriores, a unicidade de uma chave em um esquema (ou seja, tabela) é manipulada no nível do mecanismo de banco de dados. Em geral, os mecanismos do banco de dados do Classic como PostgreSQL, Oracle ou SQL Server incluem um mecanismo nativo para impedir a inserção de linhas duplicadas com base em uma coluna ou um conjunto de colunas por meio de chaves principais e/ou índices únicos. A ID duplicada não existe nessas versões quando o índice adequado e as chaves principais são definidos no nível do banco de dados.

O Adobe Campaign v8 vem com o Snowflake como o banco de dados principal. Como aumenta drasticamente a escala de consultas, a arquitetura distribuída do banco de dados do Snowflake não fornece esses mecanismos para gerenciar e impor a unicidade de uma chave dentro de uma tabela. Como consequência, com o Adobe Campaign v8, nada impede a assimilação de chaves duplicadas em uma tabela. Os usuários finais agora são responsáveis por garantir a consistência das chaves no banco de dados do Adobe Campaign. [Saiba mais](keys.md)

### Disponibilidade de recursos {#feature-availability}

Alguns recursos não estão disponíveis no contexto de uma implantação Corporativa (FFDA) do Campaign, como:

* Gerenciamento de recursos de marketing
* Cupons
* Rastreamento web
* Pesquisas


**Tópicos relacionados**

* [Práticas recomendadas do modelo de dados](../dev/datamodel-best-practices.md)
