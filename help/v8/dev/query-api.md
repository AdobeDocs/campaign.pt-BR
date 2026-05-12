---
title: Consultar o banco de dados com queryDef
description: Saiba como usar os métodos queryDef e NLWS para consultar o banco de dados do Campaign
feature: API
role: Developer
level: Intermediate, Experienced
hide: true
exl-id: c2862f94-7d15-4a49-a74e-df90d0ea7bc9
TQID: https://experienceleague.adobe.com/Kyg3a2wvNCe2sebfG01-qMnFurvDBYS7uQfGPfVmuGE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2: id: b5852c32-876b-41ae-92a7-9f588865ae52id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0id: cfc95e9b-b035-4403-a6a9-b27a8a053a37id: e739ee2b-6228-412e-878f-45de0791417d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 1421
ht-degree: 3%

---

# Consultar o banco de dados com queryDef {#query-database-api}

[!DNL Adobe Campaign] fornece métodos avançados do JavaScript para interagir com o banco de dados usando `queryDef` e o objeto `NLWS`. Esses métodos baseados em SOAP permitem carregar, criar, atualizar e consultar dados usando JSON, XML ou SQL.

>[!NOTE]
>
>Esta documentação abrange APIs orientadas por dados para consultar o banco de dados de forma programática. Para APIs REST, consulte [Introdução às APIs REST](api/get-started-apis.md). Para criação visual de consultas, consulte [Trabalhar com o editor de consultas](../start/query-editor.md).

## O que é NLWS? {#what-is-nlws}

`NLWS` (Neolane Web Services) é o objeto global do JavaScript usado para acessar os métodos de API baseados em SOAP de [!DNL Adobe Campaign]. Os esquemas são propriedades do objeto `NLWS`, permitindo que você interaja com entidades do Campaign de forma programática.

De acordo com a [documentação JSAPI do Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html?lang=pt-BR){target="_blank"}, &quot;os esquemas são objetos globais &#39;NLWS&#39;.&quot; A sintaxe para acessar métodos de esquema segue este padrão:

```javascript
NLWS.<namespace><SchemaName>.<method>()
```

**Exemplos:**

* `NLWS.nmsRecipient` - Métodos de acesso para o esquema do destinatário (`nms:recipient`)
* `NLWS.nmsDelivery` - Métodos de acesso para o esquema de entrega (`nms:delivery`)
* `NLWS.xtkQueryDef` - Acessar métodos queryDef para consultar o banco de dados

Os métodos comuns de API incluem:

