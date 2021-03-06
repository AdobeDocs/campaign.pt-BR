---
title: Novas APIs do Campaign v8
description: Novas APIs do Campaign v8
feature: API
role: Data Engineer
level: Beginner
exl-id: dd822f88-b27d-4944-879c-087f68e79825
source-git-commit: 2046e93b97e8a45c4837dd10182adc94eea6940b
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 3%

---

# APIs de campanha FDA específicas{#gs-new-api}

No contexto de um [Implantação empresarial (FDA)](enterprise-deployment.md), o Campaign v8 vem com duas APIs específicas para gerenciar dados entre o banco de dados local do Campaign e o banco de dados do Cloud. Os pré-requisitos para usá-los é ativar o mecanismo de preparo no schema. [Saiba mais](staging.md)

* API de assimilação: **xtk.session.ingest**

   Essa API é dedicada somente à inserção de dados. [Saiba mais](#data-insert-api)

* API de atualização/exclusão de dados: **xtk.session.ingestExt**

   Essa API é usada para atualizar ou excluir dados. [Saiba mais](#data-update-api)

Um fluxo de trabalho interno dedicado sincronizará os dados no banco de dados da nuvem.

## Inserir dados{#data-insert-api}

O **xtk.session.ingest** A API é dedicada somente à inserção de dados. Nenhuma atualização/exclusão.

### Inserir sem reconciliação{#insert-no-reconciliation}

**Em um fluxo de trabalho**

Use o seguinte código em um **Código JavaScript** atividade para inserir dados no banco de dados do Cloud sem reconciliação:

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Depois que o workflow é executado, a tabela de preparo é alimentada conforme esperado.

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

1. O UUID é enviado de volta para a resposta SOAP:

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

**Em um fluxo de trabalho**

Use o seguinte código em um **Código JavaScript** atividade para inserir dados no banco de dados do Cloud com reconciliação:

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Depois que o workflow é executado, a tabela de preparo é alimentada conforme esperado.

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

1. Nesse caso, o UUID não é fornecido de volta à resposta porque foi fornecido na carga. A resposta é:

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

O **xtk.session.IngestExt** A API é otimizada para atualização/exclusão de dados. Apenas para inserir, preferir **xtk.session.ingest**. Inserir está funcionando se a chave de registro não está na tabela de preparo.

### Inserir / atualizar

**Em um fluxo de trabalho**

Use o seguinte código em um **Código JavaScript** atividade para atualizar dados no banco de dados do Cloud:

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

Depois que o workflow é executado, a tabela de preparo é atualizada conforme esperado.

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

## Gestão de assinaturas {#sub-apis}

O gerenciamento de assinaturas no Campaign é descrito em [esta página](../start/subscriptions.md).

A inserção de dados de assinatura e unsubscription depende do [Mecanismo de armazenamento temporário](staging.md) no banco de dados local do Campaign. As informações do assinante são armazenadas temporariamente em tabelas de preparo no banco de dados local, e o workflow de sincronização envia esses dados do banco de dados local para o banco de dados do Cloud. Como consequência, os processos de assinatura e unsubscription são **assíncrono**. As solicitações de aceitação e recusa são processadas a cada hora por meio de um workflow técnico específico. [Saiba mais](replication.md#tech-wf)


**Tópicos relacionados**

* [JSAPI do Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=pt-BR){target=&quot;_blank&quot;}
