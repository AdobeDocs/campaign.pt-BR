---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 6%
---
# CreateRequestByName

Criar uma nova solicitação de privacidade usando o nome interno do namespace

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending Number regulation )
```

## Parâmetros

**namespaceName** Nome interno do namespace

**reconciliationValue** Valor de reconciliação

Valor de reconciliação de **type**

**confirmDeletePending** Solicitar confirmação antes de excluir os dados

**Regulation** tipo de Regulamentação com os seguintes valores:

```xml
           
               <value label="GDPR" name="gdpr" value="1"/>
            <value label="CCPA" name="ccpa" value="2"/>
            <value label="PDPA" name="pdpa" value="3"/>
            <value label="LGPD" name="lgpd" value="4"/>
           
           
```

## Retornar valor(es)

**id** ID da solicitação recém-criada

## Recursos

**Esquema:** [nms:privacyRequest](s-nms-privacyrequest.md)

**Estático:**

Sim