* `load(id)` - Carregar uma entidade pela respectiva ID. [Saiba mais](https://experienceleague.adobe.com/developer/campaign-api/api/f-load.html){target="_blank"}
* `create(data)` - Criar uma nova entidade
* `save()` - Salvar alterações em uma entidade

**Exemplo da documentação oficial:**

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

>[!NOTE]
>
>**Sintaxe alternativa:** Para compatibilidade com versões anteriores, você também pode ver sintaxe de namespace em minúsculas em alguma documentação (por exemplo, `nms.recipient.create()`, `xtk.queryDef.create()`). Ambas as sintaxes funcionam, mas `NLWS` é o padrão documentado na referência oficial JSAPI do Campaign.

## Pré-requisitos {#prerequisites}

Antes de usar os métodos queryDef e NLWS, você deve se familiarizar com:

* JavaScript
* Esquemas e modelo de dados do [!DNL Adobe Campaign]
* Expressões XPath para navegar por elementos de esquema

**Noções básicas sobre o modelo de dados do Campaign:**

O Adobe Campaign vem com um modelo de dados predefinido que consiste em tabelas vinculadas em um banco de dados na nuvem. A estrutura básica inclui:

* **Tabela de destinatários** (`nmsRecipient`) - Tabela principal que armazena perfis de marketing
* **Tabela de entrega** (`nmsDelivery`) - Armazena ações de entrega e modelos com parâmetros para executar entregas
* **Tabelas de logs** - Logs de execução de armazenamento:
   * `nmsBroadLogRcp` - Logs de entrega para todas as mensagens enviadas aos destinatários
   * `nmsTrackingLogRcp` - Logs de rastreamento para reações do recipient (aberturas, cliques)
* **Tabelas técnicas** - Armazene dados do sistema como operadores (`xtkGroup`), sessões (`xtkSessionInfo`), fluxos de trabalho (`xtkWorkflow`)

Para acessar as descrições de esquema na interface do Campaign, navegue até **Administração > Configuração > Esquemas de dados**, selecione um recurso e clique na guia **Documentação**.

## Métodos do esquema de entidade {#entity-schema-methods}

Cada esquema em [!DNL Adobe Campaign] (por exemplo, `nms:recipient`, `nms:delivery`) vem com métodos acessíveis por meio do objeto `NLWS`. Esses métodos fornecem uma maneira conveniente de interagir com entidades de banco de dados.

### Métodos estáticos {#static-methods}

Os métodos estáticos do SOAP são acessados chamando um método no objeto que representa o esquema. Por exemplo, `NLWS.xtkWorkflow.PostEvent()` invoca um método estático.

### Métodos não estáticos {#non-static-methods}

Para usar métodos SOAP não estáticos, você deve primeiro recuperar uma entidade usando os métodos `load` ou `create` nos esquemas correspondentes. Saiba mais na [documentação JSAPI do Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html?lang=pt-BR){target="_blank"}.

### Carregar, salvar e criar entidades {#load-save-create}

**Carregar uma entidade por ID e atualizá-la:**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**Criar um destinatário usando JSON:**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**Criar um destinatário usando XML:**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## Visão geral de QueryDef {#querydef-overview}

O esquema `xtk:queryDef` fornece métodos para compilar e executar consultas ao banco de dados. Você pode usar `NLWS.xtkQueryDef.create()` para criar consultas com sintaxe JSON ou XML.

**Operações disponíveis:**

* `select` - Recuperar vários registros
* `get` - Recuperar um único registro (SQL `LIMIT 1`)
* `getIfExists` - Recuperar um único registro, retornar nulo se não for encontrado
* `count` - Contar registros que correspondem aos critérios

Saiba mais sobre os métodos queryDef na [documentação do Campaign JSAPI](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}.

## Consulta com JSON {#query-json}

Use `NLWS.xtkQueryDef.create()` para criar consultas com sintaxe JSON. A operação `get` recupera um único registro (SQL `LIMIT 1`), enquanto `select` recupera vários registros.

**Obter um único destinatário:**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**Use `getIfExists` para evitar exceções:**

Se o registro talvez não exista, use `operation: "getIfExists"` em vez de `get` para evitar exceções:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## Selecionar vários registros {#select-multiple}

Use a operação `select` para recuperar vários registros. Você pode adicionar condições, ordenação e limites.

**Fluxos de trabalho de consulta com filtros e ordenação:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**Consultar entregas com sintaxe XML:**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>**Limites de resultado:** o Campaign limita automaticamente os resultados da consulta para evitar problemas de memória:
>* O limite padrão varia de acordo com o contexto (normalmente de 200 a 10.000 registros)
>* Use `lineCount` para definir explicitamente o número máximo de resultados
>* Para conjuntos de dados grandes (>1000 registros), use workflows em vez de queryDef. Os workflows foram projetados para processar milhões de linhas com eficiência.

Saiba mais sobre [ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html?lang=pt-BR){target="_blank"} e [práticas recomendadas de consulta](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}.

## Consultar dados de transição do fluxo de trabalho {#workflow-transition-data}

Ao trabalhar com atividades JavaScript em fluxos de trabalho, você pode consultar dados de transições de entrada usando `vars.targetSchema` e `vars.tableName`.

**Consultar dados do destinatário de uma transição de fluxo de trabalho:**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>Sempre use consultas parametrizadas com `$(sz)` para cadeias de caracteres e `$(l)` para números inteiros a fim de evitar vulnerabilidades de injeção de SQL. Saiba mais na [documentação JSAPI do Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html){target="_blank"}.

## Contar registros {#count-records}

Use `Count(@id)` com um alias para contar registros.

**Contar hipóteses em execução:**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**Contagem com várias condições:**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Distribuição de valores {#distribution-values}

Obtenha a distribuição de valores para um campo específico, útil para analisar padrões de dados.

**Distribuição de códigos de país:**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## Enumerações de consulta com análise {#analyze-enumerations}

A opção `analyze` retorna nomes amigáveis para valores de enumeração. Em vez de apenas valores numéricos, o Campaign também retornará o valor da string e o rótulo usando os sufixos &quot;Nome&quot; e &quot;Rótulo&quot;.

**Mapeamento de entrega de consulta com análise de enumeração:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:deliveryMapping",
    operation: "get",
    select: {
      node: [
        {expr: "@id"},
        {expr: "@name"},
        {expr: "[storage/@exclusionType]", analyze: true}  // Analyze enumeration
      ]
    },
    where: {
      condition: [{expr: "@name='mapRecipient'"}]
    }
  }
});

