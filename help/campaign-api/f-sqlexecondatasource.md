---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# sqlExecOnDataSource

Executa um script SQL em uma fonte de dados.

```text
sqlExecOnDataSource (query, dataSource [, value1, ... ])
```

## Parâmetros

**consulta** A consulta SQL.

**dataSource** A fonte de dados.

**value1, ...** Variáveis da consulta SQL.

## Valor de retorno

O número de registros atualizados ou inseridos em um comando SQL UPDATE ou INSERT.

## Observações

Os valores autorizados para a fonte de dados podem ser:

* &quot;&quot; ou &quot;padrão&quot; aponta para o banco de dados do Adobe Campaign

* &quot;nms:extAccount:InternalName&quot; aponta para uma fonte de dados definida nas contas externas (FDA) do Adobe Campaign

* &quot;name&quot; (nome da fonte de dados) aponta para uma fonte de dados definida no arquivo de configuração da instância (config-instance.xml) no seguinte formulário:

  ```xml
                   <dataStore hosts="*" lang="">
        <dataSource name="datasourcename">
          <dbcnx encrypted="" login="" password=""
                 provider="" server=""/>
        </dataSource>
      </dataStore>
  ```

Exemplo:

```javascript
sqlExecOnDataSource("UPDATE XtkOption SET sStringValue = $(sz) WHERE sName = $(sz)", oracleExternalDB, 'WdbcOptions_TableSpaceWork_nms:extAccount:' + sExtAccount)
```

As variáveis opcionais definidas como parâmetros desta função são definidas em [sqlGetString(query, value1, ...)](f-sqlgetstring.md)

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
