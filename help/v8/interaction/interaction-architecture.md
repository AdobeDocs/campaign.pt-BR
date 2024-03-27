---
title: Entender a arquitetura de interação do Campaign
description: Noções básicas sobre a arquitetura de interação do Campaign
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 7a710960-7e41-4462-bd5e-18e874aa46f8
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 67%

---

# Entender os ambientes e a arquitetura da interação do Campaign

## Ambientes {#environments}

Há dois ambientes para cada targeting dimension usada ao gerenciar ofertas:

* A **design** ambiente no qual o gerente de ofertas cuida da criação e categorização de ofertas, edição e início do processo de aprovação para que elas possam ser usadas. As regras para cada categoria, os espaços de oferta nos quais as ofertas podem ser apresentadas e os filtros predefinidos usados para definir a elegibilidade de uma oferta também são definidos neste ambiente.

  As categorias também podem ser publicadas manualmente no ambiente online.

  O processo de aprovação de ofertas é detalhado [nesta seção](interaction-offer.md#approve-offers).

* A **live** ambiente no qual podem ser encontradas ofertas aprovadas do ambiente de design, bem como os vários espaços de oferta, filtros, categorias e regras configurados no ambiente de design. Durante uma chamada para o mecanismo de Oferta, o mecanismo sempre usará ofertas do ambiente ativo.

Uma oferta só é implantada nos espaços de oferta selecionados durante o processo de aprovação. Portanto, uma oferta pode estar ativa, mas inutilizável em um espaço de oferta que também está ativo.

## Interações de entrada e saída {#interaction-types}

O módulo de Interação do Adobe Campaign propõe dois tipos de interações:

* **entrada** interações, iniciadas por um contato. [Saiba mais](interaction-present-offers.md)
* **saída** interações, iniciadas por um Gerente de delivery do Campaign. [Saiba mais](interaction-send-offers.md)

Esses dois tipos de interações podem ser realizadas em **modo unitário** (a oferta é calculada para um único contato) ou em **modo de lote** (a oferta é calculada para um conjunto de contatos). Geralmente, as interações de entrada são realizadas no modo unitário e as interações de saída são executadas em modo de lote. No entanto, podem existir certas exceções, [mensagens transacionais](../send/transactional.md) por exemplo, onde a interação de saída é executada no modo unitário.

Assim que uma oferta puder ou deve ser apresentada (de acordo com as configurações realizadas), o mecanismo de Oferta reproduzirá a função intermediária: ele calcula automaticamente a melhor oferta possível para um contato entre as disponíveis ao combinar dados recebidos sobre o contato e as diferentes regras que podem ser aplicadas conforme especificado na aplicação.

![](assets/architecture_interaction2.png)

## Arquitetura distribuída

Para oferecer suporte à escalabilidade e fornecer serviço 24 horas por dia, 7 dias por semana no canal de entrada, a variável **Interação** O módulo é implementado em uma arquitetura distribuída. Esse tipo de arquitetura já é usado com o [Centro de mensagens](../architecture/architecture.md#transac-msg-archi) e é composto por várias instâncias:

* uma ou várias instâncias de controle dedicadas ao canal de saída e contendo a base de design de marketing e ambiente.
* uma ou várias instâncias de execução dedicadas ao canal de entrada.

![](assets/interaction_powerbooster_schema.png)

As instâncias de controle são dedicadas ao canal de entrada e contêm a versão online do catálogo. Cada instância de execução é independente e dedicada a um segmento de contato (por exemplo, uma instância de execução por país). As chamadas para o mecanismo de oferta devem ser executadas diretamente na execução (uma URL específica por instância de execução). Como a sincronização entre instâncias não é automática, as interações do mesmo contato devem ser enviadas pela mesma instância.

### Sincronização {#synchronization}

A sincronização de oferta é realizada por meio de pacotes. Em instâncias de execução, todos os objetos de catálogo são prefixados pelo nome da conta externa. Isso significa que várias instâncias de controle (instâncias de desenvolvimento e produção por exemplo) podem ser suportadas em uma mesma instância de execução.

>[!CAUTION]
>
>Use nomes internos curtos e explícitos.

As ofertas são automaticamente implantadas e publicadas em instâncias de execução e controle.

Ofertas excluídas no ambiente de design são desabilitadas em todas as instâncias online. As propostas e ofertas obsoletas são excluídas automaticamente em todas as instâncias após o período de purga (especificado no assistente de implantação de cada instância) e o período de deslizamento (especificado nas regras de tipologia de propostas de entrada).

![](assets/interaction_powerbooster_schema2.png)

Um workflow é criado para cada ambiente e conta externa para a sincronização de propostas. A frequência de sincronização pode ser ajustada para cada ambiente e conta externa.

Você deve estar ciente dos seguintes mecanismos de sincronização:

* Se usar a função de fallback de um ambiente anônimo para um ambiente identificado, esses dois ambientes deverão estar na mesma instância de execução.
* A sincronização entre várias instâncias de execução não é executada em tempo real. As interações do mesmo contato devem ser enviadas para a mesma instância. A instância de controle deve ser dedicada ao canal de saída (sem tempo real).
* O banco de dados de marketing não é sincronizado automaticamente. Os dados de marketing usados nos pesos e regras de qualificação devem ser duplicados em instâncias de execução. Esse processo não é fornecido como padrão, é necessário desenvolvê-lo durante o período de integração.
* A sincronização de propostas é realizada exclusivamente pela conexão FDA.
* Se usar o Interaction e o Message Center na mesma instância, a sincronização ocorrerá por meio do protocolo FDA nos dois casos.

### Configuração de pacotes {#packages-configuration}

Quaisquer extensões de schema diretamente vinculadas à **Interação** (ofertas, propostas, destinatários, etc.) devem ser implantadas nas instâncias de execução.

A variável **Interação** O pacote de é instalado em todas as instâncias (controle e execução). Dois pacotes adicionais estão disponíveis: um pacote para as instâncias de controle e outro para cada instância de execução.

>[!NOTE]
>
>Ao instalar o pacote, os campos do tipo **longo** da tabela **nms:proposition**, como ID da proposta, tornam-se campos de tipo **int64.** Esse tipo de dado é detalhado no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/schema-structure.html#mapping-the-types-of-adobe-campaign-dbms-data){target="_blank"}.

A duração da retenção de dados é configurada em cada instância (por meio da variável **[!UICONTROL Data purge]** no assistente de implantação). Em instâncias de execução, esse período deve corresponder à profundidade histórica necessária para as regras de tipologia (período de deslizamento) e as regras de qualificação serem calculadas.

Nas instâncias de controle:

1. Crie uma conta externa por instância de execução:

   ![](assets/interaction_powerbooster1.png)

   * Complete o rótulo e adicione um nome interno curto e explícito.
   * Selecione o **[!UICONTROL Execution instance]**.
   * Marque a opção **[!UICONTROL Enabled]**.
   * Conclua os parâmetros de conexão da instância de execução.
   * Cada instância de execução deve ser vinculada a um ID. Esse ID é atribuído ao clicar no botão **[!UICONTROL Initialize connection]**.
   * Verifique o tipo de aplicativo usado:**[!UICONTROL Message Center]**, **[!UICONTROL Interaction]** ou ambos.
   * Insira a conta da FDA utilizada. Um operador deve ser criado nas instâncias de execução e deve ter os seguintes direitos de leitura e gravação no banco de dados da instância em questão:

     ```
     grant SELECT ON nmspropositionrcp, nmsoffer, nmsofferspace, xtkoption, xtkfolder TO user;
     grant DELETE, INSERT, UPDATE ON nmspropositionrcp TO user;
     ```

   >[!NOTE]
   >
   >O endereço IP da instância de controle deve ser autorizado nas instâncias de execução.

1. Configure o ambiente:

   ![](assets/interaction_powerbooster2.png)

   * Adicione a lista de instâncias de execução.
   * Para cada um, especifique o período de sincronização e os critérios do filtro (por exemplo, por país).

     >[!NOTE]
     >
     >Se encontrar um erro, poderá consultar os workflows de sincronização e oferecer notificações. Eles podem ser encontrados nos workflows técnicos do aplicativo.

Se, por motivos de otimização, apenas parte do banco de dados de marketing for duplicado nas instâncias de execução, é possível especificar um schema restrito vinculado ao ambiente para permitir que os usuários usem apenas dados que estejam disponíveis nas instâncias de execução. É possível criar uma oferta usando dados que não estão disponíveis em instâncias de execução. Para fazer isso, é necessário desativar a regra nos outros canais limitando essa regra no canal de saída (campo **[!UICONTROL Taken into account if]**).

![](assets/ita_filtering.png)

### Opções de manutenção {#maintenance-options}

Aqui está uma lista de opções de manutenção disponíveis na instância de controle:

>[!CAUTION]
>
>Essas opções só devem ser usadas para casos de manutenção específicos.

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: última data em que um ambiente foi sincronizado em uma determinada instância.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: última data em que as propostas de um determinado schema foram sincronizadas de uma instância para outra.
* **`NmsInteraction_MapWorkflowId`**: uma opção contendo a lista de todos os workflows de sincronização gerados.

A seguinte opção está disponível nas instâncias de execução:

**NmsExecutionInstanceId**: opção contendo o ID da instância.

### Instalação de pacotes {#packages-installation}

Se a instância não tiver o plug-in **Interação** pacote, nenhuma migração é necessária. Por padrão, a tabela de propostas estará em 64 bits após a instalação dos pacotes.

>[!CAUTION]
>
>Dependendo do volume de propostas existentes na instância, essa operação pode demorar algum tempo.

* Se a instância tiver pouca ou nenhuma proposta, nenhuma modificação manual da tabela de propostas será necessária. A modificação será feita quando os pacotes estiverem instalados.
* Se a instância tiver muitas propostas, é melhor alterar a estrutura da tabela de propostas antes de instalar os pacotes de controle e executá-las. Recomendamos executar as queries durante um período de baixa atividade.

>[!NOTE]
>
>Se as configurações específicas na tabela de propostas foram executadas, adapte as queries de acordo.


Há dois métodos:

**Tabela de trabalho** (recomendado)

```
CREATE TABLE NmsPropositionRcp_tmp AS SELECT * FROM nmspropositionrcp WHERE 0=1;
ALTER TABLE nmspropositionrcp_tmp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
INSERT INTO nmspropositionrcp_tmp SELECT * FROM nmspropositionrcp;
DROP TABLE nmspropositionrcp;
CREATE INDEX proposition_id ON NmsPropositionRcp (ipropositionid);
CREATE INDEX nmspropositionrcp_deliveryid ON NmsPropositionRcp (ideliveryid);
CREATE INDEX nmspropositionrcp_lastmodified ON NmsPropositionRcp (tslastmodified);
CREATE INDEX nmspropositionrcp_offerid ON NmsPropositionRcp (iofferid);
CREATE INDEX nmspropositionrcp_offerspaceid ON NmsPropositionRcp (iofferspaceid);
CREATE INDEX nmspropositionrcp_recipientidid ON NmsPropositionRcp (irecipientid);
ALTER TABLE nmspropositionrcp_tmp RENAME TO nmspropositionrcp;
```

**Alterar Tabela**

```
ALTER TABLE nmspropositionrcp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
```