var mapping = query.ExecuteQuery();

// Result includes:
// - exclusionType: 2 (numeric value)
// - exclusionTypeName: "excludeRecipient" (string value)
// - exclusionTypeLabel: "Exclude recipient" (display label)
logInfo("Type: " + mapping.$exclusionType);
logInfo("Name: " + mapping.$exclusionTypeName);
logInfo("Label: " + mapping.$exclusionTypeLabel);
```

Saiba mais sobre a [opção de análise](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#the-analyze-option){target="_blank"}.

## Paginação {#pagination}

Use `lineCount` e `startLine` para paginar por meio de conjuntos de resultados grandes.

**Recuperar registros nas páginas:**

```javascript
// Get records 3 and 4 (skip first 2)
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    lineCount: 2,     // Number of records per page
    startLine: 2,     // Starting position (0-indexed)
    select: {
      node: [
        {expr: "@id"},
        {expr: "@email"}
      ]
    },
    orderBy: {
      node: [{expr: "@id"}]  // Critical: Always use orderBy for pagination
    }
  }
});

var recipients = query.ExecuteQuery();
```

>[!CAUTION]
>
>**A paginação exige orderBy:** sem uma cláusula `orderBy`, não há garantia de que os resultados da consulta estejam em uma ordem consistente. As chamadas subsequentes podem retornar páginas diferentes ou registros duplicados. Sempre inclua um `orderBy` ao usar paginação.

Saiba mais sobre [paginação](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#pagination){target="_blank"}.

## Construção de consulta dinâmica {#dynamic-queries}

Criar consultas dinamicamente ao anexar condições de forma programática.

**Anexar condições a uma consulta existente:**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**Criar cláusulas select e where em loops:**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Métodos queryDef avançados {#advanced-methods}

Além de `ExecuteQuery()`, queryDef fornece vários métodos especializados para casos de uso avançados.

### BuildQuery - Gerar SQL sem executar {#build-query}

Use `BuildQuery()` para gerar a instrução SQL sem executá-la. Isso é útil para depurar, registrar ou transmitir consultas a sistemas externos.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

Saiba mais sobre [BuildQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html){target="_blank"}.

### BuildQueryEx - Obter SQL com cadeia de caracteres de formato {#build-query-ex}

`BuildQueryEx()` retorna a consulta SQL e uma cadeia de formato compatível com a função `sqlSelect()`.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

Saiba mais sobre [BuildQueryEx](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html){target="_blank"}.

### Selecionar tudo - Adicione todos os campos para selecionar {#select-all}

O método `SelectAll()` adiciona automaticamente todos os campos do esquema à cláusula select, evitando que você liste cada campo manualmente.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

Saiba mais sobre [SelectAll](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html){target="_blank"}.

### Atualizar - Registros de atualização em massa {#mass-update}

O método `Update()` permite executar atualizações em massa nos registros correspondentes aos critérios de consulta sem carregar cada registro individualmente.

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>As atualizações em massa afetam todos os registros correspondentes à cláusula where. Sempre teste as condições where com uma consulta select primeiro para verificar quais registros serão afetados.

Saiba mais sobre [Atualização](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html){target="_blank"}.

### GetInstanceFromModel - instâncias de modelo de consulta {#get-instance-from-model}

Use `GetInstanceFromModel()` para recuperar dados de instâncias criadas a partir de modelos.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

Saiba mais sobre [GetInstanceFromModel](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html){target="_blank"}.

## Operações em lote {#batch-operations}

Processar vários registros em lote para melhorar o desempenho.

**Rótulos de entrega de atualização em lote:**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## Execução de SQL bruta {#raw-sql}

Para operações complexas, você pode executar SQL bruto diretamente.

**Executar SQL com parâmetros:**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

**Consulta com sqlSelect:**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>Ao usar SQL bruto:
>
>* Sempre validar e limpar entradas de usuário
>* Use consultas parametrizadas com `$(sz)`, `$(l)`, `$(dt)` etc.
>* Esteja ciente das diferenças entre os bancos de dados local e em nuvem em [implantações do FFDA](../architecture/enterprise-deployment.md)

## Práticas recomendadas {#best-practices}

Ao trabalhar com os métodos queryDef e NLWS:

* **Usar fluxos de trabalho para conjuntos de dados grandes** - QueryDef não foi projetado para processamento de dados de alto volume. Para conjuntos de dados com mais de 1.000 registros, use fluxos de trabalho que podem lidar com milhões de linhas com eficiência. Saiba mais na [documentação do Campaign SDK](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* **Usar consultas com parâmetros** - Sempre usar parâmetros associados (`$(sz)`, `$(l)`) com `sqlExec` para impedir a injeção de SQL
* **Definir limites explícitos** - Use `lineCount` para controlar o tamanho do resultado. Os limites padrão do Campaign variam de acordo com o contexto (200-10.000 registros)
* **Usar orderBy com paginação** - Sempre incluir uma cláusula `orderBy` ao usar `startLine` e `lineCount` para garantir paginação consistente
* **Use getIfExists** - Use `operation: "getIfExists"` quando os registros não existirem para evitar exceções
* **Use analisar para enumerações** - Adicione `analyze: true` para selecionar nós e obter nomes e rótulos de enumeração amigáveis
* **Otimizar consultas** - Adicione as condições `where` apropriadas para limitar os conjuntos de resultados
* **Processamento em lote** - Processe vários registros em lotes para evitar problemas de memória e tempos limite
* **Reconhecimento de FFDA** - Em [implantações corporativas (FFDA)](../architecture/enterprise-deployment.md), esteja ciente de que [!DNL Campaign] funciona com dois bancos de dados



## Casos de uso prático {#use-cases}

### Depurar e registrar consultas {#debug-queries}

Use `BuildQuery()` para inspecionar o SQL gerado antes da execução:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### Duplicar um registro com SelectAll {#duplicate-record}

Usar `SelectAll()` para copiar todos os campos ao duplicar registros:

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### Validar antes da atualização em massa {#validate-mass-update}

Sempre visualizar registros afetados antes de executar atualizações em massa:

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## Referência da sintaxe da definição de consulta {#querydef-reference}

Estrutura completa do objeto `queryDef`:

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## Tópicos relacionados {#related-topics}

* [Introdução às APIs do Campaign](api.md)
* [Campaign JavaScript SDK - API de consulta](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* [Referência da API queryDef](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}
* [Documentação JSAPI do Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=pt-BR){target="_blank"}
* [Trabalhar com esquemas](schemas.md)
* [Trabalhar com o editor de consultas](../start/query-editor.md)
