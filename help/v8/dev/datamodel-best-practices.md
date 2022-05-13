---
title: Práticas recomendadas do modelo de dados
description: Conheça as práticas recomendadas de extensão do modelo de dados do Campaign
exl-id: bdd5e993-0ce9-49a8-a618-ab0ff3796d49
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '2717'
ht-degree: 4%

---

# Práticas recomendadas do modelo de dados{#data-model-best-practices}

Este documento descreve as principais recomendações ao projetar o modelo de dados do Adobe Campaign.

O sistema Adobe Campaign é muito flexível e pode ser estendido além da implementação inicial. No entanto, embora as possibilidades sejam infinitas, é fundamental tomar decisões sábias e criar bases fortes para começar a projetar seu modelo de dados.

Para obter uma melhor compreensão das tabelas integradas do Campaign e como elas se relacionam entre si, consulte [esta seção](datamodel.md) .

![](../assets/do-not-localize/glass.png) Leia [esta seção](schemas.md) para começar a usar os esquemas do Campaign.

![](../assets/do-not-localize/glass.png) Saiba como configurar schemas de extensão para estender o modelo de dados conceituais do banco de dados do Adobe Campaign em [esta página](extend-schema.md).

## Arquitetura do modelo de dados {#data-model-architecture}

O Adobe Campaign é um poderoso sistema de gerenciamento de campanhas em vários canais que pode ajudar você a alinhar suas estratégias online e offline para criar experiências personalizadas de clientes.

### Abordagem centrada no cliente {#customer-centric-approach}

Embora a maioria dos provedores de serviços de email esteja se comunicando com os clientes por meio de uma abordagem centrada em listas, o Adobe Campaign depende de um banco de dados relacional para aproveitar uma visão mais ampla dos clientes e seus atributos.

Para acessar a descrição de cada tabela, acesse **[!UICONTROL Admin > Configuration > Data schemas]**, selecione um recurso na lista e clique no botão **[!UICONTROL Documentation]** guia .


