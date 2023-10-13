---
title: Novas APIs do Campaign v8
description: Novas APIs do Campaign v8
feature: Architecture, API, FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: dd822f88-b27d-4944-879c-087f68e79825
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 4%

---

# APIs específicas do Campaign FFDA{#gs-new-api}

No contexto de um [Implantação corporativa (FFDA)](enterprise-deployment.md), o Campaign v8 vem com duas APIs específicas para gerenciar dados entre o banco de dados local do Campaign e o banco de dados da nuvem. Os pré-requisitos para usá-los é ativar o mecanismo de preparo no esquema. [Saiba mais](staging.md)

* API de assimilação: **xtk.session.ingest**

  Essa API é dedicada somente à Inserção de dados. [Saiba mais](#data-insert-api)

* API de atualização/exclusão de dados: **xtk.session.ingestExt**

  Essa API é usada para atualizar ou excluir dados. [Saiba mais](#data-update-api)

Um fluxo de trabalho integrado dedicado sincronizará os dados no banco de dados da nuvem.

## Inserir dados{#data-insert-api}

A variável **xtk.session.ingest** A API é dedicada somente à Inserção de dados. Nenhuma atualização/exclusão.

### Inserir sem reconciliação{#insert-no-reconciliation}

**Em um workflow**

Use o código a seguir em uma **Código Javascript** Atividade para inserir dados no banco de dados em nuvem sem reconciliação:

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Depois que o fluxo de trabalho é executado, a tabela de preparo é alimentada conforme esperado.

**De uma chamada SOAP**

1. Obtenha o token de autenticação.
1. Acione a API. A carga é:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:Ingest>
           <urn:sessiontoken>___xxxxxxx-xxxx-xxx-xxx-xxxxxxxxxxx</urn:sessiontoken>
           <urn:domDoc>
               <sampleTableStg
                   testcol1="Test Value 1 (from SOAP)"
                   testcol2="Test Value 2 (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:Ingest>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. A UUID é enviada de volta para a resposta SOAP:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string">e1e7c8b3-6f79-44da-a72d-49ed0f73db2c</pstrSUuids>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Como resultado, a tabela de preparo é alimentada conforme esperado.

![](assets/no-reconciliation.png)

### Inserir com reconciliação

**Em um workflow**

Use o código a seguir em uma **Código Javascript** Atividade para inserir dados no banco de dados em nuvem com reconciliação:

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Depois que o fluxo de trabalho é executado, a tabela de preparo é alimentada conforme esperado.

![](assets/with-reconciliation.png)


**De uma chamada SOAP**

1. Obtenha o token de autenticação.
1. Acione a API. A carga é:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
     <urn:Ingest>
        <urn:sessiontoken>___5e71f4bf-d38a-4ba8-ac15-35a958f7f138</urn:sessiontoken>
        <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                testcol1="Test Value 1 (from SOAP)"
                testcol2="Test Value 2 (from SOAP)"
                xtkschema="dem:sampleTableStg">
            </sampleTableStg>
        </urn:domDoc>
     </urn:Ingest>
    </soapenv:Body>
   </soapenv:Envelope>
   ```

1. Nesse caso, a UUID não é fornecida de volta para a resposta porque foi fornecida na carga. A resposta é:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string"/>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Como resultado, a tabela de preparo é alimentada conforme esperado.

## Atualizar ou excluir dados{#data-update-api}

A variável **xtk.session.IngestExt** A API está otimizada para atualização/exclusão de dados. Somente para inserção, prefira **xtk.session.ingest**. Insert está funcionando se a chave do registro não estiver na tabela de preparo.

### Inserir/atualizar

**Em um workflow**

Use o código a seguir em uma **Código Javascript** Atividade para atualizar dados no banco de dados em nuvem:

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

Depois que o fluxo de trabalho é executado, a tabela de preparo é atualizada conforme esperado.

![](assets/updated-data.png)

**De uma chamada SOAP**

1. Obtenha o token de autenticação.
1. Acione a API. A carga é:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:IngestExt>
           <urn:sessiontoken>___444cd168-a1e2-4fb6-a2a8-73be9f133489</urn:sessiontoken>
           <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                   testcol1="Test Value E (from SOAP)"
                   testcol2="Test Value F (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:IngestExt>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. A resposta SOAP é:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestExtResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default"/>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Como resultado, a tabela de preparo é atualizada conforme esperado.

## Gerenciamento de assinaturas {#sub-apis}

O gerenciamento de assinaturas do Campaign está descrito em [esta página](../start/subscriptions.md).

A inserção de dados de subscrição e unsubscription depende da [Mecanismo de preparo](staging.md) no banco de dados local do Campaign. As informações do assinante são armazenadas temporariamente em tabelas intermediárias no banco de dados local, e o workflow de sincronização envia esses dados do banco de dados local para o banco de dados da nuvem. Como consequência, os processos de subscrição e unsubscription são **assíncrono**. As solicitações de aceitação e recusa são processadas a cada hora por meio de um fluxo de trabalho técnico específico. [Saiba mais](replication.md#tech-wf)


**Tópicos relacionados**

* [JSAPI do Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=pt-BR){target="_blank"}