>[!NOTE]
>
>O Adobe Campaign permite criar um [tabela de recipient personalizada](custom-recipient.md). No entanto, na maioria dos casos, é recomendável aproveitar o [Tabela de recipients](datamodel.md#ootb-profiles) que já tem tabelas e recursos adicionais pré-criados.

### Dados do Adobe Campaign {#data-for-campaign}

Quais dados devem ser enviados para o Adobe Campaign? É importante determinar os dados necessários para suas atividades de marketing.

>[!NOTE]
>
>O Adobe Campaign não é um data warehouse nem uma ferramenta de relatórios. Portanto, não tente importar todos os clientes possíveis e suas informações associadas para o Adobe Campaign ou importe dados que serão usados apenas para criar relatórios.

Para decidir se um atributo seria necessário ou não no Adobe Campaign, pergunte a si mesmo se ele se enquadra em uma dessas categorias:

* Atributo usado para **segmentação**
* Atributo usado para **processos de gestão de dados** (cálculo agregado, por exemplo)
* Atributo usado para **personalização**

Se não estiver caindo em nenhum desses, você provavelmente não precisará desse atributo no Adobe Campaign.

### Escolha dos tipos de dados {#data-types}

Para garantir uma boa arquitetura e o desempenho do sistema, siga as práticas recomendadas abaixo para configurar os dados no Adobe Campaign.

* Em uma tabela grande, é possível inserir campos de sequência ou numéricos e adicionar links a tabelas de referência (ao trabalhar com a lista de valores).
* O **expr** permite definir um atributo de schema como um campo calculado em vez de um valor de conjunto físico em uma tabela. Isso pode habilitar o acesso às informações em um formato diferente (como para idade e data de nascimento, por exemplo) sem a necessidade de armazenar ambos os valores. Essa é uma boa maneira de evitar a duplicação de campos. Por exemplo, a tabela Recipient usa uma expressão para o domínio, que já está presente no campo de email.
* No entanto, quando o cálculo da expressão é complexo, não é recomendável usar a variável **expr** como cálculo dinâmico pode afetar o desempenho de suas consultas.
* O **XML** é uma boa maneira de evitar a criação de muitos campos. Mas também ocupa espaço em disco, pois usa uma coluna CLOB no banco de dados. Também pode levar a queries SQL complexos e afetar o desempenho.
* O comprimento de um **string** deve ser sempre definido com a coluna . Por padrão, o comprimento máximo no Adobe Campaign é de 16K, mas o Adobe recomenda manter o campo mais curto se você já souber que o tamanho não excederá um comprimento menor.
* É aceitável ter um campo menor no Adobe Campaign do que no sistema de origem se você tiver certeza de que o tamanho no sistema de origem foi superestimado e não seria atingido. Isso pode significar uma string menor ou um número inteiro menor no Adobe Campaign.

### Escolha dos campos {#choice-of-fields}

Um campo precisa ser armazenado em uma tabela se tiver uma finalidade de direcionamento ou personalização. Em outras palavras, se um campo não for usado para enviar um email personalizado ou como um critério em uma query, ele ocupará espaço em disco desnecessariamente.

### Escolha de chaves {#choice-of-keys}

Além do **autouuid** e **autopk** definido por padrão na maioria das tabelas, você deve considerar adicionar algumas chaves lógicas ou comerciais (número de conta, número de cliente e assim por diante). Ele pode ser usado posteriormente para importações/reconciliação ou pacotes de dados. Para obter mais informações, consulte [Identificadores](#identifiers).

Chaves eficientes são essenciais para o desempenho. Com o Snowflake, é possível inserir tipos de dados numéricos ou baseados em sequência como chaves para tabelas.

>[!NOTE]
>
>O **autouuid** somente se aplica a [Implantações empresariais (FDA)](../architecture/enterprise-deployment.md).

## Identificadores {#identifiers}

Os recursos do Adobe Campaign têm três identificadores e é possível adicionar um identificador adicional.

A tabela a seguir descreve esses identificadores e sua finalidade.

| Identifier | Descrição | Práticas recomendadas |
|--- |--- |--- |
| ID | <ul><li>A id é a chave primária física de uma tabela do Adobe Campaign. Para tabelas integradas, é uma ID universal exclusiva (UUID)</li><li>Esse identificador deve ser exclusivo. </li><li>Uma UUID pode ser visível em uma definição de esquema.</li></ul> | <ul><li>Os identificadores gerados automaticamente não devem ser usados como referência em um workflow ou em uma definição de pacote.</li><li>A id em uma tabela é um UUID e esse tipo não deve ser alterado.</li></ul> |
| Nome (ou nome interno) | <ul><li>Essas informações são um identificador exclusivo de um registro em uma tabela. Esse valor pode ser atualizado manualmente, geralmente com um nome gerado.</li><li>Esse identificador mantém seu valor quando implantado em uma instância diferente do Adobe Campaign e não deve estar vazio.</li></ul> | <ul><li>Renomeie o nome do registro gerado pelo Adobe Campaign se o objeto for implantado de um ambiente para outro.</li><li>Quando um objeto tem um atributo de namespace (*schema* por exemplo), esse namespace comum será aproveitado em todos os objetos personalizados criados. Alguns namespaces reservados não devem ser usados: *nms*, *xtk*, etc.  Observe que alguns namespaces são somente internos. [Saiba mais](schemas.md#reserved-namespaces).</li><li>Quando um objeto não tem namespace (*workflow* ou *delivery* por exemplo), essa noção de namespace seria adicionada como um prefixo de um objeto de nome interno: *namespaceMyObjectName*.</li><li>Não use caracteres especiais, como espaço &quot;&quot;, semircoluna &quot;:&quot; ou hífen &quot;-&quot;. Todos esses caracteres seriam substituídos por um sublinhado &quot;_&quot; (caractere permitido). Por exemplo, &quot;abc-def&quot; e &quot;abc:def&quot; seriam armazenadas como &quot;abc_def&quot; e se substituiriam.</li></ul> |
| Rótulo | <ul><li>O rótulo é o identificador comercial de um objeto ou registro no Adobe Campaign.</li><li>Esse objeto permite espaços e caracteres especiais.</li><li>Não garante a singularidade de um registro.</li></ul> | <ul><li>É recomendável determinar uma estrutura para seus rótulos de objetos.</li><li>Essa é a solução mais fácil de usar para identificar um registro ou objeto para um usuário do Adobe Campaign.</li></ul> |

No contexto de um [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), a chave primária do Adobe Campaign é um UUID gerado automaticamente para todas as tabelas incorporadas. Uma UUID também pode ser usada para tabelas personalizadas. [Saiba mais](../architecture/keys.md)

Mesmo que o número de IDs seja infinito, é necessário tomar cuidado com o tamanho do banco de dados para garantir desempenho ideal. Para evitar qualquer problema, ajuste as configurações de limpeza de instância. Para obter mais informações, consulte [esta seção](#data-retention).


## Chaves internas personalizadas {#custom-internal-keys}

As chaves primárias são necessárias para cada tabela criada no Adobe Campaign.

A maioria das organizações está importando registros de sistemas externos. Embora a chave física da tabela Recipient seja o atributo &quot;id&quot;, é possível determinar uma chave personalizada além disso.

Essa chave personalizada é a chave primária de registro real no sistema externo que alimenta o Adobe Campaign.

Ao criar uma tabela personalizada, você tem duas opções:
* Uma combinação de chave gerada automaticamente (id) e chave interna (personalizada). Essa opção é interessante se a chave do sistema for uma chave composta ou não um inteiro. Com Snowflake, números inteiros ou chaves baseadas em sequência fornecerão desempenho mais alto em grandes tabelas e unirão a outras tabelas.
* Usar a chave primária como a chave primária do sistema externo. Essa solução geralmente é preferida, pois simplifica a abordagem para importar e exportar dados, com uma chave consistente entre diferentes sistemas. **Autouuid** deve ser desativado se a chave for chamada de &quot;id&quot; e se espera que seja preenchida com valores externos (não gerados automaticamente).

>[!CAUTION]
>
>* Uma autouuid não deve ser usada como referência em workflows.
> * O **autouuid** somente se aplica a [Implantações empresariais (FDA)](../architecture/enterprise-deployment.md).
>


## Links e cardinalidade {#links-and-cardinality}

### Links {#links}

Cuidado com a &quot;própria&quot; integridade em tabelas grandes. Excluir registros que tenham tabelas grandes na integridade &quot;própria&quot; pode potencialmente interromper a instância. A tabela está bloqueada e as exclusões são feitas uma por uma. Portanto, é melhor usar integridade &quot;neutra&quot; em tabelas secundárias que têm grandes volumes.

Declarar um link como uma associação externa não é bom para o desempenho. O registro de id zero emula a funcionalidade de associação externa. No contexto de um [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), não é necessário declarar associações externas se o link usar o **autouuid**.

Embora seja possível unir qualquer tabela em um workflow, o Adobe recomenda definir links comuns entre recursos diretamente na definição da estrutura de dados.

O link deve ser definido de acordo com os dados reais nas tabelas. Uma definição incorreta pode afetar dados recuperados por meio de links, por exemplo, registros duplicados inesperadamente.

Nomeie seu link de forma consistente com o nome da tabela: o nome do link deve ajudar a entender o que é a tabela distante.

Não nomeie um link com &quot;id&quot; como sufixo. Por exemplo, nomeie-a como &quot;transaction&quot; em vez de &quot;transactionId&quot;.

Por padrão, o Adobe Campaign criará um link usando a chave primária da tabela externa. Para mais clareza, é preferível definir explicitamente a associação na definição do link.

### Cardinalidade {#cardinality}

Ao projetar um link, verifique se o registro de destino é exclusivo quando uma relação 1-1 foi declarada. Caso contrário, a associação poderá retornar vários registros quando apenas um for esperado. Isso resulta em erros durante a preparação do delivery quando &quot;a query retorna mais linhas do que o esperado&quot;. Defina o nome do link com o mesmo nome do schema de destino.

Defina um link com uma cardinalidade (1-N) no schema no lado (1). Por exemplo, a relação Recipient (1) - (N) Transaction deve ser definida no schema de transações.

Observe que uma cardinalidade reversa de um link é (N) por padrão. É possível definir um link (1-1) adicionando o atributo revCardinality=&#39;single&#39; à definição do link.

Se o link reverso não deve estar visível para o usuário, você pode ocultá-lo com a definição do link revLink=&#39;_NENHUM_&quot;. Um bom caso de uso para isso é definir um link do recipient para a última transação concluída, por exemplo. Você só precisa ver o link do recipient para a última transação e nenhum link reverso é necessário para ficar visível da tabela de transações.

Os links que executam uma associação externa (1-0.1) devem ser usados com cuidado, pois afetarão o desempenho do sistema.

## Retenção de dados {#data-retention}

O Adobe Campaign não é um data warehouse nem uma ferramenta de relatórios. Portanto, para garantir um bom desempenho da solução Adobe Campaign, o crescimento do banco de dados deve permanecer sob controle. Para isso, siga as práticas recomendadas abaixo.

Quanto à retenção, as tabelas de log integradas no Campaign têm períodos de retenção predefinidos, geralmente limitando o armazenamento dos dados a seis meses ou menos.

A seguir estão os valores de retenção padrão para tabelas integradas. Esteja ciente de que a configuração de retenção é definida pelos administradores técnicos da Adobe durante a implementação e os valores podem variar com base nos requisitos do cliente.

* **Rastreamento consolidado**: 1 ano
* **Registros de entrega**: 6 meses
* **Logs de rastreamento**: 1 ano
* **Deliveries excluídos**: 1 semana
* **Importação de rejeitos**: 6 meses
* **Perfis do visitante**: 1 mês
* **Apresentações da oferta**: 1 ano
* **Eventos**: 1 mês
* **Estatísticas de processamento de evento**: 1 ano
* **Eventos arquivados**: 1 ano
* **Eventos de pipeline ignorados**: 1 mês

>[!CAUTION]
>
>As tabelas personalizadas não são removidas com o processo de limpeza padrão. Embora isso possa não ser necessário no primeiro dia, não se esqueça de criar um processo de limpeza para suas tabelas personalizadas, pois isso pode levar a desafios de desempenho.

Existem algumas soluções para minimizar a necessidade de registros no Adobe Campaign:
* Exporte os dados em um data warehouse fora do Adobe Campaign.
* Gere valores agregados que usarão menos espaço enquanto forem suficientes para suas práticas de marketing. Por exemplo, não é necessário ter o histórico completo de transações do cliente no Adobe Campaign para rastrear as últimas compras.

Você pode declarar o atributo &quot;deleteStatus&quot; em um schema. É mais eficiente marcar o registro como excluído e, em seguida, adiar a exclusão na tarefa de limpeza.

![](../assets/do-not-localize/speech.png)  Como usuário do Managed Cloud Services, entre em contato com os consultores de Adobe ou administradores técnicos para saber mais sobre retenção ou se é necessário definir a retenção para tabelas personalizadas.

## Desempenho {#performance}

Para garantir melhor desempenho a qualquer momento, siga as práticas recomendadas abaixo.

### Recomendações gerais {#general-recommendations}

* Evite usar operações como &quot;CONTAINS&quot; em consultas. Se você sabe o que é esperado e deseja filtrar, aplique a mesma condição com um &quot;EQUAL TO&quot; ou outros operadores de filtro específicos.
* Tente e verifique se os processos como importação e exportação acontecem fora do horário comercial.
* Certifique-se de que haja um agendamento para todas as atividades diárias e siga o agendamento.
* Se um ou alguns dos processos diários falharem e se for obrigatório executá-lo no mesmo dia, verifique se não há processos conflitantes em execução quando o processo manual é iniciado, pois isso pode afetar o desempenho do sistema.
* Certifique-se de que nenhuma campanha diária seja executada durante o processo de importação ou quando qualquer processo manual for executado.
* Use uma ou várias tabelas de referência em vez de duplicar um campo em cada linha. Ao usar pares de chave/valor, é preferível escolher uma chave numérica.
* Uma string curta permanece aceitável. Caso as tabelas de referências já estejam em vigor em um sistema externo, reutilizar a mesma facilitará a integração de dados com o Adobe Campaign.

### Relações um para muitos {#one-to-many-relationships}

* O design de dados afeta a usabilidade e a funcionalidade. Se você projetar seu modelo de dados com muitas relações um para muitos, torna mais difícil para os usuários construir uma lógica significativa no aplicativo. A lógica de filtro one-to-many pode ser difícil para profissionais de marketing não técnicos construírem e compreenderem corretamente.
* É bom ter todos os campos essenciais em uma tabela, pois facilita a criação de consultas por parte dos usuários. Às vezes, também é bom que o desempenho duplique alguns campos nas tabelas se puder evitar uma junção.
* Determinadas funcionalidades integradas não poderão fazer referência a relações um para muitos, por exemplo, fórmula de Ponderação de ofertas e Deliveries.

## Tabelas grandes {#large-tables}

O Adobe Campaign depende de mecanismos de banco de dados de terceiros. Dependendo do provedor, a otimização do desempenho para tabelas maiores pode exigir um design específico.

Abaixo estão algumas práticas recomendadas comuns que devem ser seguidas ao projetar seu modelo de dados usando tabelas grandes e associações complexas.

* Ao usar tabelas de recipients personalizadas adicionais, verifique se você tem uma tabela de log dedicada para cada mapeamento de delivery.
* Reduza o número de colunas, principalmente identificando aquelas que não estão utilizadas.
* Otimize as relações do modelo de dados evitando associações complexas, como associações em várias condições e/ou várias colunas.
* Para chaves de junção, você pode usar valores numéricos ou baseados em sequência.
* Reduza o máximo possível de profundidade da retenção de log. Se precisar de um histórico mais profundo, você pode agregar computação e/ou manipular tabelas de log personalizadas para armazenar um histórico maior.

### Tamanho das tabelas {#size-of-tables}

O tamanho da tabela é uma combinação do número de registros e do número de colunas por registro. Ambos podem afetar o desempenho das consultas.

* A **tamanho pequeno** é semelhante à tabela Delivery .
* A **tamanho médio** tabela é igual ao tamanho da tabela Recipient . Ele tem um registro por cliente.
* A **tamanho grande** é semelhante à tabela Broad log . Ele tem muitos registros por cliente.
Por exemplo, se seu banco de dados contém 10 milhões de recipients, a tabela Broad log contém cerca de 100 a 200 milhões de mensagens e a tabela Delivery contém alguns milhares de registros.

O número de linhas também afeta o desempenho. O banco de dados do Adobe Campaign não foi projetado para armazenar dados históricos que não são usados ativamente para fins de direcionamento ou personalização - esse é um banco de dados operacional.

Para evitar qualquer problema de desempenho relacionado ao alto número de linhas, mantenha os registros necessários no banco de dados. Qualquer outro registro deve ser exportado para um data warehouse de terceiros e removido do banco de dados operacional do Adobe Campaign.

Estas são algumas práticas recomendadas relacionadas ao tamanho das tabelas:

* Crie tabelas grandes com menos campos e mais dados numéricos.
* Não use o tipo de número grande de coluna para armazenar números pequenos, como valores booleanos.
* Remova colunas não usadas da definição da tabela.
* Não mantenha os dados históricos ou inativos no banco de dados do Adobe Campaign (exportação e limpeza).
